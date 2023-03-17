# P3 Model

[![CC BY-NC-SA 4.0][cc-by-nc-sa-shield]][cc-by-nc-sa]

P3 Model is a tool to navigate throughout complex software systems from all important perspectives at all level of details for everyone involved in system development including nontechnical people.

## Introduction

As Eric Evans says *software development is all design*. Good design must be based on knowledge about the domain and current solution. Thus we need tools that give us deep and always up-to-date insight into our system in all important aspects. Unfortunately traditional system documentation are rarely up-to-date, accurate and complete so can give us such insight. 

**P3 Model** is named from **three main perspectives** from which we can look at the software system:

- **domain**
- **technology**
- **people**

**Technical concerns are not enough to design and maintain software system.** Thus we need to add date about domain model and people working on the system and all relations between elements from this three perspectives. Only such a combination of data give us accurate enough insight.

**To gather all important information about software system we need some structure.** P3 Model is also an attempt to standardize main modeling, architecture and design concepts to allow gathering information in a precise form. This standardization doesn't mean reinventing the wheel but only providing some high level structure in which we can fit existing and future patterns.

**Source code of the software system contains a lot of information** about architecture and domain model **but not all that is needed** to understand in deeply in all aspects. Thus **we need to add metadata** about:

- business concepts not represented directly in the code (e.g. domain model boundaries, processes, etc.)
- intent to use architecture or design patterns
- rationale of design decisions
- people responsible for maintenance and development of certain parts of the system
- etc.

**Given this metadata we can generate valuable documentation directly from the source code.** It's always up-to-date so it can be reliable source of truth about domain model and it's implementation. **This is next generation living documentation** that we are waiting for so long.

**Based on data gathered in P3 Model we can build visual representation** of the system understandable for people with different competences including nontechnical people. This shared representation can give us real boost in design work and gathering feedback from everyone involved in development process.

## Ecosystem

**P3 Model**

P3 Model is a set of abstraction that standardized the way we gather information about software system including domain, technology and people.

This set of abstractions and data scheme based on it is technology independent.

**Source code parsers and metadata**

Parser reads source code augmented with metadata and produces and outputs elements and its relations in accordance with P3 Model.

Parser and annotations are specific for programming language. 

Our goal is to provide libraries with annotations and parsers for most popular programming languages.

**Visualization tools**

Visualization tools transforms P3 Model data for given system to visual and interactive representation. 

P3 Model is independent of any visualization tool. It can be standalone tool or IDE plugin.

Our goal is to provide such a tool something like Google Maps for software systems. Third parties can also create other tools based on P3 Model date provided by parsers.

## FAQ

jakie były inspiracje: living documentation (Cirille), architecture views & beyond (SEI), C4, interactive maps

dlaczego Living Documentation: zapewnienie aktualności; w drugą stronę się nie da

dlaczego nie C4: tylko perspektywa techniczna

dlaczego nie UML: tylko perspektywa techniczna, nie nadaje się dla osób nietechnicznych, brak interaktywności

czy jest zależny od języka programowania: sam model nie, dzięki oddzieleniu metadanych i parsera od modelu, a modelu od wizualizacji

## Contribution

Join us and help building P3 Model. Let's solve the problem of outdated and useless documentation together.


## License

This work is licensed under a
[Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License][cc-by-nc-sa].

[![CC BY-NC-SA 4.0][cc-by-nc-sa-image]][cc-by-nc-sa]

[cc-by-nc-sa]: http://creativecommons.org/licenses/by-nc-sa/4.0/
[cc-by-nc-sa-image]: https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png
[cc-by-nc-sa-shield]: https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg

