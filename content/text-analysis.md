---
title: Text analysis
prev: network-analysis
---

The text used for the text analysis were collected from Harry Potter character fandom wiki-pages. By going to the webpage for the desired character, looking for the main text on the page, and then gathering all of that text together into one long string. We skip over any irrelevant information, like tables or lists, and only collect the main text. The infobox that is present on all character pages is still included. 




The shortest wiki text is 126 characters (with spaces) and belongs to the character Oakden Hernshaw. The site contains the short description "Oakden Hernshaw was a wizard." a long with some sparse information about species and gender in the infobox. The longest wiki text is of length 285806 and is, not surprisingly, the one about Harry Potter. The distribution of the wiki texts can be seen below.

<img src="/images/Distribution_wiki_text.png" />

> The average length of a wiki text is 4486 characters (with spaces) and the median is 1004. For reference 4,500 characters is between 642 words and 1125 words.

Becuase the distribution is so left skewed plotting it in log-scale helps with the visualization:

<img src="/images/Distribution_wiki_text_ls.png" />


In order to do various natural language processing(NLP) tasks, we start by tokenizing the text. We do this by removing URLs, punctuation marks, numbers, stopwords, and other unwanted tokens, in order to reduce their impact and to return a list of cleaned tokens that can be used for further NLP analysis. The distribution of the tokenized wiki texts can be seen below. 

<img src="/images/Distribution_wiki_text_tokenized.png"     />

> The average length of the tokenized wiki texts is 405.92 characters (with spaces). So the average length has been reduced with a factor of 10 by tokenization.

And the distribution plotted in log-scale:
<img src="/images/Distribution_wiki_text_tokenized_ls.png" />

It makes sense that that tokenizing the text drastically reduced the amount of words, as Wikipedia articles often are written in a very formal style and aim to provide comprehensive and neutral information on a particular topic. As a result, they often contain a lot of common and generic words known as stopwords. By tokenizing the text we also remove things such as punctuation, numbers, and special characters, which also plays a part in the reduction.

Now we would like to find out which words charecterize the house communities. For this purpose we calculate the TF-IDF scores on the tokenized wiki-texts. When calculating the TF-IDF score, the term frequency is weighted by the inverse document frequency. Tokens with high scores are typically more specific to the community and used less frequently in general. These scores help us identify words that distinguish communities, providing insight into what makes each community unique. Below are shown wordclouds for the four main houses of Hogwarts "Gryffindor", "Slytherin", "Hufflepuff" & "Ravenclaw". The higher the TF-IDF score - the bigger the word. 

<img src="/images/House_wordclouds.png"     />

All four communities have the words “harry”, “hogwarts”, and “school” in their top 10 words, indicating that these words are important to all four communities, which makes sense since the whole universe and both movies and books are centered around the three subjects. The only house that doesn't have Harry as it's top TF-IDF word is Hufflepuff thas has the word "newt" instead. "newt" is short for "Newton Scamander" who is the main protagonist of the Fantastic Beasts film series. Since the house Hufflepuff does not play a significant role in the original Harry Potter universe and the Fantastic Beasts film series has been a huge spinoff, it isn't surprising that words from the expanded universe get to play a part in the house's wordcloud. In the tables below the top 10 words and scores for each house is presented.

<div style="display: flex; flex-wrap: wrap;">
  <div style="flex: 1; margin-right: 10px;">
    <table>
      <caption>Top 10 words for Gryffindor</caption>
      <tr>
        <th>Word</th>
        <th>TF-IDF Score</th>
      </tr>
      <tr>
        <td>harry</td>
        <td>0.5861462680076663</td>
      </tr>
      <tr>
        <td>ron</td>
        <td>0.2347650556979932</td>
      </tr>
      <tr>
        <td>hogwarts</td>
        <td>0.22301403005913825</td>
      </tr>
      <tr>
        <td>hermione</td>
        <td>0.22199220174271608</td>
      </tr>
      <tr>
        <td>dumbledore</td>
        <td>0.1720503427775826</td>
      </tr>
      <tr>
        <td>weasley</td>
        <td>0.1438223355364202</td>
      </tr>
      <tr>
        <td>year</td>
        <td>0.14011820788938983</td>
      </tr>
      <tr>
        <td>school</td>
        <td>0.13564770900504286</td>
      </tr>
      <tr>
        <td>potter</td>
        <td>0.13168812427890694</td>
      </tr>
      <tr>
        <td>voldemort</td>
        <td>0.11661615661167997</td>
      </tr>
    </table>
  </div>

  <div style="display: inline-block; vertical-align: top;">
    <table>
      <caption>Top 10 words for Slytherin</caption>
      <tr>
        <th>Word</th>
        <th>TF-IDF Score</th>
      </tr>
      <tr>
        <td>harry</td>
        <td>0.3269527068515053</td>
      </tr>
      <tr>
        <td>voldemort</td>
        <td>0.2878410851562119</td>
      </tr>
      <tr>
        <td>black</td>
        <td>0.23671478228654724</td>
      </tr>
      <tr>
        <td>hogwarts</td>
        <td>0.23543662471480561</td>
      </tr>
      <tr>
        <td>snape</td>
        <td>0.2165198926530297</td>
      </tr>
      <tr>
        <td>death</td>
        <td>0.18967858364645576</td>
      </tr>
      <tr>
        <td>draco</td>
        <td>0.16743864189815166</td>
      </tr>
      <tr>
        <td>family</td>
        <td>0.1633485376685785</td>
      </tr>
      <tr>
        <td>school</td>
        <td>0.15414580315203885</td>
    <tr>
     <tr>
        <td>Slytherin</td>
        <td>0.14980006740811735</td>
    <tr>
  </table>
  </div>


