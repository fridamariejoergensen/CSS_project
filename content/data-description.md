---
title: Data description
prev: "/"
next: network-analysis
---

The data utilized in this project comes from the [Harry Potter fandom wiki](https://harrypotter.fandom.com/wiki/Main_Page). This wiki covers the entire universe includes the original Harry Potter books and movies, the Fantastic Beasts movies, and a roleplaying game called Hogwarts Legacy. First, the Harry Potter wiki API was queried to obtain all characters in the universe. From these queries we gained the following attributes about each character:
* Name
* Blood status (muggle, pure blood etc.)
* House (at one of the schools for magic)
* Species
* Death time
* Alias
* Gender
* Wiki-link

The wiki-links were then used to webscrape each character's wiki page. Two things were scraped from the wiki-pages, the main text of the articles:

<img src="/images/Text.png"     />


and the links in the text:

<img src="/images/All links.png"     />


From the links we counted the number of references to other characters. This data was saved for creating edges in a network.

<img src="/images/Charecter links.png"     />

## **Filtering the data**
The original data set consisted of 4066 characters. However, some of the characters had little or no information attached. We concluded that if we had no information about a character or if their name included "unidentified", they were not relevant for the network. Furthermore, some of the data was actually the actors from the Harry Potter movies. Lastly, some nodes were groups of people, eg. Arthur Weasley's ten unidentified subordinates. We created an initial network to check the degree of the characters, to exclude characters with no links. To summarize, the following filters were applied to remove data:

* If blood status, house, species, death time and alias were all "None". Removed: 91 characters
* If name started with "unidentified". Removed: 431 characters
* If name was in a list of actors webscraped from [imdb](https://www.imdb.com/title/tt0241527/fullcredits#cast). Removed: 4 characters
* If the species was "Humans" indicating that the entry was a group. Removed: 56 characters
* If character has degree 0 in the network. Removed: 1731 characters

After these filters, the data consisted of 1751 characters.

## **Visualization of data**
To gain insight into the data we have created a few visualizations. Firstly, we see that the data is mostly populated by humans, however there are many species represented in the data set. The total number of different species is 182. The distribution of the top species and a wordcloud showing the different species can be seen below.

<table>
<tr><td>

| Top 5 Species  | Count |
|---|---|
| Human | 1518 |
| Human (formerly), Ghost | 13 |
| Goblin | 10 |
| House-elf | 9 |
| Giant | 9 |

</td><td>

<img src="/images/species_wordcloud.png"     />

</td></tr> </table>
<i>Figure 1. The count of the top species and a wordcloud, where the size of a species represents the count. The size of the words are not linearly scaled, as "Human" would then be the only visible word.</i>

Humans is clearly the largest species, which makes a lot of sense for the universe. However in the wordcloud, it is clear that a lot of different species exist in the universe and a lot of them are fictional species. 

In the Harry Potter books and movies, the division of characters into houses at the British school for magic, Hogwarts, is an important theme in the universe. We have plotted the distribution of characters into houses including three houses outside of Hogwarts. The characters are distributed among 8 houses. The plot only shows 7 houses, as the last one holds all characters whose 'House' attribute is empty (referred to as 'Unknown'). The 'Unknown' house has 1398 characters and thereby is out of range compared to the other houses.

<img src="/images/houses_count.png"     />

<i>Figure 2. The count of the characters in each house. 1401 characters are excluded as their house was unknown (None), meaning their past is unknown or they never went to a school.</i>

A clear tendency to see from the data is that houses 'Griffyndor' and 'Slytherin' holds the most members, approximately 100 and 120. This makes a lot of sense given that a main theme in the Harry Potter books and movies is the feud between these two houses. Furthermore, 'Hufflepuff' and 'Ravenclaw' are also represented well with around 60 characters each, whereas the 'non-Hogwarts' houses have very few members. This holds exactly with our expectation of the universe, as it is centered around Hogwarts.

## **Community analysis**
We have an expectation that the network will be divided into communities corresponding to their houses. To investigate this hypothesis, we divided the network into communities based on their houses. As comparison, we found communities with the Louvain algorithm. For both of these community divisions we calculated the modularity, which represents the strength of a community division. A high modularity indicates that the nodes within a community are highly connected and sparsely connected to nodes outside of the community. Modularity can be used as a measure to estimate which community division captures a network structure best.
$$ Q_{\text{House communities}} = 0.13
$$ Q_{\text{Louvain communities}} = 0.60

When computing the communities, the split into communities depending on 'House' holds 8 different communities, respectively 'Gryffindor', 'Slytherin', 'Hufflepuff', 'Ravenclaw', 'Thunderbird', 'Pukwudgie' and 'Wampus'. This is a very small number of communities compared to the Louvain communities, of which there are 363.

The modularity of the Louvain communities is clearly higher. A likely explaination for the low modularity of the house communities is that the 'Unknown' house is over-represented in the data set. The 'Unknown' house was assigned to any character without a house, meaning there is no guarantee that the characters in this house have any edges between them. They are likely less connected than the characters in the other houses. The 'Unknown' house is the largest community, and since the nodes within might be lowly connected it makes sense that the modularity is low.

<img src="/images/houses_communities.png"     />

<i>Figure 3. Distribution of community sizes for both 'House' and Louvain splits.</i>¨

From the figure above it is clear that both the House communities as well as the Louvain communities are heavy tailed. This is due to the fact that the lines in log-log scale are approximately linear. At the same time it is clear, than when considering the mean of the house community sizes, it is very skewed meaning that some communities are very large and holds a great amount of member, while other communities are very small holding not that many members. 

<table>
<tr><td>

| House community | Size |
|---|---|
| Unknown | 1399 |
| Slytherin | 118 |
| Gryffindor | 107 |
| Hufflepuff | 61 |
| Ravenclaw | 61 |
| Thunderbird | 3 |
| Pukwudgie | 1 |
| Wampus | 1 |

</td><td></table>

From the table the very skewed distribution of members in each house is showed. This is was causes the mean of the community sizes to be pushed towards the right in the plot.

 <img src="/images/LYN.png" width="50" height="50" />