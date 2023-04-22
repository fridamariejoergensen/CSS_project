---
title: Data description
prev: "/"
next: network-analysis
---

{{< load-plotly >}}

The data utilized in this project comes from the [Harry Potter fandom wiki](https://harrypotter.fandom.com/wiki/Main_Page). First, the Harry Potter wiki API was queried to obtain all characters in the universe. From these queries we gained information about a character's name, blood status (muggle, pure blood etc.), house, species, death time, alias, wiki-link, and gender. The wiki-links were then used to webscrape each character's wiki page. Two things were scraped, the main text of the articles and the links in the text. From the links we counted the number of references to other characters. This data was saved for creating edges in a network.

???? Perhaps insert gif showing were the things we found ?????

## **Filtering the data**
The original data set consisted of 4066 characters. However, some of the characters had little or no information attached. We concluded that if we had no information about a character or if their name included "unidentified", they were not relevant for the network. Furthermore, some of the data was actually the actors from the Harry Potter movies. Lastly, some nodes were groups of people, eg. Arthur Weasley's ten unidentified subordinates. We created an initial network to check the degree of the characters, to exclude characters with no links. To summarize, the following filters were applied to remove data:

* If blood status, house, species, death time and alias were all "None"
* If name started with "unidentified" 
* If name was in a list of actors webscraped from [imdb](https://www.imdb.com/title/tt0241527/fullcredits#cast)
* If the species was "Humans" indicating that the entry was a group
* If character has degree 0 in the network

After these filters, the data consisted of ???? characters.

## **Visualization of data**
To gain insight into the data we have created a few visualizations. Firstly, we see that the data is mostly populated by humans, however there are many species represented in the data set. The total number of different species is 182. The distribution of the top species and a wordcloud showing the different species can be seen below.

<table>
<tr><td>

| Top 5 Species  | Count |
|---|---|
| Human | 3096 |
| Goblin | 31 |
| House-elf | 20 |
| Human (formerly), Ghost | 19 |
| Giant | 12 |

</td><td>

<img src="/images/species_wordcloud.png"     />

</td></tr> </table>
<i>Figur ???. The count of the top species and a wordcloud, where the size of a species represents the count. The wize of the words are not linearly scaled, as "Human" would then be the only visible word.</i>

> Nulla in justo hendrerit, tincidunt mauris et, porta est. Donec in leo vitae est ultrices dapibus id nec tortor. Maecenas ut ipsum eu nisl cursus facilisis scelerisque eu ex. Aliquam euismod elementum libero, at vehicula ipsum.

Another clear tendency to see from the data is that houses 'Griffyndor' and 'Slytherin' holds the most members, approximately 250 and 225. The ??? characters are distributed among 8 houses. The plot only shows 7 houses, as the last one holds all characters whose 'House' attribute is empty (referred to as 'Unknown'). The 'Unknown' house has 2679 characters and thereby is out of range compared to the other houses.

{{<plotly json="images/Houses_count.json" height="550px" />}}

Nam commodo lorem quis tortor euismod, ut ultrices orci aliquet. Sed eget dui nec sem ullamcorper convallis id nec ante. Aliquam ultricies a massa quis semper. Donec suscipit augue ut sagittis hendrerit. Aliquam erat volutpat. Proin aliquet maximus nibh, id aliquet justo maximus at. Sed accumsan ante id aliquam pellentesque. 

![](/images/dtu-logo.png)

Aliquam nec hendrerit quam. Suspendisse maximus eros sollicitudin, accumsan turpis eu, blandit nulla. Nunc lorem elit, molestie at libero gravida, placerat consectetur ante. Sed tincidunt viverra tellus a vehicula.


1. Lorem ipsum dolor sit amet
1. Lorem ipsum dolor sit amet
1. Lorem ipsum dolor sit amet

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam blandit lobortis turpis. Praesent porttitor, turpis eu posuere molestie, sem dolor scelerisque sapien, eu aliquet ante felis ac metus. Pellentesque semper ultricies urna. Aenean auctor, turpis ut convallis ultrices, eros tellus bibendum risus, eu varius velit ante et diam. 

* Lorem ipsum dolor sit amet
* Lorem ipsum dolor sit amet
* Lorem ipsum dolor sit amet

In suscipit lorem orci, eu placerat nibh dignissim ut. Nullam consequat nisl dui, in ornare risus porttitor sed. Integer vitae nibh semper purus ultrices rutrum. Pellentesque non diam ornare, imperdiet elit a, tempus lacus. Suspendisse viverra euismod dapibus.

Suspendisse non tellus faucibus, dapibus leo at, elementum magna. Fusce quis ante ex. In non ex eleifend, luctus risus quis, dapibus velit. Nulla facilisi. Integer iaculis arcu at fermentum varius. Donec auctor dolor non dolor pulvinar luctus. Mauris vestibulum lacinia nisl, a dictum erat molestie sed. Vivamus vel blandit turpis, nec sollicitudin massa. Nunc velit eros, tristique elementum congue eget, auctor dictum tellus. 

Quisque iaculis, sem quis imperdiet faucibus, nunc lorem feugiat purus, vestibulum condimentum turpis turpis ut ante. Donec vestibulum lectus ut ullamcorper condimentum. Curabitur fermentum nulla vitae arcu sollicitudin pulvinar.

<img src="/images/dtu-logo.png" width="200" />

Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia curae; Suspendisse eu tellus ut erat porttitor luctus. Vivamus aliquam auctor massa, in auctor orci. Ut quis enim ut lorem consectetur blandit dictum eu mauris.