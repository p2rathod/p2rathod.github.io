---
title: RSVP Module for Wedding Events
layout: post
category: long-form
---

I was recently tasked with the pleasure of building a friend's site for his wedding. They wanted their guests to RSVP online - seemed pretty simple. Unfortunately I wasn't able to find a *good* out-of-the-box solution (not to say they don't exist).

I decided to build the RSVP module on my own. I was keen to use new tools like Firebase, Sendgrid, and Parse Cloud.

The following is a quick description of that project with (admittadly, not well written at all) code examples.

---

## Product Functionality:

* Search for a single household's attendees by searching for a single person's name
* Ability to RSVP for the wedding and reception for a single househould at the same time.
* Otherwise put, a household doesn't have to search for their names individually. One person can RSVP for everybody.
* Ability to set dietary restrictions from a predefined list (Vegetarian, Halal, No Beef, None)
* Ability to provide custom dietary restrictions (e.g. Peanut Allergy)

---


## The UI

A couple of screenshots of the UI. These include searching for a name, and the result - the family's attendees.

![Name Lookup]({{site.url}}/images/rsvp_wedding/name_lookup.png)
![RSVP Result]({{site.url}}/images/rsvp_wedding/rsvp_result.png)

---

## The Data Model
The data model was a simple listing of attendees. Each attendee had:

* First Name
* Last Name
* Postal Code - this was the key that grouped each household together
* Note - special note, such as a kids menu
* Type - whether this guest was the primary invite, or a guest
* RSVP for Wedding - the first event
* RSVP for Reception - the second event
* Dietary Restriction - free text
* RSVP complete flag - flag signifying the completion of the RSVP

An example:

	{
	    "contact" : "pratik.rathod@gmail.com",
	    "first_name" : "Pratik",
	    "full_name" : "Pratik Rathod",
	    "last_name" : "Rathod",
	    "note" : "",
	    "postal_code" : "001",
	    "rsvp_complete" : true,
	    "rsvp_diet" : "veggie",
	    "rsvp_reception" : true,
	    "rsvp_wedding" : true,
	    "type" : "Primary"
	}

---

## The Backend (Firebase.com)
I decided to use firebase for three reasons:

* The tutorial was clear and simple and the documentation was in depth.
* The integration was straightforward.
* It was free.

The Firebase integration allows you to hack together a web app with a JSON data set - perfect for a listing of attendees. The list was key'ed on a attendee ID that was auto-incremented by Firebase.

To set up the tool, I simply initialized it with my credientials and referenced the list of attendees:


	var ref = new Firebase("https://domain.firebaseio.com/invite_list");


Once initialized, we could respond to a name lookup and produce the household fairly easily.

First we look up the name and get the postal code:

	// get the first name and 
	// uppercase the first letter (helper function in script)
	var first = upper_first_letter(document.getElementById("firstname").value);
	var last = upper_first_letter(document.getElementById("lastname").value);

	var name = first + " " + last;

	// search for user by using person's full name
	ref.orderByChild("full_name").equalTo(name).limitToLast(1).once("value", function(snapshot) {
		if (snapshot.numChildren() == 0) {
		  console.log("user not found");
		  $("#rsvpSuccessAlert").hide();
		  $("#rsvpUserNotFound").show(400);
		}
		else {
		  $("#rsvpUserNotFound").hide();
		  var postalcode = 0;

		  // for some reason, the search returned multiple rows
		  $.each( snapshot.val(), function( index, value ) {
		    if (value) {
		      postalcode = value.postal_code;
		      return false;
		    }
		    else {
		      console.log("value is undefined");
		    }
		  });  

		  get_family_from_postal(postalcode);
		}
	});



Then we look up the family of names using the postal code:

	// Get family members based on postal code
	// show each person's status in their form
	function get_family_from_postal(postalcode) {
	  ref.orderByChild("postal_code").equalTo(postalcode).once("value", function(familysnap) {
	    $.each( familysnap.val(), function( index, person ) {
	      if (person) {
	        var formhtml = $.parseHTML(nameForm);
	        if (person.type === "Guest") { name += " (Guest)"; }
	        $(formhtml).find('#lookup_names').text(person.full_name);
	        if (person.rsvp_complete) {
	          set_status_if_filled(formhtml, person);
	        }
	        else {
	          set_default_rsvp_values(formhtml);
	        }
	        add_change_event_on_diet(formhtml);

	        // save key to global variable. This is used when submitting the form.
	        family[person.full_name] = index; 
	        // add name to rsvp list
	        $('#rsvpForm .lookup_info').append($(formhtml));
	      }
	    });
	    attach_rsvp_submission_handler();

	    // Remove the search form
	    // Add the RSVP form
	    $("#contactForm").hide(400);
	    $("#rsvpForm").show(400);
	  });
	}
	


*Finally, we produce a form for each household member.* 

Note that I used re-used the same snippet (including IDs) for each family member (technically a html faux-pas).

	var nameForm = "\
	<div id='lookup_rsvp_in'  class='form-group controls'> \
	    <div id='lookup_names'>Pratik Rathod</div>\
	    <input id='weddingRSVP' type='checkbox' name='rsvp_wedding' data-animate='false' data-handle-width='25' data-on-text='Yes' data-off-text='No' data-on-color='success' data-off-color='warning' data-size='small' value='rsvp_wedding'>Wedding</input>\
	    <input id='receptionRSVP' type='checkbox' name='rsvp_reception' data-animate='false' data-handle-width='25' data-on-text='Yes' data-off-text='No' data-on-color='success' data-off-color='warning' data-size='small' value='rsvp_reception'>Reception</input> \
	    <select name='rsvp_diet' id='rsvp_diet' class='rsvp_diet'> \
	      <option selected disabled>Dietary Restrictions</option> \
	      <option value='none'>None</option> \
	      <option value='veggie'>Vegetarian</option> \
	      <option value='halal'>Halal</option> \
	      <option value='nobeef'>No Beef</option> \
	      <option value='other'>Other (Please Specify)</option> \
	    </select> \
	    <input id='rsvp_other_diet' class='rsvp_other_diet' name='rsvp_other_diet' type='text' placeholder='Other Diet' size='8' /> \
	</div>\
	";
	

---

## Updating Firebase.com
While loading each name, we saved the attendees key in a global variable. This allowed us to load and update each indivudial Firebase record indpenedently of all others. The code is below:


	$.each( people_form, function( index, person ) {

      // find name and diet within form
      var name = $(person).find('#lookup_names').text();
      var othersOption = $(person).find('#rsvp_diet').find('option:selected');
      if(othersOption.val() == "other") {
        // replace select value with text field value
        othersOption.val($(person).find('#rsvp_other_diet').val());
      }
    
      // find person to upload new data to
      var up_person = new Firebase("https://domain.firebaseio.com/invite_list/" + family[name]);
      if (up_person) {
        up_person.update({
          "rsvp_wedding":$(person).find('input[name=rsvp_wedding]').is(':checked'),
          "rsvp_reception":$(person).find('input[name=rsvp_reception]').is(':checked'),
          "rsvp_diet":othersOption.val(),
          "rsvp_complete":true
        });
      
        // send a backup email of activity
        send_backup_email(name, up_person);
      }
    });


---


## Email Submission for Backup (Sendgrid + Parse Cloud)
While the firebase back end was good for full storage, we thought it was best to also send an email confirmation to the couple. This required a tool like Sendgrid, an online email service. Unfortunately, Sendgrid doesn't support static websites and so integration was a problem. Fortunately, the following link provided all I was looking for: [Sendgrid via Parse Cloud Computing](https://sendgrid.com/blog/send-email-static-websites-using-parse/). This was perfect.

The cloud code looked like this:

	Parse.Cloud.define("sendEmail", function(request, response) {
	  var sendgrid = require("sendgrid");
	  sendgrid.initialize("email", "pwd");
	 
	  var name = request.params.name;
	  var to = request.params.to;
	  var toname = request.params.toname;
	  var from = request.params.from;
	  var subject = request.params.subject;
	  var text = request.params.text;
	 
	  sendgrid.sendEmail({
	   to: to,
	   toname: toname,
	   from: from,
	   subject: subject,
	   text: text
	   }, {
	     success: function(httpResponse) {
	       console.log(httpResponse);
	       response.success("Email sent!");
	    },
	     error: function(httpResponse) {
	       console.error(httpResponse);
	       response.error("Uh oh, something went wrong (Parse + Sendgrid)");
	    }
	  });
	});


Client side, we need a simple initialization and call to the service. 

That code looked like the following:

	$(document).ready(function(){
	  // Initialize Parse with your Parse application & javascript keys
	  Parse.initialize("ID Here", "JS ID here"); 
	});

	// Send backup email to kiranwedsjustin@gmail.com
	// This uses Sendgrid via Parse Cloud Computing
	// https://sendgrid.com/blog/send-email-static-websites-using-parse/
	function send_backup_email(name, upload_person) {
	  upload_person.on("value", function(snapshot) {
	    var data = {};
	    data["to"] = "kiranwedsjustin@gmail.com";
	    data["toname"] = "Kiran Weds Justin";
	    data["from"] = "kiranwedsjustin@gmail.com";
	    data["subject"] = "RSVP: " + name;
	    data["text"] = JSON.stringify(snapshot.val(), undefined, 2);

	    // Run our Parse Cloud Code and 
	    // pass our 'data' object to it
	    Parse.Cloud.run("sendEmail", data, {
	      success: function(object) {
	        console.log("email confirmation sent");
	      },
	      error: function(object, error) {
	        console.log("email failed: " + error);
	      }
	    });

	  }, function (errorObject) {
	    console.log("The confirmation email could not be sent: " + errorObject.code);
	  });
	}
	
A version of the code is [here](https://github.com/kiranandjustin/kiranandjustin.github.io/blob/master/js/firebaselib.js).

All in all - a pretty interesting hack. Hopefully others can make use of this and improve on it

Best,
Pratik








