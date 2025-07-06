## Publications

<style>
  .pub-container {
    display: flex;
    flex-wrap: wrap;
    align-items: flex-start;
    margin-bottom: 2.5em;
    gap: 1.5em;
  }

  .pub-image {
    flex: 0 0 220px;
    overflow: hidden;
    border-radius: 12px;
    box-shadow: 0 4px 14px rgba(0, 0, 0, 0.2);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
  }

  .pub-image img {
    width: 100%;
    height: auto;
    display: block;
    transition: transform 0.4s ease;
    border-radius: 12px;
  }

  .pub-image:hover img {
    transform: scale(1.06);
  }

  .pub-info {
    flex: 1;
    min-width: 250px;
  }

  .pub-title {
    font-size: 1.15em;
    font-weight: 600;
    color: #0066cc;
    text-decoration: none;
  }

  .pub-title:hover {
    text-decoration: underline;
  }

  .pub-authors {
    font-size: 0.95em;
    margin: 0.2em 0;
  }

  .pub-meta {
    font-size: 0.9em;
    color: #555;
  }
</style>

{% for publication in site.data.publications %}
<div class="pub-container">
  {% if publication.image %}
  <div class="pub-image">
    <img src="{{ publication.image }}" alt="thumbnail for {{ publication.title }}">
  </div>
  {% endif %}
<div class="pub-info">
  {% if publication.doi %}
    {% if publication.doi contains 'doi.org' %}
      {% assign doi_url = publication.doi %}
    {% else %}
      {% assign doi_url = 'https://doi.org/' | append: publication.doi %}
    {% endif %}
    <a href="{{ doi_url }}" target="_blank" class="pub-title">{{ publication.title }}</a>
  {% else %}
    <strong class="pub-title">{{ publication.title }}</strong>
  {% endif %}
  <div class="pub-authors">{{ publication.authors }}</div>
  <div class="pub-meta">
    <em>{{ publication.venue }}</em>
    {% if publication.volume %}, Vol. {{ publication.volume }}{% endif %}
    {% if publication.issue %}, No. {{ publication.issue }}{% endif %}
    {% if publication.pages %}, pp. {{ publication.pages }}{% endif %}
    {% if publication.article_id %}, Article ID {{ publication.article_id }}{% endif %}
    , {{ publication.year }}.
  </div>
</div>

</div>
{% endfor %}
