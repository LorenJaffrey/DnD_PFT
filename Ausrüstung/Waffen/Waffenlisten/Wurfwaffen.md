```dataview
TABLE schadenFern as "Schaden", schadensartFern AS "Schadensart", range1 AS "Minimalreichweite", range2 AS "Grundreichweite", range3 AS "Maximalreichweite", händeFern AS "Hände"
FROM "_DnD/Ausrüstung/Waffen/Waffen" AND #Waffe/Klasse/Fernkampfwaffe/Wurfwaffe 
```