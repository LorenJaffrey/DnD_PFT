---
aliases: 
- Hervorrufung
---

# `=this.file.name`
Manipulieren magische Energiequellen mit einer Vielzahl von Effekten. Manche erzeugen Feuerblitze, andere kanalisieren positive Energie um Wunden zu heilen.

```dataview
TABLE grad AS "Grad", zeitaufwand AS "Zeitaufwand", reichweite AS "Reichweite", verbal AS "Verbal", geste AS "Geste", material AS "Material", dauer AS "Dauer", konzentration AS "Konzentration", ritual AS "Ritual", skalierbar AS "Skalierbar" 
FROM #Zauber/Schule/Hervorrufung
SORT grad, file.name
```