---
aliases: Armbrust, Armbrüsten
---
```dataview
TABLE schaden as "Schaden", schadensart AS "Schadensart", grundreichweite AS "Grundreichweite", maximalreichweite AS "Maximalreichweite", hände AS "Hände", gewicht AS "Gewicht", kosten as "Kosten"
FROM "_DnD/Ausrüstung/Waffen/Waffenliste" AND #Waffe/Gruppe/Armbrust
```