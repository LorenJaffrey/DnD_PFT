---
aliases: 
- Talent
---
## Beschreibung
Jedes Talent kann nur einmal erlangt werden, außer im Talent steht Gegenteiliges.
Solltest du jemals die Voraussetzungen für ein Talent nicht mehr erfüllen, kannst du es so lange nicht nutzen, bis du diese wieder erfüllst.

## Übersicht

```dataview
TABLE Voraussetzungen, Stufe, Wiederholbar, aliases AS "Alias"
FROM #Talent
SORT file.name ASC
```