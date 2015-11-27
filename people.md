---
layout: default
title: People
permalink: /people/
depth: 1
---
{% include base.html %}

{% assign principal = false %}
{% assign postdoc = false %}
{% assign grad = false %}
{% assign ugrad = false %}

{% for person in site.data.people.principal-investigator %}{% if person %}
	{% assign principal = true %}
{% endif %}{% endfor %}
{% for person in site.data.people.postdoc %}{% if person %}
	{% assign postdoc = true %}
{% endif %}{% endfor %}
{% for person in site.data.people.graduate %}{% if person %}
	{% assign grad = true %}
{% endif %}{% endfor %}
{% for person in site.data.people.undergrad %}{% if person %}
	{% assign ugrad = true %}
{% endif %}{% endfor %}

<div class="section">
	<h1 class="c1 bb3">People</h1>
	<!-- Principal Investigator -->
	{% if principal %}
	<div class="eventbox">
		<h2 class="c2 bb4 subheading">Principal Investigator</h2>
		{% for person in site.data.people.principal-investigator %}
			{% include people-include.html param="person" variable-param=person %}
		{% endfor %}
	</div>
	{% endif %}
	<!-- PostDocs -->
	{% if postdoc %}
	<div class="eventbox">
		<h2 class="c2 bb4 subheading">PostDocs</h2>
		{% for person in site.data.people.postdoc %}
			{% include people-include.html param="person" variable-param=person %}
		{% endfor %}
	</div>
	{% endif %}
	<!-- Graduate Students -->
	{% if grad %}
	<div class="eventbox">
		<h2 class="c2 bb4 subheading">Graduate Students</h2>
		{% for person in site.data.people.graduate %}
			{% include people-include.html param="person" variable-param=person %}
		{% endfor %}
	</div>
	{% endif %}
	<!-- Undergraduate Students -->
	{% if ugrad %}
	<div class="eventbox">
		<h2 class="c2 bb4 subheading">Undergraduate Students</h2>
		{% for person in site.data.people.undergrad %}
			{% include people-include.html param="person" variable-param=person %}
		{% endfor %}
	</div>
	{% endif %}
	
</div>