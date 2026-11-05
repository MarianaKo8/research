---
layout: archive
title: "News"
permalink: /news/
author_profile: true


news:
  - date: "2026-10-30"
    headline: "Our CENP-A study selected for the 2026 Nanoscale HOT Articles collection"
    text: >-
      Using coarse-grained molecular dynamics, we investigated allosteric coupling in CENP-A upon CENP-N binding.
      [View the HOT Articles collection](https://pubs.rsc.org/nr/collection/33355/2026-Nanoscale-HOT-articles).
    link: "https://doi.org/10.1039/D5NR04720J"

  - date: "2026-10-23"
    headline: "Aleksandr Avdoshin defends his doctoral thesis with summa cum laude"
    text: "Congratulations, Aleksandr!"
    link: ""

  - date: "2026-07-16"
    headline: "Helmy Pacheco Hernández successfully defends her PhD"
    text: "Her doctoral research was supported by a DAAD scholarship. Congratulations, Helmy!"
    link: ""

  - date: "2025-09-12"
    headline: "Best Poster Award for Helmy in Turin"
    text: >-
      Helmy received the Best Poster Award at the Ab Initio Modelling in Solid State Chemistry Summer School
      for her work on two-photon absorption in pyrene-based MOFs. Congratulations!
    link: "https://www.int.kit.edu/wenzel.php"

  - date: "2025-05-17"
    headline: "Sharing synthetic genomics at the KIT Open Day"
    text: >-
      Our group joined Center SynGen to introduce visitors to DNA research and synthetic genomics.
      [SynGen report](https://www.syn-gen.de/news/kit-open-day)
      · [KIT Open Day](https://www.kit.edu/kit/english/open-day.php).
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
