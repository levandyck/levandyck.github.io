---
layout: page
permalink: /publications/
title: Contributions
description:
sections:
  - bibquery: "@article"
    text: "Peer-reviewed manuscripts"
  - bibquery: "@inproceedings"
    text: "Conference proceedings"
  - bibquery: "@thesis"
    text: "Theses"
  - bibquery: "@misc"
    text: "Science communication"
years: [2024, 2023, 2022, 2021, 2020]
social: true
nav: true
nav_order: 4
---

<!-- _pages/publications.md -->
<div class="publications">

{%- for section in page.sections %}
  <a id="{{section.text}}"></a>
  <p class="bibtitle" style="font-size: 1.5em;">{{section.text}}</p>
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
