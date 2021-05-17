## Paper Swordsmen in the Web
---

With enterprises across movies, fiction, video game, and licensed merchandise, fictional “universes” such as the Marvel Universe are important market forces of our economy as well as an immerse system of narrative elements and signification.

The *Transmedia Fictional Worlds Ontology* (TFWO) developed by the GAMER Research Group at the University of Washington is an ontology that attempted to model two things.

1. Economically, it models the complex relation among creative works (individual stories, meta-storylines, adaptations) and agents (creators, contributors, copyright owners, and fans) of the transmedia fictional world system.

2. Culturally, it models the system of narrative elements and signification which drive the storylines.

Developed with materials from western creative works, namely Harry Potter, the Marvel Universe, Lord of the Rings, and Star Wars, TFWO is questionably geographically limited. *Paper Swordsmen in the Web* took the case of Jin Yong’s Wuxia Universe, a martial art fictional world created by the greatest Hong Kong novelist ever since the 1950s, to test the general applicability of TFWO.

## Specification of TFWO
---

TFWO is an OWL 2.0 model serialized in the RDF-XML format with 72 classes and 239 properties.

One of the design principles of TFWO is to be interoperable with relevant ontologies. Therefore, TFWO has imported four relevant ontologies, namely

1. Schema.org (for root classes)

2. Comic Book Ontology

3. Ontology of Astronomical Object Types Version 1.3 (for intergalactic / Sci-fi works)

4. SKOS (for management concepts).

## Research Methodology and Material
---

### Domain Analysis 

Two major sources of material are consulted for domain analysis.

1. The author of this paper who is also a fan of Jin Yong’s wuxia fiction. The author is particularly familiar with the *Condor Trilogy*, *Demi- Gods and Semi-Devils*, and *The Smiling, Proud Wanderer*.

2. Fan-driven sites, wikis, and databases as well as the relevant Wikipedia and Wikidata pages. These sources provided excellent ready-made classification (such as place, martial art types, and characters), description, and English translation of narrative elements with examples.

### Encoding

The result of domain analysis is then translated and entered into spreadsheet set out by Branch et al. Hundreds of classes and properties are created and subjected to comparison with the vocabularies in TFWO.

During the comparison process, nuances and differences between wuxia fiction elements and TFWO vocabularies are documented with the concept from SKOS (Simple Knowledge Organization System), namely board match, exact match, narrower match, related match, and close match.

### RDFS Conversion Test

After the coding stage, the theoretical data model is experimented in [Protégé](https://protege.stanford.edu/).

### Encoding Concern

To aggregate fictional worlds across culture and medium, the encoding sought to instantiate culturally specific terms with generic concept. (e.g. Yin and Yang as an individual / instance of Negative and Positive Energy)

## Result
---

### Encoding Example

[![Image](1.jpg)](1.jpg)

Representation of *Heaven and Earth Great Shift* (fictional martial art skill).

[![Image](2.jpg)](2.jpg)

Representation of *Five Elements Fists* (martial art skill created using an alternate version of real thing).

[![Image](3.jpg)](3.jpg)

Crosslinking fictional universe by a proxy parent class *Air*. The *Force* in Star Wars has been viewed as an inspiration of the martial art *Qi* in many *fans interpretation*.

[![Image](4.jpg)](4.jpg)

Representation of copyright and authorship metadata of Jin Yong's fictional universe. 

[![Image](5.jpg)](5.jpg)

Knowledge graph expanded from intercultural lovers Zhang Wuji (Han Chinese) and Zhao Min (Mongol). The graph positioned elements according to the geolocation of  'real things': To the west: Persian cluster. To the North: Mongol cluster. To the South: Han cluster.
