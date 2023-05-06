---
title: About this project
layout: single
next: data-description
---

 Our main concept is to analyze the network of Harry Potter characters. The assumption is that the Harry Potter universe functions as a (real) network, and that Wiki pages are a good documentation of the universe (because the fictional world is so well-documented with info from books, movies, etc.). The purpose of the task is to investigate whether expectations about the Harry Potter universe align with what a network based on Wiki information would reveal. We will explore the Harry Potter universe by mapping connections on their wiki pages. This means that each character is a node, and edges come from references to other people in the text (directed, weighted edges by number of references). 

 <img src="/images/Hogwarts.jpg" />

We will use the Harry Potter API to get all characters in the universe, which will be nodes in a network. To create the network, we will use web scraping to determine edges between the nodes through hyperlinks on each character's page on the Harry Potter Wiki. To populate the nodes with attributes we will use a Harry Potter database API. We will perform text processing on the content of the specific pages for individuals on the Harry Potter Wiki.

The different sections of our analysis can be found using the Navigation Menu in the top right corner. And all the behind the scenes stuff, including code and further explanations can be found in our [Explainer Notebook](explainer-notebook.html).


# !! INDSÆT RIGTIGT LINK TIL EXPLAINER!!!!!!

