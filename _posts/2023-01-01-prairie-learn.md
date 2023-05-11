---
layout: post
title: PrairieLearn Online Modules
date: 2023-01-01 08:00:00
description: implementing and testing the paired-vector element
_styles: >
  img.center {
    display: block;
    margin: 0 auto;
    border: 1px solid #FFFFFF
  }
  div.caption {
   margin-left: auto;
   margin-right: auto;
   width: 500px;
  }
---

## Highlights
- I designed new online exercises with MAE 2020 instructors for free-body diagrams 🏗️
- I implemented the frontend and backend of a new feature using FabricJS and Python <a href="https://github.com/PrairieLearn/PrairieLearn/pull/4466"><i class="fa-solid fa-arrow-up-right-from-square"></i></a>
- I co-authored a [paper](https://peer.asee.org/improving-understanding-of-reaction-forces-in-free-body-diagrams-using-a-paired-vector-object-in-prairie-learn) on improvement in student outcomes and got a shiny plaque 🤩

<br>
<br>

## Background on PrairieLearn

PrairieLearn is an online learning management system used by various universities in the US. PrairieLearn supports problems with a drawing canvas, which we use to build students' skills in drawing free-body diagrams (FBDs).

<img src="/assets/img/pl-images/problem-1-dark.png" alt="old PL problem" width="500" class="center"/>

<div class="caption">Here is a sample problem statement from the PrairieLearn system. The question asks students to complete a free-body diagram by drawing arrows on a canvas.</div>

One particularly challenging application of FBDs for new learners in a statics course is for "frames" consisting of multiple members, pinned together and loaded with forces. When analyzing a frame, students are taught to first draw an overall FBD and then an "exploded" FBD, which contains separate entities for each component of the frame and also shows the internal forces between components.

<img src="/assets/img/pl-images/beer.png" alt="textbook excerpt" width="500" class="center"/>

<div class="caption">Here is a free-body diagram with both external forces (T, W, A<sub>x</sub>, A<sub>y</sub>) and internal forces (C<sub>x</sub>, C<sub>y</sub>, F<sub>BE</sub>). The internal forces appear where members are pinned together, and consist of forces with the same magnitude and opposite direction.<br>Taken from <i>Statics and Mechanics of Materials</i> by Beer.</div>

A major point of confusion for students in the course is how to treat reactions on members separated from each other at pins, including (1) identifying two-force members and (2) identifying pairs of forces that form equal and opposite reactions. PrairieLearn supports grading individual forces based on their placement and orientation, but there was no mechanism to grade "exploded" FBDs for frames according to (1) and (2), which significantly limited the set of problems the platform could support and, in turn, the utility of the platform for our students.

<br>

## Investigating Client Needs

I met with the professors of our course as well as the programmers who developed the initial canvas/drawing feature in PrairieLearn to come up with a plan for implementation. We first discussed whether the current grading logic could be extended to identify and grade pairs of opposite forces in our problems specific for frames. While this would be relatively straightforward to implement, this wouldn't be the best fit for our students because we wanted them to conceptualize the equal-and-opposite internal forces (which appear in pairs whenever two elements are separated) differently from the external forces on a frame (which are simply copied over from the overall FBD to the "exploded" FBD).

<img src="/assets/img/pl-images/sketch.png" alt="drawing" width="500" class="center"/> 

<div class="caption">Here's a sketch I developed for our initial meeting. The coloring indicates that the vectors appear in pairs, and the dotted lines show the students that the forces are paired to each other.</div>

We decided on a drawing element that would allow students to insert two arrows at once onto the free-body diagram, which indicated to the backend that they had to be linked for grading. To be correct, the two arrows had to have opposite orientation (e.g. if one of them points left, the other has to point right). Since this was one of the concepts that students were learning, we didn't enforce this in the user interface: students would still be able to draw incorrect FBDs with improperly aligned forces and get feedback that the arrows need to be aligned.

<br>

## Final Product and Documentation

I implemented the frontend using the FabricJS canvas library, which PrairieLearn already extends for its drawing elements. I added a new class to extend `PLDrawingBaseElement` which cycles through colors for the student: this way, if there are multiple forces on an "exploded" free-body diagram, the student knows which forces are paired with each other. Unpaired forces remain red to be consistent with normal FBDs.

<img src="/assets/img/pl-images/soln-dark.png" alt="drawing" width="500" class="center"/>

<div class="caption">Here's the final product. The forces in this diagram correspond to the forces in parts (b)-(c) of the first figure, with pairs indicated by forces of the same color.</div>

After implementing the grading logic in Python, I wrote an entry in the [documentation](https://prairielearn.readthedocs.io/en/latest/pl-drawing/#pl-paired-vector-element) and waited for my [pull request](https://github.com/PrairieLearn/PrairieLearn/pull/4466) to be reviewed and merged. After the CI/CD process was complete, we were all set to start using the element in our course.

In order to determine the effectiveness of the new paired-vector element, we conducted an A/B test in which half of our students were given a homework assignment involving the new element, and half of the students were given simpler questions that could be supported using PrairieLearn's old features. We found that students who practiced with the new paired vectors better learned to draw exploded FBDs. I co-authored a [paper](https://peer.asee.org/improving-understanding-of-reaction-forces-in-free-body-diagrams-using-a-paired-vector-object-in-prairie-learn) on the motivation and results of this project, and we won the Best Paper Award.

<br>

## Lessons Learned

This project taught me the importance of documentation. Not only did I read the user-facing documentation when familiarizing myself with the PrairieLearn system, I also read the developer documentation to make sure I was following all the right steps to add my feature. Finally, I contributed documentation for the feature that I added, with a helpful example so that other instructors could benefit from my work.

While I had used version control before for personal projects, this was my first time seeing a CI/CD pipeline. I also had to fight with some linting/code quality checkers before my pull request was ready to merge.
<br>
All of these tools are standard in industry, but this project was my first exposure to them 🙂


<!-- For this assignment, I’m asking you to reflect on what you’ve done and explain the choices you’ve made in terms of some of the language we have learned—from keywords in lectures, examples we’ve gone over, or points made in writer/designer. Your goal, in other words, is to justify Given that, what aspects of your site did you choose to make that way, and how do they showcase your professionalism as a computer scientist or an aerospace engineer? -->

<!-- https://vb-cs.github.io/Professional-Portfolio/index.html#hero -->