---
layout: page
title: Travel
comments: false
---

<!-- Featured
================================================== -->

<section class="featured-posts">
    <div class="section-title">
        <h2>
            <span>Featured</span>
        </h2>
    </div>
    <div class="row listfeaturedtag">

        {% for post in site.posts %}
            {% if post.category == "travel" %}
                {% if post.travel_featured == true %}
                    {% include featuredbox.html %}
                {% endif %}
            {% endif %}
        {% endfor %}

    </div>

</section>

<!-- Travel
================================================== -->

<section class="recent-posts">
    <div class="masonrygrid row listrecent">

        {% for post in site.posts %}
            {% if post.category == "travel" %}
                {% include postbox.html %}
            {% endif %}
        {% endfor %}

    </div>

</section>
