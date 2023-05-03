---
title: Network analysis
prev: data-description
next: text-analysis
---

To investigate the connections between the Harry Potter characters the universe can be modelled as a social network. From the Harry Potter wiki API, we have access to all characters. Based on the wiki hyperlinks between the characters, a network of nodes and edges was be created. Each node is a character and the references are edges. The network is modelled as a directed, weighted graph. If character 1 references character 2, an edge is created with a direction from character 1 to 2. The edge is weighted by the number of times the wiki page of character 1 references character 2. 

After having filtered the data like explained in the [Data Description](../data-description), there are 1751 characters left, meaning the network has 1751 nodes. Based on the hyperlink references, the network has 7853 edges. The network can be seen below:

<img src="/images/total_network.png"     />
<i>Figur ???. TEXT</i>


The nodes are colored according to the characters 'House' attribute, meaning which house they are a member of at Hogwarts. The network reveals that a large amount of all characters is not assigned to a house. Also it is clear that a lot of characters only are linked to 1 or 2 other people, seen from the outer ring of small grouped nodes. Nevertheless, the characters in the center of the network are very interferred among each other.

If the network is sized by strength, it is clear that the most connected character in the Harry Potter universe is 'Harry Potter' meaning that he has the largest sum of weigths of incoming edges. This is seen in the network below:

<img src="/images/network_sized_strength.png"     />
<i>Figur ???. TEXT</i>

## **Random network**
To better understand the Harry Potter network, we have created a random network as a baseline for comparison. The random network is created with the same number of nodes and edges. Since the Harry Potter network is directed the random network is as well. 

<!---Despite the Harry Potter network being directed and weighted, the random network is both undirected and unweighted. EXPLAIN ??--->

<!---Furthermore, the weights of each edge is considered when calculating the total number of edges, meaning each weight number counts as an edge in the random network. The random network can be seen below:-->

<img src="/images/random_network.png"     />
<i>Figur ???. TEXT</i>

The random network is much more clustered and the degree of each node is more equally distributed such that there are no outliers, as there is in the Harry Potter network.

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
    <td>4.5</td>
    <td>4.5</td>
    <td>4.5</td>
    <td>4.5</td>
  </tr>
  <tr>
    <td>Median</td>
    <td>1</td>
    <td>2</td>
    <td>4</td>
    <td>4</td>
  </tr>
  <tr>
    <td>Mode</td>
    <td>0</td>
    <td>1</td>
    <td>4</td>
    <td>4</td>
  </tr>
  <tr>
    <td>Min</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
    <td>0</td>
  </tr>
  <tr>
    <td>Max</td>
    <td>210</td>
    <td>92</td>
    <td>13</td>
    <td>13</td>
  </tr>
</tbody>
</table>

As mentioned earlier, the degrees of the random network is more equally distributed. This is for instance seen by the fact that the median and the mean of the random network is very close. This is also stated from the fact that the degree with the highest frequency among the nodes is 4 (equal to the median). Comparing this to the Harry Potter statistics, the statistics are more varying. For instance the most frequent in-degree is 0, while the mean of the in-degrees among all characters are 4.5. This must mean that the distribution of in-degrees are very skewed (also seen from the big difference in minimum and maximum value of in degree). Lastly since the mean is almost in the middle of the minimum and maximum value (for both in- and out-degrees) for the random network, the distribution of both types of degrees seem to be Gaussian distributed, which is not the case for the Harry Potter network.

We have plotted distribution of the in- and out-degrees of the nodes:

<img src="/images/degree_distribution_network.png"     />
<i>Figur ???. TEXT</i>

From the plot it is apparent that the distribution of the character's degrees is heavy tailed. Since this is the case there must be a large inequality among both in-degrees and out-degrees. But since the line is not perfectly linear, this distribution does not fit all the way through. The slopes of both lines in the plot are negative, meaning that the most frequent occuring weights are small. Considering an example 'Tom Riddle', the values of his degrees occurs in the less frequent area, meaning that he must has a large both in-degree and out-degree.

The top characters based on in- and out-degree can be seen in the table below. Exactly as expected the characters that has the greatest both in- and out-degree is Harry Potter. This makes sense considering he is the center character throughout all books and movies. Considering that Albus Dumbledore, Tom Riddle, Ronald Weasley and Hermione Granger is on both lists as well states their importance in the universe as well. Despite this, both Ronald Weasley's father Arthur and his sister, Ginevra, is found to be very relevant to other characters though they are not among the mostly known characters.

<table>
<tr><td>

