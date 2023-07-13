---
layout: home
author_profile: true
permalink: /
---


**Kategorie** / [Timeline](/timeline) / [Přehled](/prehled)

{% assign sorted_categories = site.categories | sort %}
{% for category in sorted_categories %}
<div id="{{ category | first | downcase }}"><h2 class="archive__subtitle">{{ category | first }}</h2></div>
	{%- assign sorted_posts = category.last | sort: "date" | reverse -%}
	<ul>
		{%- for post in sorted_posts -%}
		<li>
			<b><a href="{{- post.url -}}">{{- post.title -}}</a></b>
			{% include read-time.html -%}
            {% if post.excerpt -%}
                <p class="archive__item-excerpt" itemprop="description">{{ post.excerpt | markdownify | strip_html | truncate: 160 }}</p>
            {%- endif %}
		</li>
		{%- endfor -%}
	</ul>
{%- endfor -%}

