# P3 Model

[![CC BY-SA 4.0][cc-by-sa-shield]][cc-by-sa]

P3 Model is a structured and technology-independent model that standardizes the way software systems are described and documented.

P3 Model is named from **three main perspectives** from which we can look at the software system:

- *Domain* - what business concepts are implemented in the system
- *Technology* - what technical solutions are used to run the system
- *People* - how people develop, maintain and use the system

## Introduction

As Eric Evans says *software development is all design*. Good design must be based on knowledge about the domain and current  solution. Thus we need simple but expressive enough model to describe and document software systems.

**Technical concerns are not enough to design and maintain software system.** Thus we need to add date about domain model and people working on the  system and all relations between elements from this three perspectives. Only such a combination of data give us accurate enough insight.

**To gather all important information about software system we need some structure.** P3 Model is an attempt to standardize main modeling, architecture  and design concepts to allow gathering information in a precise form. This standardization doesn't mean reinventing the wheel but only providing some high level structure in which we can fit existing and future patterns.

**Check out [P3 Elements](https://github.com/P3-model/P3-model/blob/main/Elements.md)** that defines this structure and all key terms.

## FAQ

**Why not C4 Model?**

Because it contains only a part of technology perspective. We believe that broader approach is needed for documentation that  support design and maintenance of software systems.

**Why not UML?**

Because UML is a diagram notation, not the model. We  believe that creating views based on shared model is more flexible  approach. Of course UML can be used to generate some views on top on P3  model data.


## License

This work is licensed under a
[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].

[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg

