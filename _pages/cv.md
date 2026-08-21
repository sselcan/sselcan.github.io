---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

My full CV is available as a PDF. A summary follows below.

<p>
  <a class="btn btn--primary" href="{{ base_path }}/files/Seyma_Selcan_Magara_CV.pdf">Download CV (PDF)</a>
</p>

Education
======
* Ph.D in Computer Science, University of Tübingen, 2026 (expected)
* M.Sc. in Computer Science, Sabanci University, 2022
* B.Sc. in Computer Science and Engineering, Sabanci University, 2019
* B.Sc. in Electronics Engineering, Sabanci University, 2018

Publications
======
  <ul>{% for post in site.publications reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>

Teaching
======
  <ul>{% for post in site.teaching reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
