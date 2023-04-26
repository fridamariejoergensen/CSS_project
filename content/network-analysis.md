---
title: Network analysis
prev: data-description
next: text-analysis
---

To investigate the connections between the Harry Potter characters the universe can be modelled as a social network. From the Harry Potter wiki API, we have access to all characters. Based on the wiki hyperlinks between the characters, a network of nodes and edges was be created. Each node is a character and the references are edges. The network is modelled as a directed, weighted graph. If character 1 references character 2, an edge is created with a direction from character 1 to 2. The edge is weighted by the number of times the wiki page of character 1 references character 2. 

After having filtered the data like explained in the [Data Description](../data-description), there are ???? characters left, meaning the network has ???? nodes. Based on the hyperlink references, the network has ???? edges.

## **Degree analysis**
The degree of a node describes how many edges are connected to a node. With directed graphs we distinguish between edges going in and out of a node, referred to as in-degree and out-degree. Furthermore, with a weighted graph the weight of an edge is included in the degree, so we are dealing with weighted in- and out-degree. We have summarized some statistical metrics of the degrees found in the Harry Potter network and compare this to the random network.
<table>
<thead>
  <tr>
    <th></th>
    <th colspan="2">Harry Potter Network</th>
    <th colspan="2">Random Network</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>Degree Metrics</td>
    <td>In-degree</td>
    <td>Out-degree</td>
    <td>In-degree</td>
    <td>Out-degree</td>
  </tr>
  <tr>
    <td>Mean</td>
    <td>???</td>
    <td>???</td>
    <td>???</td>
    <td>???</td>
  </tr>
  <tr>
    <td>Median</td>
    <td>???</td>
    <td>???</td>
    <td>???</td>
    <td>???</td>
  </tr>
  <tr>
    <td>Mode</td>
    <td>???</td>
    <td>???</td>
    <td>???</td>
    <td>???</td>
  </tr>
  <tr>
    <td>Min</td>
    <td>???</td>
    <td>???</td>
    <td>???</td>
    <td>???</td>
  </tr>
  <tr>
    <td>Max</td>
    <td>???</td>
    <td>???</td>
    <td>???</td>
    <td>???</td>
  </tr>
</tbody>
</table>

We see that .............

We have plotted distribution of the in- and out-degrees of the nodes:
PLOT
From the plot it is apparent ...........

The top characters based on in- and out-degree can be seen in the table below. Comment ......

## **Clustering coefficient**
To investigate whether there are groupings in the Harry Potter network, we calculate the clustering coefficient. The clustering coefficient describes how much nodes tend to cluster together. A high clustering coefficient would mean that there are groups where the nodes have a high density of edges between them. Since our network is a weighted, directed graph, we used the [networkx clustering function](https://networkx.org/documentation/stable/reference/algorithms/generated/networkx.algorithms.cluster.clustering.html#networkx.algorithms.cluster.clustering) which handles both the weight and the directed edges, when calculating the clustering coefficient. The average clustering coefficient is:
$$\langle C \rangle_{\text{HP network}} = $$
$$\langle C \rangle_{\text{Random network}} = $$
(As expected the Harry Potter network has a higher clustering coefficient than the random network does.????) 

The top 5 characters based on the clustering coefficient can be seen below:

| Top 5 clustered characters  | Clustering coefficient |
|---|---|
| Harry Po | ??? |
| Vold | ??? |
| Albus | ??? |
| Ron | ??? |
| Sheep | ??? |




## **Assortativity**
The assortativity coefficient describes the correlation between the degrees of the nodes. It compares the degrees of two connected nodes to evaluate if same degree nodes are more likely to be connected or not. In the case of out directed network, the assortativity is calculated based on either in- or out-degree on the source node and target node. This means that the coefficient eg. calculates if nodes of high in-degree are highly connected to other nodes with a high in-degree. So the coefficient can be calculated on four combinations of comparing node degrees (in to in, in to out, out to in, and out to out). These four assortativity coefficients have been calculated:

Har vægt en påvirkning ???

<table>
<thead>
  <tr>
    <th></th>
    <th colspan="2">Harry Potter Network</th>
    <th></th>
    <th colspan="2">Random Network</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td></td>
    <td colspan="2">Target node</td>
    <td></td>
    <td colspan="2">Target node</td>
  </tr>
  <tr>
    <td>Source node</td>
    <td>In-degree to </td>
    <td>Out-degree</td>
    <td></td>
    <td>In-degree</td>
    <td>Out-degree</td>
  </tr>
  <tr>
    <td>In-degree</td>
    <td>???</td>
    <td>???</td>
    <td></td>
    <td>???</td>
    <td>???</td>
  </tr>
  <tr>
    <td>Out degree</td>
    <td>???</td>
    <td>???</td>
    <td></td>
    <td>???</td>
    <td>???</td>
  </tr>
</tbody>
</table>

Comment on this ?????????????