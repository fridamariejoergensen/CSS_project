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

The wiki-links were then used to webscrape each character's wiki page. Two things were scraped, the main text of the articles and the links in the text. From the links we counted the number of references to other characters. This data was saved for creating edges in a network.

???? Perhaps insert gif showing were the things we found ?????

## **Filtering the data**
The original data set consisted of 4066 characters. However, some of the characters had little or no information attached. We concluded that if we had no information about a character or if their name included "unidentified", they were not relevant for the network. Furthermore, some of the data was actually the actors from the Harry Potter movies. Lastly, some nodes were groups of people, eg. Arthur Weasley's ten unidentified subordinates. We created an initial network to check the degree of the characters, to exclude characters with no links. To summarize, the following filters were applied to remove data:

* If blood status, house, species, death time and alias were all "None". Removed: ???? characters
* If name started with "unidentified". Removed: ???? characters
* If name was in a list of actors webscraped from [imdb](https://www.imdb.com/title/tt0241527/fullcredits#cast). Removed: ???? characters
* If the species was "Humans" indicating that the entry was a group. Removed: ???? characters
* If character has degree 0 in the network. Removed: ??? characters

After these filters, the data consisted of ???? characters.

## **Visualization of data**
To gain insight into the data we have created a few visualizations. Firstly, we see that the data is mostly populated by humans, however there are many species represented in the data set. The total number of different species is 182. The distribution of the top species and a wordcloud showing the different species can be seen below.

<table>
<tr><td>

| Top 5 Species  | Count |
|---|---|
| Human | ??? |
| Goblin | ??? |
| House-elf | ??? |
| Human (formerly), Ghost | ??? |
| Giant | ??? |

</td><td>

<img src="/images/species_wordcloud.png"     />

</td></tr> </table>
<i>Figur ???. The count of the top species and a wordcloud, where the size of a species represents the count. The size of the words are not linearly scaled, as "Human" would then be the only visible word.</i>

Humans is clearly the largest species, which makes a lot of sense for the universe. However in the wordcloud, it is clear that a lot of different species exist in the universe and a lot of them are fictional species. 

In the Harry Potter books and movies, the division of characters into houses at the British school for magic, Hogwarts, is an important theme in the universe. We have plotted the distribution of characters into houses including three houses outside of Hogwarts. The characters are distributed among 8 houses. The plot only shows 7 houses, as the last one holds all characters whose 'House' attribute is empty (referred to as 'Unknown'). The 'Unknown' house has ???? characters and thereby is out of range compared to the other houses.

<img src="/images/houses_count.png"     />
<i>Figur ???. The count of the characters in each house. ??? characters are excluded as their house was unknown (None), meaning their past is unknown or they never went to a school.</i>

A clear tendency to see from the data is that houses 'Griffyndor' and 'Slytherin' holds the most members, approximately 250 and 225. This makes a lot of sense given that a main theme in the Harry Potter books and movies is the feud between these two houses. Furthermore, 'Hufflepuff' and 'Ravenclaw' are also represented well with around 150 characters each, whereas the 'non-Hogwarts' houses have very few members. This holds exactly with our expectation of the universe, as it is centered around Hogwarts.


1. Lorem ipsum dolor sit amet
1. Lorem ipsum dolor sit amet
1. Lorem ipsum dolor sit amet

> Nulla in justo hendrerit, tincidunt mauris et, porta est. Donec in leo vitae est ultrices dapibus id nec tortor. Maecenas ut ipsum eu nisl cursus facilisis scelerisque eu ex. Aliquam euismod elementum libero, at vehicula ipsum.
