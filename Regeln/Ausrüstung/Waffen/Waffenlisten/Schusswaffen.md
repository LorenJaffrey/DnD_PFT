```dataview
TABLE schaden as "Schaden", schadensart AS "Schadensart", mindestreichweite AS "Mindestreichweite", grundreichweite AS "Grundreichweite", maximalreichweite AS "Maximalreichweite", hände AS "Hände"
FROM "_DnD/Ausrüstung/Waffen/Waffen" AND #Waffe/Klasse/Fernkampfwaffe/Schusswaffe 
SORT file.name ASC
```