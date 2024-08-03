---
layout: date_sparse
title: Dates
permalink: /dates/
---

<p align="center"><strong>
    Please note all deadlines are at {{ site.deadline-time }}.
</strong></p>

<div class="row pl-2 pr-2 pt-2 pb-2 mx-auto justify-content-center">
<table class="table table-striped table-bordered" style="max-width: 750px;">
  <tbody>
    <tr>
      <th scope="row">Subject</th>
      <th scope="row">Date (all deadlines {{site.deadline-time}})</th>
    </tr>
    {% for item in site.data.timeline.deadlines %}
    <tr>
      <td><del>{{ item.title }}</del>&nbsp;
          {% for tag in item.tags %}
            {% case tag.key %}
              {% when "Authors" %}
                  {% assign badge-color = "badge-success" %}
              {% when "Reviewers" %}
                  {% assign badge-color = "badge-primary" %}
              {% when "ACs" %}
                  {% assign badge-color = "badge-info" %}
              {% when "PCs" %}
                  {% assign badge-color = "badge-secondary" %}
              {% when "Everyone" %}
                  {% assign badge-color = "badge-dark" %}
              {% else %}
                  {% assign badge-color = "badge-secondary" %}
            {% endcase %}
            <span class="badge {{badge-color}} mt-2 mb-2" style="font-weight: normal;">{{ tag.key }}</span>
          {% endfor %}
      </td>
      <td>{{item.date | date: '%A, %e %B %Y'}}</td>
    </tr>
    {% endfor %}
  </tbody>
</table>
</div>