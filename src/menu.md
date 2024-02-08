---
layout: base
title: "Vietnamese Food and drinks"
---

Let's have a landing page

<!-- We need links to our sections /-->
{% for section in menu.sections %}

## [{{ section.title}}]({{section.title | slugify | prepend:"/menu/" | url}})

{{ section.details }}

{% endfor %}
