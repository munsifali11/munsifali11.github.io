## Publications

{% for publication in site.data.publications %}
- <strong>{{ publication.authors }}</strong>.  
  "{{ publication.title }}".  
  <em>{{ publication.venue }}</em>{% if publication.volume %}, Vol. {{ publication.volume }}{% endif %}{% if publication.issue %}, No. {{ publication.issue }}{% endif %}{% if publication.pages %}, pp. {{ publication.pages }}{% endif %}{% if publication.article_id %}, Article ID {{ publication.article_id }}{% endif %}, {{ publication.year }}.{% if publication.doi %} [DOI](https://doi.org/{{ publication.doi }}){% endif %}
{% endfor %}

