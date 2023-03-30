---
layout: about
title: about
permalink: /
# subtitle: <a href='#'>Affiliations</a>. Address. Contacts. Moto. Etc.

profile:
  align: right
  image: sanjit_fullbody.png
  image_circular: false # crops the image to make it circular
  address:

# selected_papers: true # includes a list of papers marked as "selected={true}"
news: true  # includes a list of news items
social: true  # includes social icons at the bottom of the page
---

Hi, I'm Sanjit! I study Computer Science at Cornell University, with a minor in Aerospace Engineering 🚀.

I'm currently interested in quantitatve as well as development roles in the trading industry. This summer, I'll be at [Akuna Capital](https://akunacapital.com/) as a quant developer. Last summer, I was a developer intern at [SIG](https://sig.com).

I love thinking about problems in mathematics and computer science. As a TA for CS 4820, I've been sharing the lessons I've learned for 4 semesters.

<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>

# Work Experience
<br>


<div class="float-right">

<figure>

  <picture>

    <img 
      src="/assets/img/akuna_logo_full.png"
      width="250"
      onerror="this.onerror=null; $('.responsive-img-srcset').remove();"
    />

  </picture>

</figure>

</div>

## Akuna Capital
##### Quantitative Developer Intern (incoming)

<br>

<br>


<div class="profile float-right">
    {%- assign img_path = include.path | remove: ".jpg" | remove: ".jpeg" | remove: ".png" | remove: ".tiff" -%}

<figure>

  <picture>

    <!-- Fallback to the original file -->
    <img 
      src="/assets/img/sig_logo.svg"
      height="62"
      onerror="this.onerror=null; $('.responsive-img-srcset').remove();"
    />

  </picture>

</figure>

</div>

## Susquehanna International Group
##### Software Engineering Intern, Test Automation Team
* I monitored the continuous deployment of software to quantitative traders.
* I modularized and migrated the testing codebase, bringing build times down 20%.
* I led a team of 6 interns to trade cryptocurrencies on a simulated exchange, building market data pipelines and investigating various strategic indicators.

<br>

<div class="float-right">

<figure>

  <picture>

    <img 
      src="/assets/img/cornell_seal_simple_web_white.svg"
      width="65"
      onerror="this.onerror=null; $('.responsive-img-srcset').remove();"
    />

  </picture>

</figure>

</div>

## Cornell University
##### Undergraduate Researcher
* As a member of [CUAI](https://cuai.github.io/), I've worked on neural networks for hypergraph node classification.
* During summer 2021 I was a fellow in the Computer Science Undergraduate Research Program (CSURP), where I researched hash proof systems.

##### Teaching Assistant
* I help run review sessions, write programming assignments, and manage the autograder for CS 4820: Intro Analysis of Algorithms.
* I help 100+ students in weekly recitations and the online Q\&A forums.


<br>

<div class="float-right">

<figure>

  <picture>

    <img 
      src="/assets/img/cup_logo.png"
      width="65"
      onerror="this.onerror=null; $('.responsive-img-srcset').remove();"
    />

  </picture>

</figure>
</div>

## Cornell Cup Robotics <a href="https://github.com/cornell-cup/C1C0_path_planning"><i class="fab fa-github"></i></a>
##### Senior Developer, Autonomous Navigation Team
* I led 6 path planning developers for our robotic lab assistant, interfacing with sensor and locomotion APIs and deploying our algorithms on the physical robot.
* I organized integration with other subteams, e.g. parsing verbal input into commands.
* I wrote a module for our indoor GPS system, allowing others to work with robot position data at a higher level of abstraction.
* I used a server-client architecture to offboard computations, improving efficiency 5x.


<br>
<br>
<br>
<br>
# Projects
<br>


## OcTET <a href="https://github.com/SanjitBasker/octet-public"><i class="fab fa-github"></i></a>
* I led a team of 3 to create Octet, an Emacs-like text editor written in OCaml.
* I implemented and compared multiple implementations of the text buffer to improve worst-case performance on operations such as pasting many lines of input.
* I tested the backend extensively with OUnit, writing glass-box and random tests.


## PrairieLearn Online Modules <a href="https://github.com/PrairieLearn/PrairieLearn/pull/4466"><i class="fab fa-github"></i></a>
* I designed new online exercises with MAE 2020 instructors for free-body diagrams.
* I wrote the frontend (FabricJS) and backend (Python) to auto-grade submissions, adding new features to target common errors in student understanding.
* I used A/B testing and co-authored a paper on improvement in student outcomes.
<br>
<br>
<br>
<br>