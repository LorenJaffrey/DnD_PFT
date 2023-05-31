---
aliases: Einfache Waffe, Einfachen Waffe, Einfachen Waffen
---
```dataview
TABLE schaden as "Schaden", schadensart AS "Schadensart", hände AS "Hände", gewicht AS "Gewicht", kosten as "Kosten"
FROM "_DnD/Ausrüstung/Waffen/Waffenliste" AND #Waffe/Kategorie/Einfache_Waffe
```