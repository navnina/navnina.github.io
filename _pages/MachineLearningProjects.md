---
layout : "archive"
permalink :"machine-learning"
title : "Machine Learning Posts"
author_profile : true
header:
 image:"/images/cover.jpg"

{% include base_path %}
{% include group_by_array collection=site.posts field="tags" %}

{% for tag in group_names %}
  {% assign posts = group_items[forloop.index0] %}
  <h2 id="{{ tag | slugify }}" class="archive__subtitle">{{ tag }}</h2>
  {% for post in posts %}
    {% include archive_single.html %}
  {% endfor %}
{% endfor %}
