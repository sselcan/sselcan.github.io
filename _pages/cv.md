---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

Here is my full CV. You can read it below or download a copy.

<p>
  <a class="btn btn--primary" href="{{ base_path }}/files/Seyma_Selcan_Magara_CV.pdf" download>Download CV (PDF)</a>
</p>

<div class="cv-embed">
  <object data="{{ base_path }}/files/Seyma_Selcan_Magara_CV.pdf" type="application/pdf" width="100%" height="100%">
    <p>Your browser can&rsquo;t display PDFs inline.
      <a href="{{ base_path }}/files/Seyma_Selcan_Magara_CV.pdf">Download the CV instead</a>.</p>
  </object>
</div>

<style>
  .cv-embed {
    width: 100%;
    height: 80vh;
    min-height: 500px;
    margin-bottom: 2em;
    border: 1px solid #e6e6e6;
  }
  @media (max-width: 600px) {
    /* inline PDF viewers are unusable on small screens; the download link above still works */
    .cv-embed { display: none; }
  }
</style>

A short summary follows below; see also [Publications](/publications/) and [Teaching](/teaching/).

---

Education
======
* Ph.D in Computer Science, University of Tübingen, 2026 (expected)
* M.Sc. in Computer Science, Sabanci University, 2022
* B.Sc. in Computer Science and Engineering, Sabanci University, 2019
* B.Sc. in Electronics Engineering, Sabanci University, 2018


<!-- Work experience
======
* Researcher
  * GitHub University
  * Duties includes: Updates and improvements to template
  * Supervisor: The Users

* 2018-2022: Teaching Assistant
  * Sabanci University
  * Duties included: Merging pull requests
  * Supervisor: Professor Hub -->

<!-- * Summer 2015: Research Assistant
  * GitHub University
  * Duties included: Tagging issues
  * Supervisor: Professor Git
   -->
<!-- Skills
======
* Skill 1
* Skill 2
  * Sub-skill 2.1
  * Sub-skill 2.2
  * Sub-skill 2.3
* Skill 3 -->

Publications
======
  <ul>{% for post in site.publications reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
  
<!-- Talks
======
  <ul>{% for post in site.talks reversed %}
    {% include archive-single-talk-cv.html  %}
  {% endfor %}</ul>
   -->

Teaching
======
  <ul>{% for post in site.teaching reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
  
<!-- Service and leadership
======
* Currently signed in to 43 different slack teams -->
