---
layout: default
title: Research
permalink: /research/
depth: 1
---
{% include base.html %}

<div class="section">
	<h1 class="c1 bb3">Research</h1>
	{% for rsch in site.data.research.research %}
	<div style="width:100%;overflow:hidden;">
		<div class="eventbox">
			<h2 class="c2 bb4 subheading">{{ rsch.title }}</h2>
			<div class="rsch-img r5">
				<img src="{{ base }}/static/img/research/{{ rsch.pic }}" class="r5" style="width:100%;" />
				{% if rsch.publication_id %}
					{% for pub in site.data.publications.publications %}
						{% if pub.id == rsch.publication_id %}
							{% if pub.DOI %}
				<a href="http://dx.doi.org/{{ pub.DOI }}" target="_blank"><p class="c3 c4h" style="text-align:center;padding-bottom:10px;font-size:0.9em;">Related article: {{ pub.title }}</p></a>
							{% else %}
				<p class="c3" style="text-align:center;padding-bottom:10px;font-size:0.9em;">Related article: {{ pub.title }}</p>
							{% endif %}
						{% endif %}
					{% endfor %}
				{% endif %}
			</div>	
			<article class="c1 rsch-txt">{{ rsch.description | markdownify }}</article>
		</div>
	</div>
	{% if rsch.video %}
	<div class="vid"><div><iframe id="ytplayer" src="http://www.youtube.com/embed/{{ rsch.video }}"></iframe></div></div>
	{% endif %}
	{% endfor %}
</div>