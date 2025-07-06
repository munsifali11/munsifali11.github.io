## Publications

{% for publication in site.data.publications %}
<div style="display: flex; flex-wrap: wrap; align-items: flex-start; margin-bottom: 2em;">
  {% if publication.image %}
  <div style="flex: 0 0 320px; margin-right: 2em;">
    <img src="{{ publication.image }}" alt="thumbnail for {{ publication.title }}" style="width: 220px; height: auto; border-radius: 8px; box-shadow: 0 2px 6px rgba(0,0,0,0.15);">
  </div>
  {% endif %}
  <div style="flex: 1; min-width: 250px;">
    <strong>{{ publication.authors }}</strong><br>
    "{{ publication.title }}"<br>
    <em>{{ publication.venue }}</em>{% if publication.volume %}, Vol. {{ publication.volume }}{% endif %}{% if publication.issue %}, No. {{ publication.issue }}{% endif %}{% if publication.pages %}, pp. {{ publication.pages }}{% endif %}{% if publication.article_id %}, Article ID {{ publication.article_id }}{% endif %}, {{ publication.year }}.{% if publication.doi %} [DOI](https://doi.org/{{ publication.doi }}){% endif %}
  </div>
</div>
{% endfor %}



