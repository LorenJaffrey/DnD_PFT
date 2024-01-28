---
aliases:
- Verzauberung
---
# Verzauberungen
Beeinflussen den Verstand einer anderen Person und manipulieren oder kontrollieren ihr Verhalten.

```dataview
TABLE grad AS "Grad", zeitaufwand AS "Zeitaufwand", reichweite AS "Reichweite", verbal AS "Verbal", geste AS "Geste", material AS "Material", dauer AS "Dauer", konzentration AS "Konzentration", ritual AS "Ritual", skalierbar AS "Skalierbar" 
FROM #Zauber/Schule/Verzauberung
SORT grad, file.name
```