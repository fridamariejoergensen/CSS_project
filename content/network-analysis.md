---
title: Network analysis
prev: data-description
next: text-analysis
---

To investigate the connections between the Harry Potter characters the universe can be modelled as a social network. From the Harry Potter wiki API, we have access to all characters. Based on the wiki hyperlinks between the characters, a network of nodes and edges was be created. Each node is a character and the references are edges. The network is modelled as a directed, weighted graph. If character 1 references character 2, an edge is created with a direction from character 1 to 2. The edge is weighted by the number of times the wiki page of character 1 references character 2. 

After having filtered the data like explained in the [Data Description](data-description.md), there are 1751 characters left, meaning the network has 1751 nodes. Based on the hyperlink references, the network has 7852 edges. The network can be seen below in figure 1:

<img src="/images/total_network.png"     />
<i>Figure 1. The nodes are colored based on the table below.</i>

<table>
<tr><td>

| House  | Color of nodes |
|---|---|
| Unknown | Orange |
| Gryffindor | Dark orange |
| Slytherin | Light blue |
| Ravenclaw | Dark blue |
| Hufflepuff | Beige |
| Wampus | Pink |
| Thunderbird | Purple |
| Pukwudgie | Green |

</td></tr> </table>

The nodes are colored according to the characters 'House' attribute, meaning which house they are a member of at Hogwarts. The network reveals that a large amount of all characters is not assigned to a house. Also it is clear that a lot of characters only are linked to 1 or 2 other people, seen from the outer ring of small grouped nodes. Nevertheless, the characters in the center of the network are very interferred among each other.

In figure 2 the network is sized by strength, meaning the nodes are arranged according to the sum of all weights of incoming edges. Then it is clear that the most connected character in the Harry Potter universe is 'Harry Potter' as he has the largest sum of weigths of incoming edges. This is seen below:

<img src="/images/network_sized_strength.png"     />
<i>Figure 2. Nodes are sized by strength.</i>

## **Random network**
To better understand the Harry Potter network, we have created a random network as a baseline for comparison. The random network is created with the same number of nodes and edges. Since the Harry Potter network is directed the random network is as well. The Harry Potter network is weighted as well, therefore the random network is assigned the weights of the edges in the Harry Potter network randomly. Thereby an both directed and weighted random graph is made.

<img src="/images/random_network.png"     />
<i>Figure 3. Random network visualized and sized by strength.</i>

The random network is much more clustered and the degree of each node is more equally distributed such that there are no outliers, as there is in the Harry Potter network. At the same time the sum of incoming edge weights (strength) is more similar across all nodes.

## **Degree analysis**
The degree of a node describes how many edges are connected to a node. With directed graphs we distinguish between edges going in and out of a node, referred to as in-degree and out-degree. Though, we have modelled our network as a directed, weighted graph, the weights are not taken into account in the following degree investigation. We have summarized some statistical metrics of the degrees found in the Harry Potter network and compare this to the random network.
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
<i>Figure 4. Distribution of in- and out-degree of all characters in the Harry Potter network.</i>

From the plot it is apparent that the distribution of the character's degrees is heavy tailed. Since this is the case there must be a large inequality among both in-degrees and out-degrees. But since the line is not perfectly linear, this distribution does not fit all the way through. The slopes of both lines in the plot are negative, meaning that the most frequent occuring weights are small. Considering an example 'Tom Riddle', the values of his degrees occurs in the less frequent area, meaning that he must has a large both in-degree and out-degree. This can also be seen from the 2 tabels below, that states the top 10 characters of both largest in- and out-degree separately.

The table below reveals exactly as expected the characters that has the greatest both in- and out-degree is Harry Potter. This makes sense considering he is the center character throughout all books and movies. Considering that Albus Dumbledore, Tom Riddle, Ronald Weasley and Hermione Granger is on both lists as well states their importance in the universe as well. Despite this, both Ronald Weasley's father Arthur and his sister, Ginevra, is found to be very relevant to other characters though they are not among the mostly known characters.

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

