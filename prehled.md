---
layout: home
author_profile: true
peramlink: /prehled
---

[Kategorie](/) / [Timeline](/timeline) / **Přehled**

<div>
{%- for post in site.posts -%}
{%- assign current_date = post.date | date: "%Y" -%}
{%- if current_date != last_date -%}
{%- if date -%}<div class="spacer"></div>{%- endif -%}
<h3 class="archive__subtitle">{{- current_date -}}</h3>
{%- assign last_date = current_date -%}
{%- endif -%}
<ul>
<li><b><a href="{{- post.url -}}">{{- post.title -}}</a></b>{% include read-time.html -%}</li>
</ul>
{% endfor %}
</div>
