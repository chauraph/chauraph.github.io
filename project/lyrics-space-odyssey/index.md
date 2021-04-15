## Lyrics Space Odyssey
---
<sup>with Fengan Li, Hugo Enrique Montaño Castillo, Lars Magne Tungland, Martina Verna and Xin Wang</sup>

*Lyrics Space Odyssey* is a data storytelling project exploring the Million Song Dataset. It is composed of a series of visualizations, which all contribute to displaying different – but complementary - aspects of the same data. The project's objective is to provide a platform for audiences to explore the relationship between word choice of a lyric, song genre and popularity. In the end, audiences are given full autonomy to utilize the interactive exploratory tool for composing their own.

The Million Song Dataset is a freely available collection of audio features and metadata consisting of one million contemporary popular music tracks. As the Million Song Dataset core does not include metadata for genre and lyric, data fusion is completed with Tableau Prep to augment the target data from the MusixMatch Dataset and TagTraum Dataset.

The final narrative is divided into three conceptual chapters: **Describe**, **Explore**, **Create**.

## 1. Describe
---
### Lyrics and Word Co-occurrence Networks

A Gephi networks that present an introductory overview, showing a galaxy of edges and nodes: the audience here detects color clusters and perceives the complexity of the data, so that they wants to know more about them.

In the lyrics network, each nodes represent a song and an edge is encoded to represent two songs that have over 30% of vocabularies overlapped in their lyrics. The lyrics network is constructed in the light of genres, which shows interesting insight: rap (orange) stands out with a unique vocabulary field. 

<img src="1.png?raw=true"/>
 
AWS is employed to launch a Gephi instance for computing a network graph of million songs.

Moving onto the **Explore** section, the audience experience a descent from the galaxy of songs into songs and words level.

## 2. Explore
---
### Co-occurrence Packed Bubbles

The main principle behind this visualization is to display information at a glance. It aims at precise and intuitive presentation of the data.

#### General Display

This dashboard consists of two packed bubbles charts. On the left, there is a bag of words (BOW) where the words-to-explore are kept. On the right, there is a second packed bubbles chart which shows the co-occurrences of a selected word in the BOW. Each bubble is encoded with three variables consistent throughout the visualization: 
1) color : the most frequent music genre for a word
2) size : the popularity/uniqueness of a word, which is represented by computing tf-idf weight of a word
3) text : the word

<img src="2.png?raw=true"/>

#### Color Concern

The categorization of the words is encoded with different colors. The color palette responds to the distribution of words. Our analysis revealed that Rap was the genre with the biggest number of words, followed by R&B. And most importantly, these words were often used in all songs. Thus, Rap and R&B are encoded with low saturated colors: light grey and light blue, respectively. The opposite was done for the genres with a small number of words, for instance Blues and Jazz. These genres were encoded with highly saturated colors. The objective was to avoid scenarios like the one in the figure below, where Rap and R&B could lead to big areas of saturated color.

<img src="3.png?raw=true"/>

### Exemplar Song Analysis

This dashboard also follows the purpose of providing information at a glance. But now, regarding a song’s lyrics. In addition, a new concept is introduced: the egocentricity of a song.

#### General Display

This dashboard is built around two parts. On the left there is a packed bubbles chart like the one detailed in the previous section, representing the co-occurrences of words within a song. On the right, there is the scatter plot meter measuring the egocentricity of a song.

#### Egocentricity Meter

Allows the precise representation of an otherwise too abstract variable: pronoun usage. In our visualization each axis encodes a dimension of egocentrism. Horizontally, the relation between the first (I) and second (You) person singular. Vertically, the first person possessive, object pronoun and its plurals (me, my, we, our, us) compared with the second person possessive and third person singulars, plurals, possessives and object pronouns (your, he, his, him, she, her, they, their, them) . The more dominant a pronoun (or pronouns for the vertical axis), the further placement from the center.

<img src="4.png?raw=true"/>

### Yearly Ego Position

This dashboard emphasizes the aim of giving insights at a glance. This time the main objective is to contrast the egocentricity of the different music genres.

#### General Display

This dashboard is an elaborated version on the ego chart described before. Instead of positioning a unique song, in this chart the user discovers the ego positioning of a music genre as a whole. For this purpose, more variables were added to the basic ego chart: music genre, year, and number of songs for each year. To control the display of data, some filters were added: one for the genre and one for the years.

<img src="5.png?raw=true"/>


### 2. Assess assumptions on which statistical inference will be based

```javascript
if (isAwesome){
  return true
}
```

### 3. Support the selection of appropriate statistical tools and techniques

<img src="images/dummy_thumbnail.jpg?raw=true"/>

### 4. Provide a basis for further data collection through surveys or experiments

Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. 

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).
