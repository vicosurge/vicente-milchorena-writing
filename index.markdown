---
layout: default
title: Digimente — Short Fiction by Vicente Muñoz
---

# Digimente

<p class="tagline">Short fiction by Vicente Manuel Muñoz Milchorena, writing as Digimente and as Vico.</p>

{% assign stories = site.data.stories | sort: "date" | reverse %}

{% for story in stories %}
<article class="story">
  <h3 class="story-title">
    {% if story.url %}<a href="{{ story.url }}">{{ story.title }}</a>{% else %}{{ story.title }}{% endif %}
  </h3>
  <p class="story-meta">
    <span class="pen">as {{ story.pen_name | default: "Vicente Muñoz" }}</span>
    {% if story.publication %}<span class="sep">·</span>{% if story.publication_url %}<a href="{{ story.publication_url }}">{{ story.publication }}</a>{% else %}{{ story.publication }}{% endif %}{% endif %}
    <span class="sep">·</span>{% if story.date_display %}{{ story.date_display }}{% else %}{{ story.date | date: "%B %Y" }}{% endif %}
    {% if story.language %}<span class="sep">·</span>{{ story.language }}{% endif %}
    {% unless story.url %}<span class="sep">·</span><span class="archived">link unavailable</span>{% endunless %}
  </p>
  {% if story.blurb %}<p class="story-blurb">{{ story.blurb }}</p>{% endif %}
</article>
{% endfor %}
