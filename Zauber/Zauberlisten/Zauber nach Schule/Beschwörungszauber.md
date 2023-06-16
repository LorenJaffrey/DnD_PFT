Transportieren Gegenstände oder Kreaturen von einem Ort an einen anderen.

```dataview
TABLE grad AS "Grad", zeitaufwand AS "Zeitaufwand", reichweite AS "Reichweite", verbal AS "Verbal", geste AS "Geste", material AS "Material", dauer AS "Dauer", konzentration AS "Konzentration", ritual AS "Ritual", skalierbar AS "Skalierbar" 
FROM #Zauber/Schule/Beschwörung
SORT grad, file.name
```