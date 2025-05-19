---
aliases:
tags:
---
# `=this.file.name`
```dataview
TABLE WITHOUT ID 
file.link AS "Talent", Stufe, Voraussetzungen, choice(Wiederholbar,"X","") AS "Wiederholbar", aliases AS "Alias"
FROM #Talent/Allgemein
SORT Stufe, file.name ASC
```