## Lyrics Space Odyssey
---
<sup>with Fengan Li, Hugo Enrique Montaño Castillo, Lars Magne Tungland, Martina Verna and Xin Wang</sup>

*Lyrics Space Odyssey* is a data storytelling project exploring the Million Song Dataset. It is composed of a series of visualizations, which all contribute to displaying different – but complementary - aspects of the same data. The project's objective is to provide a platform for users to explore the relationship between word choice of a lyric, song genre and popularity. In the end, users are given full autonomy to utilize the interactive exploratory tool for composing their own.

The Million Song Dataset is a freely available collection of audio features and metadata consisting of one million contemporary popular music tracks. As the Million Song Dataset core does not include metadata for genre and lyric, data fusion is completed with Tableau Prep to augment the target data from the MusixMatch Dataset and TagTraum Dataset.

The final narrative is divided into three conceptual chapters: **Describe**, **Explore**, **Create**.

## 1. Describe
---
### Lyrics and Word Co-occurrence Networks

A Gephi networks that present an introductory overview, showing a galaxy of edges and nodes: the user here detects color clusters and perceives the complexity of the data, so that they wants to know more about them.

In the lyrics network, each nodes represent a song and an edge is encoded to represent two songs that have over 30% of vocabularies overlapped in their lyrics. The lyrics network is constructed in the light of genres, which shows interesting insight: rap (orange) stands out with a unique vocabulary field. 

<img src="1.png?raw=true"/>
 
AWS is employed to launch a Gephi instance for computing a network graph of million songs.

Moving onto the **Explore** section, the user experience a descent from the galaxy of songs into songs and words level.

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

<img src="4.png?raw=true"/>

#### Egocentricity Meter

Allows the precise representation of an otherwise too abstract variable: pronoun usage. In our visualization each axis encodes a dimension of egocentrism. Horizontally, the relation between the first (I) and second (You) person singular. Vertically, the first person possessive, object pronoun and its plurals (me, my, we, our, us) compared with the second person possessive and third person singulars, plurals, possessives and object pronouns (your, he, his, him, she, her, they, their, them) . The more dominant a pronoun (or pronouns for the vertical axis), the further placement from the center.

### Yearly Ego Position

This dashboard emphasizes the aim of giving insights at a glance. This time the main objective is to contrast the egocentricity of the different music genres.

#### General Display

This dashboard is an elaborated version on the ego chart described before. Instead of positioning a unique song, in this chart the user discovers the ego positioning of a music genre as a whole. For this purpose, more variables were added to the basic ego chart: music genre, year, and number of songs for each year. To control the display of data, some filters were added: one for the genre and one for the years.

<img src="5.png?raw=true"/>

#### Shape

To keep the theme in the exploratory chapter, the shapes in this scatter plot are circles. This capitalizes on the pre-attentive processing from the previous visualizations. The user remains clustering circles of same color. But in contrast to the previous charts, now they finds a circle for each year-genre combination.

#### Size

The major novelty in this chart is the association of the circles’ size to the number of songs. 

#### Interaction

There are two filters for the exploration of the different genres. The filter controlling the years is a sliding filter, this allows for an easy selection of different ranges of years. For controlling the display of specific genres there is a selectable list. This allows a controlled selection of the genres; the user can easily see which genres are currently displayed and which ones are omitted.

<img src="6.png?raw=true"/>

## 3. Create
---
### Create Your Own Lyrics

An exploration environment and a lyrics creation application

#### Design Concern

The guiding principle is to find a balance between level of details and cognitive burden to a user. New knowledge a user needs to acquire when using the application includes, parts of speech (POS), song genre, popularity-uniqueness, and the connection metaphor. Thus, a considerable effort has been devoted to simplifying UI/UX to encourage the user to ‘explore and create’.

#### General Display

1.	Mega Bubble Chart: Located on the left of the dashboard, it renders all the word appeared in the Million Songs Dataset. User can see the detail of a word bubble via tooltip and choose a word of interest by clicking it.

2.	Connection Bubble Chart: Located on the right of the dashboard, it renders the chosen word and its connected words.

<img src="7.png?raw=true"/>

#### Wildcard Filtering

User is allowed to search a word from the mega bubble chart to explore word connection. Wildcard filtering is used in which a user may feel that he/she is progressively navigating in the word bubbles. This is to immerse the user in the meta-narrative of ‘Lyrics Space Odyssey’.

<img src="8.png?raw=true"/>

#### Relation between nodes

The bubble chart is a representation of a ‘origin-edge’ relation in which the chosen word is the departure point (origin) and the connected words are edges. The relation is realized by always positioning the chosen word (colored in navy blue) at the center.

<img src="9.png?raw=true"/>

#### Exploring Word Connection

Clicking any word bubble in the dashboard will trigger the connection bubble chart to display its word connections. To encourage users to explore word connections, the interaction is designed to be as fluid as possible. The main issue is that it is easy for users to lose their whereabout after exploring a few rounds

The problem is addressed by taking advantage of pre-attentive processing. First, we added the chosen word in the connection bubble chart and colored it in navy blue. It is based on the fact that our brain can quickly detect object with distinctive coloring. Second, we instructed Tableau to always position the chosen word at the center. It is based on the cultural phenomenon that centrality tends to have a special status. Third, we made use of the highlighting function. Once a user selects another word to trigger the re-render of the connection bubble chart, the newly chosen word will be highlighted. We discovered that our brain can quickly learn the paradigm and the connection bubble chart is made self-explanatory. The value of this more fluid version is that it encourages the user to make more connection exploration. This aligns will our meta-narrative of ‘lyric space odyssey’.

<img src="10.png?raw=true"/>

#### Panning Popularity-Uniqueness

User can to pan across the Popularity-Uniqueness spectrum with a toggle and learn the relative popularity or uniqueness of the chosen word by comparing with its connected word.

<img src="11.png?raw=true"/>

#### Lyric Composer, Genre Switch

User can use the lyric composer to compose lyric. Action available includes add word, backspace and reset. Lyric composer is a Node.js app embed as a web object in Tableau Dashboard. Word collected in the lyric composer can be retrieved again as a data source of Tableau. Additional analysis of the created lyric is possible though it is not implemented in the scope of this project.

Genre switch allow user to navigate to the word connections of songs from another genre. By default, clicking a word bubble will show the word connections in the reprehensive genre of the chosen word.

<img src="12.png?raw=true"/>

### Hot Song Titles Chord Diagram

Assist users to name hit song title with inspiration from the hottest existing songs.

#### General Display

Each node represents a word which is used in a song title. Each edge represents a pair of words which are used together in a song title. The size of each node represents the relatively popularity of the word. The magnitude of the linkage (occurrences of each word pair in all song titles) is shown as a tooltip.

<img src="13.png?raw=true"/>

#### Hotties and Notties

Two chord diagrams representing hot song titles and bottom-ranked song titles are presented to the user. By starting from one word and following the arcs to the next and the next, users can build new song titles.
