```dataview
TABLE Schaden, Schadensart, Hände, Größe, Eigenschaften
FROM "_DnD/Ausrüstung/Waffen/Waffen" AND #Waffe/Art/Hiebwaffe 
SORT größe, file.name
```