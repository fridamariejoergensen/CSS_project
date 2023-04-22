---
title: Network analysis
prev: data-description
next: text-analysis
---

From the data consisting of characters and wiki references between the characters, a network of nodes and edges can be created. The network is modelled as a directed, weighted graph. If character 1 references another character 2 an edge is created with a direction from character 1 to 2. The edge is weighted by the number times the wiki page of character 1 references character 2.

## **Assortativity and Disassortativity**
The <a href="https://en.wikipedia.org/wiki/Assortativity" target="_blank">assortativity coefficient</a> describes the correlation between the degrees of the nodes. It compares the degrees of two connected nodes to evaluate if same degree nodes are more likely to be connected or not. The assortativity coefficient is calculated by  
$$r=\frac{\sum_{jk}kj(e_{jk}-q_jq_k)}{\sigma^2_q}$$

Explanation of formula