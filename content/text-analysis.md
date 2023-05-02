---
title: Text analysis
prev: network-analysis
---

The text used for the text analysis were collected from Harry Potter character fandom wiki-pages. By going to the webpage for the desired character, looking for the main text on the page, and then gathering all of that text together into one long string. We skip over any irrelevant information, like tables or lists, and only collect the main text. The infobox that is present on all character pages is still included. 




The shortest wiki text is 126 characters (with spaces) and belongs to the character Oakden Hernshaw. The site contains the short description "Oakden Hernshaw was a wizard." a long with some sparse information about species and gender in the infobox. The longest wiki text is of length 285806 and is, not surprisingly, the one about Harry Potter. The distribution of the wiki texts can be seen below.

<img src="/images/Distribution_wiki_text.png"     />

> The average length of a wiki text is 4486 characters (with spaces) and the median is 1004. For reference 4,500 characters is between 642 words and 1125 words.

In order to do various natural language processing(NLP) tasks, we start by tokenizing the text. We do this by removing URLs, punctuation marks, numbers, stopwords, and other unwanted tokens, in order to reduce their impact and to return a list of cleaned tokens that can be used for further NLP analysis. The distribution of the tokenized wiki texts can be seen below. 

<img src="/images/Distribution_wiki_text_tokenized.png"     />

> The average length of the tokenized wiki texts is 405.92

<img src="/images/House_wordclouds.png"     />


| Top 10 words for Gryffindor  | TF-IDF Score |
|---|---|
| harry | 0.5861462680076663 |
| ron | 0.2347650556979932 |
| hogwarts | 0.22301403005913825 |
| hermione | 0.22199220174271608 |
| dumbledore | 0.1720503427775826 |
| weasley | 0.1438223355364202 |
| year | 0.14011820788938983 |
| school | 0.13564770900504286 |
| potter | 0.13168812427890694 |
| voldemort | 0.11661615661167997 |


| Top 10 words for Slytherin  | TF-IDF Score |
|---|---|
| harry | 0.3269527068515053 |
| voldemort | 0.2878410851562119 |
| black | 0.23671478228654724 |
| hogwarts | 0.23543662471480561 |
| snape | 0.2165198926530297 |
| death | 0.18967858364645576 |
| draco | 0.16743864189815166 |
| family | 0.1633485376685785 |
| school | 0.15414580315203885 |
| slytherin | 0.14980006740811735 |


| Top 10 words for Hufflepuff  | TF-IDF Score |
|---|---|
| newt | 0.31767164296338185 |
| harry | 0.27576602197672295 |
| hogwarts | 0.27509012486403495 |
| school | 0.21966656162361511 |
| year | 0.20141733958103786 |
| hufflepuff | 0.16491889549588334 |
| jacobs | 0.15883582148169093 |
| penny | 0.15613223303093873 |
| tonks | 0.1541045416928746 |
| sibling | 0.15207685035481047 |


| Top 10 words for Ravenclaw  | TF-IDF Score |
|---|---|
| harry | 0.41612785521950924 |
| hogwarts | 0.28492216362015854 |
| school | 0.26241138319870133 |
| year | 0.21031500565190034 |
| luna | 0.19680853739902598 |
| ravenclaw | 0.17108193120307488 |
| potter | 0.14599849016202254 |
| lockhart | 0.1414963340777311 |
| professor | 0.13763734314833845 |
| students | 0.12863303097975556 |



Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam blandit lobortis turpis. Praesent porttitor, turpis eu posuere molestie, sem dolor scelerisque sapien, eu aliquet ante felis ac metus. Pellentesque semper ultricies urna. Aenean auctor, turpis ut convallis ultrices, eros tellus bibendum risus, eu varius velit ante et diam. In suscipit lorem orci, eu placerat nibh dignissim ut. Nullam consequat nisl dui, in ornare risus porttitor sed. Integer vitae nibh semper purus ultrices rutrum. Pellentesque non diam ornare, imperdiet elit a, tempus lacus. Suspendisse viverra euismod dapibus.