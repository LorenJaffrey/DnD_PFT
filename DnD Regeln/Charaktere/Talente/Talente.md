---
aliases:
  - Talent
---
# `=this.file.name`

## Beschreibung
Jedes Talent kann nur einmal erlangt werden, außer im Talent steht Gegenteiliges.
Solltest du jemals die Voraussetzungen für ein Talent nicht mehr erfüllen, kannst du es so lange nicht nutzen, bis du diese wieder erfüllst.

## Übersicht

- [ ] #task Talente überarbeiten [priority:: highest]

```dataview
TABLE WITHOUT ID 
file.link AS "Talent", Stufe,Voraussetzungen, Wiederholbar, aliases AS "Alias"
FROM #Talent
SORT Stufe, file.name ASC
```