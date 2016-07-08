---
layout: default
title: Current Openings
permalink: /openings/
depth: 1
---
{% include base.html %}

<div class="section">
	<h1 class="c1 bb3">Current Openings</h1>
	{% for opening in site.data.openings.openings %}
		<div class="eventbox news">
			<h2 class="c3 bb4 subheading">{{ opening.title }}</h2>
			{% if opening.description %}
				<a href="./static/img/openings/{{ opening.file }}" target="_blank">
					<p class="c3 c4h">Click Here For Details</p>
				</a>
				<article class="c1">{{ opening.description }}</article>
			{% endif %}
		</div>
	{% endfor %}
</div>