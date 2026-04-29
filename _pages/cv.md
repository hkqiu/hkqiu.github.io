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
* Ph.D. candidate, University of Science and Technology of China (USTC) & Changchun Institute of Applied Chemistry (CIAC), CAS
* Research focus: AI for Polymer/Molecular/Material Science

Skills
======
* Machine Learning & Deep Learning (PyTorch, Transformers)
* Molecular Dynamics Simulation
* Polymer Informatics
* Scientific Computing (Python, CUDA)

Publications
======
  <ul>{% for post in site.publications reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
