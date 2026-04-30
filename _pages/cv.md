---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

Education
======
* M.T. in Software Engineering, Institut Teknologi Bandung, 2005
* S.Si. in Mathematics (_cum laude_), Institut Teknologi Bandung, 1999

Work experience
======
* February 2002 - Present: Associate Professor
  * Universitas Kristen Maranatha
  * Duties includes: Teaching, Doing research, and Community Service
  
Skills
======
* I am grateful that I get acquainted with these three things, that are:
  * Linux,
  * \\(\LaTeX\\), and
  * GPU.

Publications
======
  <ul>{% for post in site.publications reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
  
Talks
======
  <ul>{% for post in site.talks reversed %}
    {% include archive-single-talk-cv.html  %}
  {% endfor %}</ul>
  
Teaching
======
  <ul>{% for post in site.teaching reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
  
Service and leadership
======
* Currently the Head of Tim Penjamin Mutu Fakultas Teknologi dan Rekayasa Cerdas
