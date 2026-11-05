---
layout: archive
title: "News"
permalink: /news/
author_profile: true

# EDIT THE ENTRIES BELOW. Replace or delete these examples before publishing.
# Dates must be quoted and use "YYYY-MM-DD". The newest date appears first
# automatically, regardless of where you put an entry in this list.
# Optional fields: leave text, image, image_alt, or link as "" if not needed.
# Put news pictures in images/news/ and use a path such as:
# image: "/images/news/symposium.jpg"
# For longer explanations, use text: | and indent the following paragraphs.
news:
  - date: "2026-11-05"
    headline: "Example news headline — replace with your latest update"
    text: ""
    image: ""
    image_alt: ""
    link: ""

  - date: "2026-10-30"
    headline: "Example news item with an explanation"
    text: |
      Replace this paragraph with a short explanation when the headline needs more context.

      You can include **bold text** or [a link](https://example.com) here. Delete this text when no explanation is needed.
    image: ""
    image_alt: ""
    link: ""
---

{% include base_path %}

<style>
.research-news__item {
  display: grid;
  grid-template-columns: 112px minmax(0, 1fr);
  gap: 20px;
  padding: 20px 0;
  border-bottom: 1px solid var(--global-border-color, #ddd);
}
.research-news__item:first-child { padding-top: 0; }
.research-news__item:last-child { border-bottom: 0; }
.research-news__date {
  padding-top: 2px;
  font-size: 0.85em;
  line-height: 1.6;
  color: var(--global-text-color-light, #666);
  white-space: nowrap;
}
.research-news__headline {
  margin: 0;
  padding: 0;
  border: 0;
  font-size: 1em;
  font-weight: 600;
  line-height: 1.5;
  overflow-wrap: anywhere;
}
.research-news__text {
  margin-top: 10px;
  font-size: 0.93em;
  line-height: 1.6;
}
.research-news__text > :first-child { margin-top: 0; }
.research-news__text > :last-child { margin-bottom: 0; }
.research-news__figure { margin: 14px 0 0; }
.research-news__figure img {
  display: block;
  width: auto;
  height: auto;
  max-width: 100%;
  max-height: 280px;
  border: 0;
}
@media (max-width: 600px) {
  .research-news__item {
    grid-template-columns: minmax(0, 1fr);
    gap: 4px;
    padding: 16px 0;
  }
}
</style>

<div class="research-news">
{%- assign sorted_news = page.news | sort: "date" | reverse -%}
{%- for item in sorted_news -%}
  <article class="research-news__item">
    <time class="research-news__date" datetime="{{ item.date | escape }}">{{ item.date | date: "%d %b %Y" }}</time>
    <div class="research-news__body">
      <h2 class="research-news__headline">
        {%- if item.link and item.link != "" -%}
          <a href="{{ item.link | escape }}">{{ item.headline | escape }}</a>
        {%- else -%}
          {{ item.headline | escape }}
        {%- endif -%}
      </h2>
      {%- if item.text and item.text != "" -%}
        <div class="research-news__text">{{ item.text | markdownify | strip }}</div>
      {%- endif -%}
      {%- if item.image and item.image != "" -%}
        <figure class="research-news__figure">
          <img src="{{ item.image | relative_url }}" alt="{{ item.image_alt | default: item.headline | escape }}" loading="lazy">
        </figure>
      {%- endif -%}
    </div>
  </article>
{%- endfor -%}
</div>

{%- if sorted_news == empty or sorted_news == nil -%}
<p>Research updates will appear here.</p>
{%- endif -%}
