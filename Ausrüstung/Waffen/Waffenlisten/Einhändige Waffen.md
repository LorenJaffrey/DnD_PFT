```dataview
TABLE schaden as "Schaden", schadensart AS "Schadensart", größe AS "Größe"
FROM "_DnD/Ausrüstung/Waffen/Waffen" AND #Waffe/Größe/Einhandwaffe AND #Waffe/Klasse/Nahkampfwaffe AND #Waffe/Größe/Einhandwaffe OR #Waffe/Größe/Anderthalbhänder 
```