---
Bewegung:
  Boden: 9
  Fliegen: 12
  Schwimmen: 3
  Klettern: 1.5
  Graben: 27
---
```dataviewjs
const movement = dv.current().Bewegung;
var string = "|  |  | \n | --- | --- |";
for (var key in movement) {
	if(movement[key] > 0) {
		if (string.length > 0) {
			string += " \n "
		}
	string += ("|  [[" + key + "]] | " + movement[key] + "m (" + movement[key]/1.5 + " Kästchen) |");
	}
}
dv.paragraph(string);
```

```dataviewjs
const movement = dv.current().Bewegung;
var string = "| a | b | \n | --- | --- |";
for (var key in movement) {
	if(movement[key] > 0) {
		if (string.length > 0) {
			string += "\n"
		}
	string += ("|  [[" + key + "]] | " + movement[key] + "m (" + movement[key]/1.5 + " Kästchen) |");
	}
}
dv.paragraph(string);
```


|           |                 |
| --------- | --------------- |
| [[Boden]] | 9m (6 Kästchen) |

## Michi

```dataviewjs
const movement = dv.current().Bewegung;
var string = "<table><thead><tr><th></th><th></th></tr></thead><tbody>";
for (var key in movement) {
	if (movement[key] > 0) {
		string += "<tr><td><a href='[[ " + key + " ]]'>" + key + "</a></td><td>" + movement[key] + "m (" + (movement[key] / 1.5) + " Kästchen)</td></tr>";
	}
}
string += "</tbody></table>";
dv.paragraph(string);

```

```dataviewjs
const movement = dv.current().Bewegung;
var string = "<table><thead><tr><th>a</th><th>b</th></tr></thead><tbody>";
for (var key in movement) {
    if (movement[key] > 0) {
        string += `<tr><td><a href='[[${key}]]'>${key}</a></td><td>${movement[key]}m (${(movement[key] / 1.5).toFixed(2)} Kästchen)</td></tr>`;
    }
}
string += "</tbody></table>";
dv.paragraph(string);

```
