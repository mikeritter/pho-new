---
layout: base
title: "Vietnamese Food and drinks"
---
<!-- Each menu section begins here /-->
{% for section in menu.sections %}

## {{ section.title }} {% if section.traditional %} _{{ section.traditional }}_ {% endif %}

<!-- Include the details section under the heading/-->
{% if section.details %}
{{ section.details }}
{% endif %}

<!-- Each section has a list of items /-->
{% if section.items %}

### Items

{% for item in section.items %}

- {% if item.number %}**{{ item.number }}** {% endif %}{%if item.traditional %} _{{item.traditional | strip }}_ : {%endif%}{{ item.title }}

{% if item.description %}

  - {{ item.description }}

{% endif %}

{% endfor %}
{% endif %}

<!-- Beverages has items in categories /-->
{% if section.categories %}
{% for category in section.categories %}

### {{ category.title }}

{% for item in category.items %}

- {% if item.number %}**{{ item.number }}** {% endif %}{% if item.traditional %} _{{ item.traditional | strip }}_ : {% endif %}{{ item.title }}

{% endfor %}
{% endfor %}

{% endif %}

{% endfor %}
