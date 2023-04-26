---
title: Network analysis
prev: data-description
next: text-analysis
---

To investigate the connections between the Harry Potter characters the universe can be modelled as a social network. From the Harry Potter wiki API, we have access to all characters. Based on the wiki hyperlinks between the characters, a network of nodes and edges was be created. Each node is a character and the references are edges. The network is modelled as a directed, weighted graph. If character 1 references character 2, an edge is created with a direction from character 1 to 2. The edge is weighted by the number of times the wiki page of character 1 references character 2. 

After having filtered the data like explained in the [Data Description](../data-description), there are ???? characters left, meaning the network has ???? nodes. Based on the hyperlink references, the network has ???? edges. The network can be seen below:

??????????? Insert network ???????????????????????????

??? Explain a few design things about network, are the nodes colored? if so why, are they sized by something etc. ?????

## **Random network**
To better understand the Harry Potter network, we have created a random network as a baseline for comparison. The random network is created with the same number of nodes and edges. Since the Harry Potter network is directed the random network is as well. Furthermore, the weights of each edge is considered when calculating the total number of edges, meaning each weight number counts as an edge in the random network. The random network can be seen below:

???????? Insert random network ??????????????????


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

## **Shortest path**
We could investigate the distribution and average shortest path of the Harry Potter network compared to the random network. ?????????

## **Closeness centrality**
We could investigate the distribution and average closeness centrality of the Harry Potter network compared to the random network. ?????????

# **Community analysis**
We have an expectation that the network will be divided into communities corresponding to their houses. To investigate this hypothesis, we divided the network into communities based on their houses. As comparison, we found communities with the Louvain algorithm. For both of these community divisions we calculated the modularity, which represents the strength of a community division. A high modularity indicates that the nodes within a community are highly connected and sparsely connected to nodes outside of the community. Modularity can be used as a measure to estimate which community division captures a network structure best.
$$ Q_{\text{House communities}} = $$
$$ Q_{\text{Louvain communities}} = $$

(The modularity of the Louvain communities is clearly higher. A likely explaination for the low modularity of the house communities is that the 'Unknown' house is over-represented in the data set. The 'Unknown' house was assigned to any character without a house, meaning there is no guarantee that the characters in this house have any edges between them. They are likely less connected than the characters in the other houses. The 'Unknown' house is the largest community, and since the nodes within might be lowly connected it makes sense that the modularity is low.)

## **Double edge swap**
Could use double edge swap to see if modularity is statistically different from zero.
