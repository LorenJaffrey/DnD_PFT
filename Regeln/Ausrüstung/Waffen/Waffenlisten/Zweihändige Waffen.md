```dataview
TABLE schaden as "Schaden", schadensart AS "Schadensart", hände AS "Hände", gewicht AS "Gewicht", kosten as "Kosten"
FROM "_DnD/Ausrüstung/Waffen/Waffen"  AND #Waffe/Klasse/Nahkampfwaffe AND #Waffe/Größe/Großwaffe OR #Waffe/Größe/Langwaffe 
```