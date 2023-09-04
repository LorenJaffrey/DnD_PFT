---
aliases: Kriegswaffe
---
```dataview
TABLE schaden as "Schaden", schadensart AS "Schadensart", hände AS "Hände"
FROM "_DnD/Ausrüstung/Waffen/Waffen" AND #Waffe/Kategorie/Kriegswaffe 
```