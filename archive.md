---
layout: default
title: آرشیو ماهانه
permalink: /archive/
---
<div class="post">
	<h2>آرشیو ماهانه</h2>
	<ul>
	  {% for post in site.posts %}
	    {% unless post.next %}
	      <h3>{{ post.date | date: '%Y %b' }}</h3>
	    {% else %}
	      {% capture year %}{{ post.date | date: '%Y %b' }}{% endcapture %}
	      {% capture nyear %}{{ post.next.date | date: '%Y %b' }}{% endcapture %}
	      {% if year != nyear %}
	        <h3>{{ post.date | date: '%Y %b' }}</h3>
	      {% endif %}
	    {% endunless %}

	    <li><a href="{{ post.url }}">{{ post.title }}</a></li>
	  {% endfor %}
	</ul>
</div>
