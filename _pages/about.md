---
layout: personal
permalink: /
title: Jacob Sriraman
redirect_from:
  - /about/
  - /about.html
  - /publications/
  - /talks/
  - /cv/
  - /cv-json/
  - /resume
---

{% assign home = site.data.home %}
<section class="intro{% if home.portrait != blank and home.portrait != '' %} intro-with-portrait{% endif %}" aria-labelledby="intro-title">
  <div>
    <p class="eyebrow">{{ home.eyebrow | escape }}</p>
    <h1 id="intro-title">Jacob Sriraman<span class="accent">.</span></h1>
    <div class="intro-copy">{{ home.intro | markdownify }}</div>
    <div class="about-copy">{{ home.about | markdownify }}</div>
    {% if home.currently != blank and home.currently != '' %}
    <div class="currently"><span class="small-label">On my mind</span>{{ home.currently | markdownify }}</div>
    {% endif %}
  </div>
  {% if home.portrait != blank and home.portrait != '' %}
  <img class="portrait" src="{{ home.portrait | relative_url }}" alt="{{ home.portrait_alt | escape }}" width="200" height="240">
  {% endif %}
</section>

{% if site.data.news.size > 0 %}
<section class="section news" id="news" aria-labelledby="news-title">
  <h2 id="news-title">News</h2>
  <ul class="news-list">
    {% assign updates = site.data.news | sort: 'date' | reverse %}
    {% for update in updates limit:5 %}
    <li class="news-item">
      <time datetime="{{ update.date | escape }}">{{ update.date | append: '-01' | date: '%b %Y' }}</time>
      <div>{{ update.text | markdownify }}</div>
    </li>
    {% endfor %}
  </ul>
</section>
{% endif %}

{% if home.personal != blank and home.personal != '' %}
<section class="section personal" aria-labelledby="personal-title">
  <h2 id="personal-title">{{ home.personal_heading | escape }}</h2>
  <div class="personal-copy">{{ home.personal | markdownify }}</div>
</section>
{% endif %}

<section class="section contact" id="contact" aria-labelledby="contact-title">
  <h2 id="contact-title">Get in touch</h2>
  <div>
    <a class="email-link" href="mailto:{{ site.author.email | escape }}">{{ site.author.email | escape }} <span aria-hidden="true">↗</span></a>
    <ul class="social-links" aria-label="Find me elsewhere">
      <li><a href="https://github.com/{{ site.author.github | escape }}">GitHub <span aria-hidden="true">↗</span></a></li>
      <li><a href="{{ site.author.orcid | escape }}">ORCID <span aria-hidden="true">↗</span></a></li>
      <li><a href="https://www.linkedin.com/in/{{ site.author.linkedin | escape }}/">LinkedIn <span aria-hidden="true">↗</span></a></li>
    </ul>
  </div>
</section>
