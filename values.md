---
layout: page
title: Values
comments: false
---

<!-- Values
================================================== -->

<section class="recent-posts">
    <div class="masonrygrid row listrecent">

        {% for post in site.posts %}
            {% if post.category == "value" %}
                {% include postbox.html %}
            {% endif %}
        {% endfor %}

    </div>

</section>
