---
title: Documents
layout: default
---

<!-- add items to _data/assets, and add materials to assets/documents and assets/slides -->

## Documents

<ul>
{% for item in site.data.assets reversed %}
  {% if item.type == 'document' or item.name contains "/assets/documents" %}

    {% if item.date %}
        {% assign date = item.date | string_to_date | date: "%Y-%m-%d" %}
    {% else %}
        {% assign date = item.name | remove: "/assets/documents/" | string_to_date | date: "%Y-%m-%d" %}
    {% endif %}

    <li><a href="{{item.name}}" target="_blank">{{item.title}}</a>
    
    <!-- horrible, but liquid has no named element arrays or dicts -->
    {% for person in site.data.people %}
      {% if person.name == item.author %}
        <br> <a href="/people/{{person.name}}">{{ person.full }}</a>, {{ item.date | date: "%b %Y" }}
      {% endif %}
    {% endfor %}
    </li>
  {% endif %}
{% endfor %}
</ul>

## Presentations

<ul>
{% for item in site.data.assets reversed %}
  {% if item.type == 'slides' or item.name contains "/assets/slides" %}

    {% if item.date %}
        {% assign itemdate = item.date | string_to_date | date: "%Y-%m-%d" %}
    {% else %}
        {% assign itemdate = item.name | remove: "/assets/slides/" | string_to_date | date: "%Y-%m-%d" %}
    {% endif %}

    <li><a href="{{item.name}}" target="_blank">{{item.title}}</a> 
    
    <!-- horrible, but liquid has no named element arrays or dicts -->
    {% for person in site.data.people %}
      {% if person.name == item.author %}
        <br> <a href="/people/{{person.name}}">{{ person.full }}</a>, {{ itemdate | date: "%b %Y" }}
      {% endif %}
    {% endfor %}
    </li>
  {% endif %}
{% endfor %}
</ul>