| Top 10 in-degree characters  | In-degree |
|---|---|
| Harry Potter | 210 |
| Tom Riddle | 187 |
| Albus Dumbledore | 111 |
| Ronald Weasley | 94 |
| Hermione Granger | 90 |
| Sirius Black | 67 |
| Ginevra Weasley | 65 |
| Severus Snape | 65 |
| Arthur Weasley | 62 |
| Draco Malfoy | 62 |

</td><td>

| Top 10 out-degree characters  | Out-degree |
|---|---|
| Harry Potter | 92 |
| Albus Dumbledore | 73 |
| Jacob's sibling | 62 |
| Ronald Weasley | 60 |
| Hermione Granger | 59 |
| Arthur Weasley | 49 |
| Bellatrix Lestrange | 48 |
| Ginevra Weasley | 48 |
| Cedrella Black | 45 |
| Tom Riddle | 43 |

</td></tr> </table>

If the in-degree of all characters if plotted versus their respective out-degree, it is seen, that the characters with a low in-degree also have a low out-degree, as well as the opposite in both cases. Therefore a linear relationship can be added to the plot. This is shown below:

<img src="/images/in_out_scatter.png"     />
<i>Figur ???. TEXT</i>

Since the graph is both directed and weighted according to how many times another character is referred to on their Harry Potter Wiki Fandom page, we would like to consider the distribution of edge weights among all characters. The plot is shown below, together with an indication of how many time Harry Potter is referred to on [Albus Dumbledore's page](https://harrypotter.fandom.com/wiki/Albus_Dumbledore?so=search) (Albus Dumbledore > Harry Potter), and the opposite direction (Harry Potter > Albus Dumbledore):

<img src="/images/edge_weight_distribution_network.png"     />
<i>Figur ???. TEXT</i>

We can see that the distribution of all edge weights (both in- and out-edges) is heavy tailed as well, due to the almost straight line occuring in log-log scale. Since the slope of the line decreases as more weights are considered, it means that most edges has a small weight. But large edge weights occur infrequently, for instance the weight on the edge going from Harry Potter to Albus Dumbledore (the number of times Albus is referred to on Harry's wiki page).

## **Clustering coefficient**
To investigate whether there are groupings in the Harry Potter network, we calculate the clustering coefficient. The clustering coefficient describes how much nodes tend to cluster together. A high clustering coefficient would mean that there are groups where the nodes have a high density of edges between them. Since our network is a weighted, directed graph, we used the [networkx average clustering function](https://networkx.org/documentation/stable/reference/algorithms/generated/networkx.algorithms.cluster.average_clustering.html#networkx.algorithms.cluster.average_clustering) which handles both the weight and the directed edges, when calculating the clustering coefficient. The average clustering coefficient is:
$$\langle C \rangle_{\text{HP network}} = 0.30
$$\langle C \rangle_{\text{Random network}} = 0.0027
As expected the Harry Potter network has a higher clustering coefficient than the random network does.

The Harry Potter network holds 200 nodes whose clustering coefficient is equal to 1. This means that every node, that the specific node is connected to, is also connected to each other and constitute a smaller subgraph inside the network. Also the network has 871 nodes with clustering coefficient equal to 0, meaning that for these nodes there are no connections among their respective neighbors.

When removing coefficients of 1 and 0, the top 5 clustering coefficients and the character is listed below:

| Top 5 clustered characters  | Clustering coefficient |
|---|---|
| Lucy Weasley | 0.985 |
| Sirius Black | 0.981 |
| Stamford Jorkins | 0.980 |
| Audrey Weasley | 0.979 |
| Mary Riddle | 0.970 |

COMMENT ????

## **Assortativity**
The assortativity coefficient describes the correlation between the degrees of the nodes. It compares the degrees of two connected nodes to evaluate if same degree nodes are more likely to be connected or not. In the case of out directed network, the assortativity is calculated based on either in- or out-degree on the source node and neighbouring target node. Here source node refers to a node that has a directed edge towards a another node, the neighbouring target node. This means that the coefficient eg. calculates if nodes of high in-degree often points to other nodes with a high in-degree. So the coefficient can be calculated on four combinations of comparing node degrees (in to in, in to out, out to in, and out to out). These four assortativity coefficients have been calculated:

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
    <td colspan="2">Neighbour node</td>
    <td></td>
    <td colspan="2">Neighbour node</td>
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

average closeness centrality:
$$\langle C \rangle_{\text{HP network}} = 0.064
$$\langle C \rangle_{\text{Random network}} = 0.19

distribution:
<img src="/images/closeness_cent_distribution_network.png"     />
<i>Figur ???. TEXT</i>

COMMENT

## **Double edge swap**
Could use double edge swap to see if modularity is statistically different from zero.