<div style="display: flex; flex-wrap: wrap;">
  <div style="flex: 1; margin-right: 10px;">
    <table>
      <caption>Top 10 words for Hufflepuff</caption>
      <tr>
        <th>Word</th>
        <th>TF-IDF Score</th>
      </tr>
      <tr>
        <td>newt</td>
        <td>0.31767164296338185</td>
      </tr>
      <tr>
        <td>harry</td>
        <td>0.27576602197672295</td>
      </tr>
      <tr>
        <td>hogwarts</td>
        <td>0.27509012486403495</td>
      </tr>
      <tr>
        <td>school</td>
        <td>0.21966656162361511</td>
      </tr>
      <tr>
        <td>year</td>
        <td>0.20141733958103786 </td>
      </tr>
      <tr>
        <td>hufflepuff</td>
        <td>0.16491889549588334</td>
      </tr>
      <tr>
        <td>jacobs</td>
        <td>0.15883582148169093</td>
      </tr>
      <tr>
        <td>penny</td>
        <td>0.15613223303093873</td>
      </tr>
      <tr>
        <td>tonks</td>
        <td>0.1541045416928746</td>
      </tr>
      <tr>
        <td>sibling</td>
        <td>0.15207685035481047</td>
      </tr>
    </table>
  </div>

  <div style="display: inline-block; vertical-align: top;">
    <table>
      <caption>Top 10 words for Ravenclaw</caption>
      <tr>
        <th>harry</th>
        <th>TF-IDF Score</th>
      </tr>
      <tr>
        <td>harry</td>
        <td>0.41612785521950924</td>
      </tr>
      <tr>
        <td>hogwarts</td>
        <td>0.28492216362015854</td>
      </tr>
      <tr>
        <td>school</td>
        <td>0.26241138319870133</td>
      </tr>
      <tr>
        <td>year</td>
        <td>0.21031500565190034</td>
      </tr>
      <tr>
        <td>luna</td>
        <td>0.19680853739902598</td>
      </tr>
      <tr>
        <td>ravenclaw</td>
        <td>0.17108193120307488</td>
      </tr>
      <tr>
        <td>potter</td>
        <td>0.14599849016202254</td>
      </tr>
      <tr>
        <td>lockhart</td>
        <td> 0.1414963340777311</td>
      </tr>
      <tr>
        <td>professor</td>
        <td>0.13763734314833845</td>
    <tr>
     <tr>
        <td>students</td>
        <td>0.12863303097975556</td>
    <tr>
  </table>
  </div>

We can also see some overall differences between the communities.

<p style="color:#7F0909;"> For example, Gryffindor’s top 10 words also include “ron”, “hermione”, “dumbledore”, and “weasley”. All characters associated with the Gryffindor house. Ron and Hermione are both Gryffindor students and friends of Harry, while Albus Dumbledore is the headmaster of Hogwarts and a former Gryffindor student aswell.
 The Weasley family is closely associated with the Gryffindor house, as it is said that the Weasleys are always assigned to the house by the sorting hat.</p>

<p style="color:#1A472A;">Slytherin’s top 10 words include “voldemort”, “black”, “snape”, and “draco”. Voldemort, also known as Tom Riddle, was a Slytherin student and the main antagonist of the series. Severus Snape was the Potions Master and Head of Slytherin house at Hogwarts. Draco Malfoy was a Slytherin student and Harry Potter’s rival. The Black family, including Sirius Black and Bellatrix Lestrange, were also closely associated with the Slytherin house. The word black could also be presenting more in this house document as a reference to dark/black magic, which is believed to be the evil/unethical kind of magic and Slytherin has historically been the most evil/unethical house.</p>

<p style="color:#FFC500;">Hufflepuff’s top 10 words include “jacobs”, "sibling", “penny”, and “tonks”. The words "penny" and "tonks" are also from the Fantastic Beasts universe. The words "jacobs sibling" is also within Hufllepuff's top 10."jacobs sibling" stems from the role-playing video game "Harry Potter: Hogwarts Mystery", where you create your own chareter and follow your brother Jacob around doing different magic quests. Beacuse the game is so long and complex, Jacobs Siblings wikipage is one of the longest ones, that we have webscraped.</p>

<p style="color:#0A5EA8;">Ravenclaw’s top 10 words include “luna”, “lockhart”, and “professor”.Luna was a Ravenclaw student, Gilderoy Lockhart was a former Ravenclaw student and Defense Against the Dark Arts professor at Hogwarts, and the word “Professor” may be associated with Ravenclaw due to the house’s reputation for valuing intelligence and academic achievement.</p>


It is also possible to make individual wordclouds for the charecters. We have chosen to generate one for each of the charecters that are on the list of top 10 charecters in term of indegree in our network graph. Because indegree tends to be a good indication of importance, as it means a high number of incoming connections from other characters in the network. Showing that the character is popular and influential within the network.


<img src="/images/Harry James Potter.png" />

<img src="/images/Ronald Bilius Weasley.png"     />

<img src="/images/Hermione Jean Granger.png"   />

<img src="/images/Tom Marvolo Riddle.png"     />

<img src="/images/Sirius Black III.png"     />

<img src="/images/Severus Snape.png"     />

<img src="/images/Arthur Weasley.png"     />

<img src="/images/Albus Dumbledore.png"  />

<img src="/images/Draco Lucius Malfoy.png"     />

<img src="/images/Ginevra Molly Potter (née Weasley).png"     />

