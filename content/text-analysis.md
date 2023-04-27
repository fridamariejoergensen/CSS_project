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


Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nam blandit lobortis turpis. Praesent porttitor, turpis eu posuere molestie, sem dolor scelerisque sapien, eu aliquet ante felis ac metus. Pellentesque semper ultricies urna. Aenean auctor, turpis ut convallis ultrices, eros tellus bibendum risus, eu varius velit ante et diam. In suscipit lorem orci, eu placerat nibh dignissim ut. Nullam consequat nisl dui, in ornare risus porttitor sed. Integer vitae nibh semper purus ultrices rutrum. Pellentesque non diam ornare, imperdiet elit a, tempus lacus. Suspendisse viverra euismod dapibus.