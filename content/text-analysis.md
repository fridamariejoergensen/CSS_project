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
        <td>
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
        <td>
    <tr>
     <tr>
        <td>Slytherin</td>
        <td>0.14980006740811735</td>
    <tr>
  </table>
  </div>



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

