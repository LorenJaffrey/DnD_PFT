```dataview
TABLE schaden as "Schaden", schadensart AS "Schadensart", hände AS "Hände", gewicht AS "Gewicht", kosten as "Kosten"
FROM "_DnD/Ausrüstung/Waffen/Waffenliste" AND #Waffe/Größe/Einhändig AND #Waffe/Klasse/Nahkampfwaffe  
```