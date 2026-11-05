---
layout: archive
title: "Funding"
permalink: /funding/
author_profile: true

funding:
  - name: "Center SynGen"
    logo: "/images/funding/syngen.png"
    logo_alt: "Center SynGen"
    text: "The DNA VirtMat Unit is a research platform for computational DNA design."
    link: "https://www.syn-gen.de/"

  - name: "Carl-Zeiss-Stiftung"
    logo: "/images/funding/czs.jpg"
    logo_alt: "Carl-Zeiss-Stiftung"
    text: "Supports Center SynGen, including the DNA VirtMat Unit."
    link: "https://www.carl-zeiss-stiftung.de/en/"

  - name: "Research Training Group (RTG) 2450"
    logo: "/images/funding/grk.png"
    logo_alt: "Research Training Group 2450"
    text: "Our group contributes to Project P3 on multiscale simulations of single-site catalysis in porous materials."
    link: "https://www.compnano.kit.edu/"

  - name: "German Research Foundation (DFG)"
    logo: "/images/funding/dfg.jpg"
    logo_alt: "German Research Foundation (DFG)"
    text: "Supports our research through Research Training Group 2450."
    link: "https://www.dfg.de/en"

  - name: "Virtual Materials Design (VirtMat)"
    logo: "/images/funding/virtmat.png"
    logo_alt: "Virtual Materials Design (VirtMat)"
    text: "KIT initiative within the Helmholtz Joint Lab Virtual Materials Design in the research field Information."
    link: "https://www.materials.kit.edu/298.php"
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

Our research is supported through the following funding bodies and research programmes.

<div class="research-funding">
{%- for item in page.funding -%}
  <article class="research-funding__card">
    {%- if item.link and item.link != "" -%}
      <a class="research-funding__logo" href="{{ item.link | escape }}" aria-label="{{ item.name | escape }}">
    {%- else -%}
      <div class="research-funding__logo">
    {%- endif -%}
      {%- if item.logo and item.logo != "" -%}
        <img src="{{ item.logo | relative_url }}" alt="{{ item.logo_alt | default: item.name | escape }}" loading="lazy">
      {%- else -%}
        <span class="research-funding__placeholder" aria-hidden="true">LOGO</span>
      {%- endif -%}
    {%- if item.link and item.link != "" -%}
      </a>
    {%- else -%}
      </div>
    {%- endif -%}
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
