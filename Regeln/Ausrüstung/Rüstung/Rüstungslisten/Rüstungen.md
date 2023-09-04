---
aliases: Rüstung
---
```dataview
TABLE klasse AS "Klasse", rp AS "RP", sr AS "SR", dex_cap AS "Gesch. Cap", stärke AS "Stärke", eigenschaften AS "Eigenschaften", gewicht AS "Gewicht", kosten as "Kosten"
FROM #Rüstung
SORT klasse, rp
```