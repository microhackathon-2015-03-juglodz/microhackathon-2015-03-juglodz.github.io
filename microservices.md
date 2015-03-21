---
layout: page
title: Microservices addresses
permalink: /microservices/
---

<table class='table'>
  <tbody>
  {% for project in site.data.projects %}
    <tr>
      <td><a href="http://apps.{{ site.domain }}:{{ project.port }}">{{ project.name }} (port {{ project.port }})</a></td>
      <td><strong>{{ project.hackers }}</strong></td>
      <td><a href="http://apps.{{ site.domain }}:{{ project.port }}/swagger/index.html">Swagger</a></td>
      <td><a href="http://apps.{{ site.domain }}:{{ project.port }}/collaborators/view.html">Collaborators</a></td>
      <td><a href="http://jenkins.{{ site.domain }}:8080/job/{{ project.name }}/">Jenkins</a></td>
    </tr>
  {% endfor %}
  </tbody>
</table>

