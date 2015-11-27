---
layout: default
title: News
permalink: /news/
depth: 1
---
{% include base.html %}

<div class="section">
	<h1 class="c1 bb3">News</h1>
	{% for post in site.posts %}
	{% if post.category == "news" %}
		<div class="eventbox news">
			<h2 class="c3 bb4 subheading">{{ post.title }}</h2>
			<p class="c3">{{ post.date | date: "%b %-d, %Y" }}</p>
			{% if post.pic %}
			<div class="rsch-img r5">
				<img src="{{ base }}/static/img/research/{{ post.pic }}" class="r5" style="width:100%;" />
			</div>
			{% endif %}
			<article class="c1">{{ post.content }}</article>
		</div>
		{% if post.video %}
		<div class="vid"><div><iframe id="ytplayer" src="http://www.youtube.com/embed/{{ post.video }}"></iframe></div></div>
		{% endif %}
	{% endif %}
	{% endfor %}
</div>