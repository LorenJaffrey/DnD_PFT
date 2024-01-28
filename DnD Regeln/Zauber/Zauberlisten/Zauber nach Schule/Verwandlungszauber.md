---
aliases:
- Verwandlung
---
# `=this.file.name`
Verändern die Eigenschaften oder Formen von Kreaturen und Gegenständen.

```dataview
TABLE grad AS "Grad", zeitaufwand AS "Zeitaufwand", reichweite AS "Reichweite", verbal AS "Verbal", geste AS "Geste", material AS "Material", dauer AS "Dauer", konzentration AS "Konzentration", ritual AS "Ritual", skalierbar AS "Skalierbar" 
FROM #Zauber/Schule/Verwandlung
SORT grad, file.name
```