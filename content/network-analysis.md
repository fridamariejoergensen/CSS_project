---
title: Network analysis
prev: data-description
next: text-analysis
---

To investigate the connections between the Harry Potter characters the universe can be modelled as a social network. From the Harry Potter wiki API, we have access to all characters. Based on the wiki references between the characters, a network of nodes and edges was be created. Each node is a character and the references are edges. The network is modelled as a directed, weighted graph. If character 1 references character 2, an edge is created with a direction from character 1 to 2. The edge is weighted by the number of times the wiki page of character 1 references character 2. 

## **Assortativity and Disassortativity**
The <a href="https://en.wikipedia.org/wiki/Assortativity" target="_blank">assortativity coefficient</a> describes the correlation between the degrees of the nodes. It compares the degrees of two connected nodes to evaluate if same degree nodes are more likely to be connected or not. The assortativity coefficient is calculated by  
$$r=\frac{\sum_{jk}kj(e_{jk}-q_jq_k)}{\sigma^2_q}$$

Explanation of formula 