If the in-degree of all characters is plotted versus their respective out-degree, it is seen, that the characters with a low in-degree also have a low out-degree, as well as the opposite in both cases. Therefore a linear relationship can be shown as below:

<img src="/images/in_out_scatter.png"     />
<i>Figure 5. A linear relationship between in- and out-degrees is found. </i>

The tendency shown in figure 5 reveals, that for characters with a small in-degree often has a large out-degree, but with increasing in-degree comes also an increasing out-degree. Therefore the linear relationship fits better the larger the in-degree of the character.

Since the graph is both directed and weighted according to how many times another character is referred to on their Harry Potter Wiki Fandom page, we would like to consider the distribution of edge weights among all characters. The plot is shown below, together with an indication of how many time Harry Potter is referred to on [Albus Dumbledore's page](https://harrypotter.fandom.com/wiki/Albus_Dumbledore?so=search) (Albus Dumbledore > Harry Potter), and the opposite direction (Harry Potter > Albus Dumbledore):

<img src="/images/edge_weight_distribution_network.png"     />
<i>Figure 6. Distribution of all edge weights in log-log scale.</i>

We can see that the distribution of all edge weights (both in- and out-edges) is heavy tailed as well, due to the almost straight line occuring in log-log scale. Since the slope of the line decreases as more weights are considered, it means that most edges have a very small weight. Large edge weights occur infrequently, but are very large compared to the majority of weights. An example of an infrequent and large weight is the edge going from Harry Potter to Albus Dumbledore (the number of times Albus is referred to on Harry's wiki page).

## **Clustering coefficient**
To investigate whether there are groupings in the Harry Potter network, we calculate the clustering coefficient. The clustering coefficient describes how much nodes tend to cluster together. A high clustering coefficient would mean that there are groups where the nodes have a high density of edges between them. Since our network is a weighted, directed graph, we used the [networkx average clustering function](https://networkx.org/documentation/stable/reference/algorithms/generated/networkx.algorithms.cluster.average_clustering.html#networkx.algorithms.cluster.average_clustering) which handles both the weight and the directed edges, when calculating the clustering coefficient. The average clustering coefficient is:
$$\langle C \rangle_{\text{HP network}} = 0.30 $$
$$\langle C \rangle_{\text{Random network}} = 0.0027 $$
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


The table states that it is not the most central characters, that has the largest clustering coefficient. This fulfills the expectation since the main characters are expected to have a large amount of both incoming and outgoing edges (and all of the neighbors would likely not connected). Despite the characters with clustering coefficient equal to 1, the character with the greatest clustering coefficient is Lucy Weasley. A great deal of her edges is characters in the 'Weasley' family, and in that case it makes sense that everyone else in the family is connected as well. Of her 51 edges, 33 are Weasleys as well.

## **Assortativity**
The assortativity coefficient describes the correlation between the degrees of the nodes. It compares the degrees of two connected nodes to evaluate if same degree nodes are more likely to be connected or not. In the case of out directed network, the assortativity is calculated based on either in- or out-degree on the source node and neighbouring target node. Here source node refers to a node that has a directed edge towards a another node, the neighbouring target node. This means that the coefficient eg. calculates if nodes of high in-degree often points to other nodes with a high in-degree. So the coefficient can be calculated on four combinations of comparing node degrees (in to in, in to out, out to in, and out to out). These four assortativity coefficients have been calculated:

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
    <td colspan="2">Neighbor node</td>
    <td></td>
    <td colspan="2">Neighbor node</td>
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
    <td>0.04</td>
    <td>0.07</td>
    <td></td>
    <td>0.020</td>
    <td>0.021</td>
  </tr>
  <tr>
    <td>Out degree</td>
    <td>0.13</td>
    <td>0.20</td>
    <td></td>
    <td>0.0030</td>
    <td>0.00020</td>
  </tr>
</tbody>
</table>

The values of assorsativity for the random network are very small, meaning that same degree nodes are not very likely to be connected. These values occur to be a bit higher for the Harry Potter network. The values for the Harry Potter network shows, that when the in-degree of the neighbor is considered, the assorsativity is very small (almost as small as for the random network). But when considering the out-degree of the neighbor node the assorsativity is larger for the Harry Potter network and even smaller for the random network. This suggests that for the Harry Potter network, if eigther the in- or out-degree of the source node is low, then the out-degree of neighbor node is low as well (and vice versa if the degrees are high).

## **Shortest path**
Another relevant feature to examine for the networks if the shortest paths between nodes. Since the network edges are weigthed, these are considered when finding the shortest path, such that the shortest path between 2 nodes is found by tracking the edges with the smallest weigths. In order to detect the shortest paths between all nodes in the network, the network must be strongly connected. To be strongly connected means, that there must be a path from every individual node in the every other node in the graph. Therefore we find the largest strongly connected subgraph in both the Harry Potter network and the random network.

The largest strongly connected component in the Harry Potter network holds 562 nodes, while the largest connected component in the random network holds 1717 nodes. Since the number of nodes in each of the largest connected components varies very must (respectively 562 and 1717), this may have an effect on the length of the average shortest paths. 

Using Networkx [Average shortest path length](https://networkx.org/documentation/stable/reference/algorithms/generated/networkx.algorithms.shortest_paths.generic.average_shortest_path_length.html) function, the average lengths in both networks is found to be:

$$\langle a \rangle_{\text{HP network}} = 3.66 $$
$$\langle a \rangle_{\text{Random network}} = 5.15 $$

This states, that the average shortest paths when considering all possible shortest path between nodes in both strongly connected subgraphs, the paths between nodes in the random network traverses edges of larger weigth than the paths in the Harry Potter network. A reason for this might be, as mentioned before, the largest connected component of the random networks holds approximately 3 times as many nodes, as the largest connected component of the Harry Potter network.

Considering the distribution of all shortest paths in the largest connected components, the random network has a large peak as around length 5 (which is the mean). Comparing the distribution of the paths length in the largest component of the Harry Potter network, the distribution is way more equally spread and no unusual long paths occur. This means that it is easier to get from one character to another through links on the Harry Potter Fandom Wiki page, than it would be in a random network.

<img src="/images/shortest_path_distribution.png"     />
<i>Figure 7. Distribution of shortest paths in largest connected components.</i>

Note that the y-scale on the plot is scaled by 10^6, meaning that the peak on the curve (a path length of approximately 5) occurs more than 60 times when the shortest path between all nodes in the largest connected component is calculated.

## **Closeness centrality**
Since we have considered the shortest paths in the networks, it is also relevant to investiage the closeness centrality of each of the nodes. The closeness centrality is based on the mean shortest path between a specific node and all other reachable nodes in the graph. In this case the graph does not need to be strongly connected, and therefore the closeness centrality is calculated over all nodes in both the Harry Potter network and the random network. It means that the higher the value of closeness, the more central the nodes (character) is in the network.

Taking the average of all closeness centrality values in each network gives the result:
$$\langle C \rangle_{\text{HP network}} = 0.064 $$
$$\langle C \rangle_{\text{Random network}} = 0.19 $$
These averages states that more nodes occur to be central in the random network compared to the Harry Potter network.

Since the closeness centrality is calculated for each node in the network, we examine the distribution of the values in both the Harry Potter network and the random network:
<img src="/images/closeness_cent_distribution_network.png"     />
<i>Figure 8. Distribution of closeness centrality in networks.</i>

On the distribution of the closeness centrality in both networks, the straight line for the Harry Potter network, that takes a value above 1000 on the y-axis and approximately equal to 0 on the x-axis suggests, that a very large amount of characters in the Harry Potter network are not that central due to the very low value of closeness centrality. Nevertheless, the curve goes slightly upwards again afterwards meaning that some characters holds values of closeness centrality in the interval [0.15,0.20], meaning that based on the paths to all reachable nodes, they are slightly central nodes in the network. For the random network the greatest amount of nodes (approximately 400 nodes) has a closeness centrality equal to 0.20. This means that the more nodes occur to be central in the random network than in the Harry Potter network.

