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

# **Filtering the data**
The original data set consisted of 4066 characters. However, some of the characters had little or no information attached. We concluded that if we had no information about a character or if their name included "unidentified", they were not relevant for the network. Furthermore, some of the data was actually the actors from the Harry Potter movies. Lastly, some nodes were groups of people, eg. "Arthur Weasley's ten unidentified subordinates". We created an initial network to check the degree of the characters, to exclude characters with no links. To summarize, the following filters were applied to remove data:

* If blood status, house, species, death time and alias were all "None". Removed: 91 characters
* If name started with "unidentified". Removed: 431 characters
* If name was in a list of actors webscraped from [imdb](https://www.imdb.com/title/tt0241527/fullcredits#cast). Removed: 4 characters
* If the species was "Humans" indicating that the entry was a group. Removed: 56 characters
* If character has degree 0 in the network. Removed: 1731 characters

After these filters, the data consisted of 1751 characters.

# **Visualization of data**
## **Species**
To gain insight into the data we have created a few visualizations. Firstly, we see that the data is mostly populated by humans, however there are many species represented in the data set. The total number of different species is 182. The distribution of the top species and a wordcloud showing the different species can be seen below.

<table>
<tr><td>

| Top 5 Species  | Count |
|---|---|
| Human | 1518 |
| Ghost, Human (formerly) | 16 |
| Goblin | 10 |
| House-elf | 9 |
| Giant | 9 |

</td><td>

<img src="/images/species_wordcloud.png"     />

</td></tr> </table>
<i>Figure 1. The count of the top species and a wordcloud, where the size of a species represents the count.</i>

Humans is clearly the largest species, which makes a lot of sense for the universe. However in the wordcloud, it is clear that a lot of different species exist in the universe and a lot of them are fictional species. Nevertheless, the size of the words are not linearly scaled, as "Human" would then be the only visible word.
## **Houses**
In the Harry Potter books and movies, the division of characters into houses at the British school for magic, Hogwarts, is an important theme in the universe. We have plotted the distribution of characters into houses including three houses outside of Hogwarts. The characters are distributed among 8 houses. The 'Unknown' house holds all characters whose 'House' attribute was None.

<iframe id="igraph" scrolling="no" style="border:none;" seamless="seamless" src="https://plotly.com/~s204052/1.embed" height="425" width="100%"></iframe>
<i>Figure 2. The count of the characters in each house.</i>

A clear tendency to see from the data is that besides the unknown house category, the houses 'Griffyndor' and 'Slytherin' holds the most members, approximately 100 and 120. This makes a lot of sense given that a main theme in the Harry Potter books and movies is the feud between these two houses. Furthermore, 'Hufflepuff' and 'Ravenclaw' are also represented well with around 60 characters each, whereas the 'non-Hogwarts' houses have very few members. We expected to see a larger fraction of characters in the 'Hogwarts' houses, but the 'Unknown' category is very dominant. It does however match our expectation that 'non-Hogwarts' houses have so few characters, as the universe is centered around Hogwarts.


## **Gender**
As we know the majority of the characters are humans, it makes sense to look at the gender distribution of the data. We have plotted the genders below. There is a clear majority of males in the data set. The mixed category describes groups of both males and females as our filters above missed a few groups like 'Hogwarts house-elves' and 'Hogwarts house-mice'. This was discovered too late in the project to account for. However, it is only 8 data entries that have the 'Mixed' gender and they still function as nodes with references to other characters, so it does not affect the rest of our analysis.

<iframe id="igraph" scrolling="no" style="border:none;" seamless="seamless" src="https://plotly.com/~s204052/4.embed" height="425" width="100%"></iframe>
<i>Figure 3. The count of the genders in the data set.</i>


