---
aliases: Klasse, Klassen
---
# `=this.file.name`

| Klasse           | TW  | Hauptattribut                        | max. Rüstung | Zauberwirker | Art der Zauberei                           | Tank | Damage | Investigation | Exploration | Utility | Negotiation | Support |
| ---------------- | --- | ------------------------------------ | ------------ | ------------ | ------------------------------------------ |:----:|:------:|:-------------:|:-----------:|:-------:|:-----------:|:-------:|
| [[Barbar]]       | W12 | [[Stärke]]                           | mittelschwer | ---          |                                            |  A   |   A    |       D       |      D      |    D    |      D      |    D    |
| [[Barde]]        | W8  | [[Charisma]]                         | leicht       | Primary      | [[Arten der Zauberei#Bekannte Zauber]]     |  C   |   D    |       A       |      A      |    S    |      S      |    A    |
| [[Druide]]       | W8  | [[Weisheit]]                         | mittelschwer | Primary      | [[Arten der Zauberei#Vorbereitete Zauber]] |  B   |   C    |       B       |      S      |    A    |      C      |    A    |
| [[Hexenmeister]] | W8  | [[Charisma]]                         | leicht       | Primary      | [[Arten der Zauberei#Bekannte Zauber]]     |  D   |   A    |       B       |      B      |    B    |      A      |    C    |
| [[Kämpfer]]      | W10 | [[Stärke]] oder [[Geschicklichkeit]] | schwer       | ---          |                                            |  A   |   S    |       D       |      D      |    D    |      D      |    D    |
| [[Kleriker]]     | W8  | [[Weisheit]]                         | mittelschwer | Primary      | [[Arten der Zauberei#Vorbereitete Zauber]] |  B   |   B    |       B       |      D      |    A    |      B      |    S    |
| [[Magier]]       | W6  | [[Intelligenz]]                      | ---          | Primary      | [[Arten der Zauberei#Vorbereitete Zauber]] |  D   |   B    |       S       |      B      |    S    |      C      |    B    |
| [[Magieschmied]] | W8  | [[Intelligenz]]                      | mittelschwer | Secondary    | [[Arten der Zauberei#Vorbereitete Zauber]] |  B   |   B    |       A       |      C      |    B    |      D      |    A    |
| [[Mönch]]        | W8  | [[Geschicklichkeit]] & [[Weisheit]]  | ---          | ---          |                                            |  C   |   B    |       D       |      C      |    C    |      D      |    D    |
| [[Paladin]]      | W10 | [[Stärke]] & [[Charisma]]            | schwer       | Secondary    | [[Arten der Zauberei#Vorbereitete Zauber]] |  S   |   A    |       D       |      D      |    C    |      B      |    A    |
| [[Schurke]]      | W8  | [[Geschicklichkeit]]                 | leicht       | ---          |                                            |  C   |   A    |       A       |      S      |    A    |      A      |    D    |
| [[Waldläufer]]   | W10 | [[Geschicklichkeit]] & [[Weisheit]]  | mittelschwer | Secondary    | [[Arten der Zauberei#Bekannte Zauber]]     |  C   |   A    |       B       |      A      |    B    |      D      |    C    |
| [[Zauberer]]     | W6  | [[Charisma]]                         | ---          | Primary      | [[Arten der Zauberei#Bekannte Zauber]]     |  D   |   B    |       B       |      B      |    B    |      A      |    B    |


---


``` dataview
TABLE Art, Trefferwürfel, Hauptattribut, Zauberwirker
FROM #Klasse
SORT file.name
```