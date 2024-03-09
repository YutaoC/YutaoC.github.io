---
layout: page
permalink: /publications/
title: Publications
description:
sections:
  - bibquery: "@misc"
    text: "Submitted Papers"
  - bibquery: "@article"
    text: "Journal Papers"
  - bibquery: "@inproceedings"
    text: "Conference Papers"
years: [2024, 2023, 2022, 2021, 2020]
nav: true
nav_order: 2
---

<!-- _pages/publications.md -->
<div class="publications">

<style>
h3 {text-align: center;}
</style>

{%- for section in page.sections %}
  <a id="{{section.text}}"></a>
  <h3 class="bibtitle">{{section.text}}</h3>
  {%- for y in page.years %}

    {%- comment -%}  Count bibliography in actual section and year {%- endcomment -%}
    {%- capture citecount -%}
    {%- bibliography_count -f {{site.scholar.bibliography}} -q {{section.bibquery}}[year={{y}}] -%}
    {%- endcapture -%}

    {%- comment -%} If exist bibliography in actual section and year, print {%- endcomment -%}
    {%- if citecount !="0" %}

      {% bibliography -f {{site.scholar.bibliography}} -q {{section.bibquery}}[year={{y}}] %}

    {%- endif -%}

  {%- endfor %}

{%- endfor %}

</div>
