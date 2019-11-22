---
layout: default
title: Blog
---

<ul>
	{% for post in site.posts %}
		<li>
			<h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
			<post_excerpt>{{ post.excerpt }}</post_excerpt>
		</li>
	{% endfor %}
</ul>