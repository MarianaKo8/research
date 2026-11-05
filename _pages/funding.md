---
layout: archive
title: "Funding"
permalink: /funding/
author_profile: true

# EDIT THE CARDS BELOW. Replace or delete these examples before publishing.
# Each item makes one card: logo, funding body or programme, and short text.
# Cards appear in the order listed, three per row on larger screens.
# Copy one complete item to add another card. There are no year groups.
# Put logos in images/funding/ and use a path such as:
# logo: "/images/funding/funder-logo.png"
# A blank logo shows a neutral placeholder, so no missing image is displayed.
# Leave link as "" when no funder or project website should be linked.
funding:
  - name: "Funding body or programme 1"
    logo: ""
    logo_alt: ""
    text: "Replace with a short description of the project or research supported by this funder."
    link: ""

  - name: "Funding body or programme 2"
    logo: ""
    logo_alt: ""
    text: "Replace with a short description of the project or research supported by this funder."
    link: ""

  - name: "Funding body or programme 3"
    logo: ""
    logo_alt: ""
    text: "Replace with a short description of the project or research supported by this funder."
    link: ""
---

{% include base_path %}

<style>
.research-funding {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 28px 24px;
  align-items: start;
}
.research-funding__card {
  min-width: 0;
  text-align: center;
}
.research-funding__logo {
  box-sizing: border-box;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 120px;
  padding: 14px;
  border: 1px solid var(--global-border-color, #ddd);
  border-radius: 4px;
  background: #fff;
}
.research-funding__logo img {
  display: block;
  width: 100%;
  height: 100%;
  max-width: 100%;
  object-fit: contain;
  border: 0;
}
.research-funding__placeholder {
  color: #777;
  font-size: 0.85em;
  letter-spacing: 0.06em;
}
.research-funding__name {
  margin: 14px 0 8px;
  padding: 0;
  border: 0;
  font-size: 1em;
  font-weight: 600;
  line-height: 1.4;
  overflow-wrap: anywhere;
}
.research-funding__text {
  font-size: 0.9em;
  line-height: 1.6;
  overflow-wrap: anywhere;
}
.research-funding__text > :first-child { margin-top: 0; }
.research-funding__text > :last-child { margin-bottom: 0; }
@media (max-width: 900px) {
  .research-funding { grid-template-columns: repeat(2, minmax(0, 1fr)); }
}
@media (max-width: 600px) {
  .research-funding { grid-template-columns: minmax(0, 1fr); }
}
</style>

<div class="research-funding">
{%- for item in page.funding -%}
  <article class="research-funding__card">
    <div class="research-funding__logo">
      {%- if item.logo and item.logo != "" -%}
        <img src="{{ item.logo | relative_url }}" alt="{{ item.logo_alt | default: item.name | escape }}" loading="lazy">
      {%- else -%}
        <span class="research-funding__placeholder" aria-hidden="true">LOGO</span>
      {%- endif -%}
    </div>
    <h2 class="research-funding__name">
      {%- if item.link and item.link != "" -%}
        <a href="{{ item.link | escape }}">{{ item.name | escape }}</a>
      {%- else -%}
        {{ item.name | escape }}
      {%- endif -%}
    </h2>
    {%- if item.text and item.text != "" -%}
      <div class="research-funding__text">{{ item.text | markdownify | strip }}</div>
    {%- endif -%}
  </article>
{%- endfor -%}
</div>

{%- if page.funding == empty or page.funding == nil -%}
<p>Funding information will appear here.</p>
{%- endif -%}
