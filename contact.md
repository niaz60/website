---
layout: default
title: Contact
permalink: /contact/
depth: 1
---
{% include base.html %}

<div class="section">
	<h1 class="c1 bb3">Contact</h1>
	{% for pi in site.data.people.principal-investigator %}
	{% if pi %}
	<div class="eventbox bb3" style="margin-top:20px;text-align:center;">
		{% if pi.name %}<h6 class="c1 subheading">{{ pi.name }}</h6>{% endif %}
		{% if pi.office %}<h6 class="c1 subheading">{{ pi.office }}</h6>{% endif %}
		{% if pi.email %}<h6 class="c1 subheading">{{ pi.email }}</h6>{% endif %}
		{% if pi.phone %}<h6 class="c1 subheading">{% if pi.fax %}phone: {% endif %}{{ pi.phone }}</h6>{% endif %}
		{% if pi.fax %}<h6 class="c1 subheading">fax: {{ pi.fax }}</h6>{% endif %}
	</div>
	{% endif %}
	{% endfor %}
</div>