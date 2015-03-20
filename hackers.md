---
layout: page
title: Hackers
permalink: /hackers/
---

<ul>
  {% for hacker in site.data.attendees %}
    <li><a href="https://github.com/{{ hacker.github_username }}">{{ hacker.name }}</a></li>
  {% endfor %}
</ul>
