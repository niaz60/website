---
layout: default
title: Publications
permalink: /publications/
depth: 1
---
{% include base.html %}

<div class="section">
	<h1 class="c1 bb3">Publications</h1>
	{% for pub in site.data.publications.publications %}
	{% if pub %}
	<div class="eventbox bb3" style="margin-top:20px;">
		<p class="c1 subheading">
			{% if pub.authors %}{{ pub.authors }}{% endif %}
			{% if pub.title %}, "{{ pub.title }}"{% endif %}
			{% if pub.publisher %}, {{ pub.publisher }}{% endif %}
			{% if pub.DOI %}, <a href="http://dx.doi.org/{{ pub.DOI }}" target="_blank">{{ pub.DOI }}</a>{% endif %}
			{% if pub.year %}, {{ pub.year }}{% endif %}.
		</p>
	</div>
	{% endif %}
	{% endfor %}
</div>