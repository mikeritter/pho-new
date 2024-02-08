---
layout: base.liquid
pagination:
    data: menu.sections
    size: 1
    alias: section
permalink: "menu/{{ section.title | slugify }}/"
---
<!-- Each menu section begins here /-->
# {{ section.title }} {% if section.traditional %} _{{ section.traditional }}_ {% endif %}

<!-- Include the details section under the heading/-->
{% if section.details %}
{{ section.details }}
{% endif %}

<!-- Each section has a list of items /-->
{% if section.items %}

## Items

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

{% if category.details %}{{ category.details }}{% endif %}

{% for item in category.items %}

- {% if item.number %}**{{ item.number }}** {% endif %}{% if item.traditional %} _{{ item.traditional | strip }}_ : {% endif %}{{ item.title }}

{% endfor %}
{% endfor %}

{% endif %}
