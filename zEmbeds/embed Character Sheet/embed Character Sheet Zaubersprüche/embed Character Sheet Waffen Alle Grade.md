## Zaubertricks
```dataviewjs
const diceRoller = (damage) => {
    // If damage is not defined, return a placeholder
    if (!damage) return "";
    // Otherwise, format it as a dice roller command
    return `\`dice: ${damage}|none|noform\``;
};

dv.table(
    ["Zauber", "Schule", "Zeitaufwand", "Schadensart", "Schaden ab Lv. 1", "Schaden ab Lv. 5", "Ziel", "Reichweite", "Verbal", "Geste", "Dauer", "Konzentration", "Ritual"],
    dv.pages("#Zauber")
      .where(p => p.Grad == 0 && dv.current().Zauber.some(link => link.path === p.file.path))
      .sort(p => p.file.name)
      .map(p => [
          p.file.link,
          p.Schule,
          p.Zeitaufwand,
          p.Schadensart,
          diceRoller(p.Schaden),   // Schaden as dice roller command
          diceRoller(p.SchadenLv5), // SchadenLv5 as dice roller command
          p.Ziel,
          p.Reichweite,
          p.Verbal ? "X" : "",
          p.Geste ? "X" : "",
          p.Dauer,
          p.Konzentration ? "X" : "",
          p.Ritual ? "X" : ""
      ])
);

// Apply CSS to center headers and column content
const table = this.container.querySelector("table");
table.style.width = "100%";

// Center align headers and table cells
const headers = table.querySelectorAll("th");
headers.forEach(header => header.style.textAlign = "center");

const cells = table.querySelectorAll("td");
cells.forEach(cell => cell.style.textAlign = "center");

```

## Grad 1
```dataviewjs
const diceRoller = (damage) => {
    // If damage is not defined, return a placeholder
    if (!damage) return "";
    // Otherwise, format it as a dice roller command
    return `\`dice: ${damage}|none|noform\``;
};

dv.table(
    ["Zauber", "Schule", "Zeitaufwand", "Schadensart", "Schaden", "Ziel", "Reichweite", "Verbal", "Geste", "Dauer", "Konzentration", "Ritual"],
    dv.pages("#Zauber")
      .where(p => p.Grad == 1 && dv.current().Zauber.some(link => link.path === p.file.path))
      .sort(p => p.file.name)
      .map(p => [
          p.file.link,
          p.Schule,
          p.Zeitaufwand,
          p.Schadensart,
          diceRoller(p.Schaden),   // Schaden as dice roller command
          p.Ziel,
          p.Reichweite,
          p.Verbal ? "X" : "",
          p.Geste ? "X" : "",
          p.Dauer,
          p.Konzentration ? "X" : "",
          p.Ritual ? "X" : ""
      ])
);

// Apply CSS to center headers and column content
const table = this.container.querySelector("table");
table.style.width = "100%";

// Center align headers and table cells
const headers = table.querySelectorAll("th");
headers.forEach(header => header.style.textAlign = "center");

const cells = table.querySelectorAll("td");
cells.forEach(cell => cell.style.textAlign = "center");

```

## Grad 2
```dataviewjs
const diceRoller = (damage) => {
    // If damage is not defined, return a placeholder
    if (!damage) return "";
    // Otherwise, format it as a dice roller command
    return `\`dice: ${damage}|none|noform\``;
};

dv.table(
    ["Zauber", "Schule", "Zeitaufwand", "Schadensart", "Schaden", "Ziel", "Reichweite", "Verbal", "Geste", "Dauer", "Konzentration", "Ritual"],
    dv.pages("#Zauber")
      .where(p => p.Grad == 2 && dv.current().Zauber.some(link => link.path === p.file.path))
      .sort(p => p.file.name)
      .map(p => [
          p.file.link,
          p.Schule,
          p.Zeitaufwand,
          p.Schadensart,
          diceRoller(p.Schaden),   // Schaden as dice roller command
          p.Ziel,
          p.Reichweite,
          p.Verbal ? "X" : "",
          p.Geste ? "X" : "",
          p.Dauer,
          p.Konzentration ? "X" : "",
          p.Ritual ? "X" : ""
      ])
);

// Apply CSS to center headers and column content
const table = this.container.querySelector("table");
table.style.width = "100%";

// Center align headers and table cells
const headers = table.querySelectorAll("th");
headers.forEach(header => header.style.textAlign = "center");

const cells = table.querySelectorAll("td");
cells.forEach(cell => cell.style.textAlign = "center");

```

## Grad 3
```dataviewjs
const diceRoller = (damage) => {
    // If damage is not defined, return a placeholder
    if (!damage) return "";
    // Otherwise, format it as a dice roller command
    return `\`dice: ${damage}|none|noform\``;
};

dv.table(
    ["Zauber", "Schule", "Zeitaufwand", "Schadensart", "Schaden", "Ziel", "Reichweite", "Verbal", "Geste", "Dauer", "Konzentration", "Ritual"],
    dv.pages("#Zauber")
      .where(p => p.Grad == 3 && dv.current().Zauber.some(link => link.path === p.file.path))
      .sort(p => p.file.name)
      .map(p => [
          p.file.link,
          p.Schule,
          p.Zeitaufwand,
          p.Schadensart,
          diceRoller(p.Schaden),   // Schaden as dice roller command
          p.Ziel,
          p.Reichweite,
          p.Verbal ? "X" : "",
          p.Geste ? "X" : "",
          p.Dauer,
          p.Konzentration ? "X" : "",
          p.Ritual ? "X" : ""
      ])
);

// Apply CSS to center headers and column content
const table = this.container.querySelector("table");
table.style.width = "100%";

// Center align headers and table cells
const headers = table.querySelectorAll("th");
headers.forEach(header => header.style.textAlign = "center");

const cells = table.querySelectorAll("td");
cells.forEach(cell => cell.style.textAlign = "center");

```

## Grad 4
```dataviewjs
const diceRoller = (damage) => {
    // If damage is not defined, return a placeholder
    if (!damage) return "";
    // Otherwise, format it as a dice roller command
    return `\`dice: ${damage}|none|noform\``;
};

dv.table(
    ["Zauber", "Schule", "Zeitaufwand", "Schadensart", "Schaden", "Ziel", "Reichweite", "Verbal", "Geste", "Dauer", "Konzentration", "Ritual"],
    dv.pages("#Zauber")
      .where(p => p.Grad == 4 && dv.current().Zauber.some(link => link.path === p.file.path))
      .sort(p => p.file.name)
      .map(p => [
          p.file.link,
          p.Schule,
          p.Zeitaufwand,
          p.Schadensart,
          diceRoller(p.Schaden),   // Schaden as dice roller command
          p.Ziel,
          p.Reichweite,
          p.Verbal ? "X" : "",
          p.Geste ? "X" : "",
          p.Dauer,
          p.Konzentration ? "X" : "",
          p.Ritual ? "X" : ""
      ])
);

// Apply CSS to center headers and column content
const table = this.container.querySelector("table");
table.style.width = "100%";

// Center align headers and table cells
const headers = table.querySelectorAll("th");
headers.forEach(header => header.style.textAlign = "center");

const cells = table.querySelectorAll("td");
cells.forEach(cell => cell.style.textAlign = "center");

```

## Grad 5
```dataviewjs
const diceRoller = (damage) => {
    // If damage is not defined, return a placeholder
    if (!damage) return "";
    // Otherwise, format it as a dice roller command
    return `\`dice: ${damage}|none|noform\``;
};

dv.table(
    ["Zauber", "Schule", "Zeitaufwand", "Schadensart", "Schaden", "Ziel", "Reichweite", "Verbal", "Geste", "Dauer", "Konzentration", "Ritual"],
    dv.pages("#Zauber")
      .where(p => p.Grad == 5 && dv.current().Zauber.some(link => link.path === p.file.path))
      .sort(p => p.file.name)
      .map(p => [
          p.file.link,
          p.Schule,
          p.Zeitaufwand,
          p.Schadensart,
          diceRoller(p.Schaden),   // Schaden as dice roller command
          p.Ziel,
          p.Reichweite,
          p.Verbal ? "X" : "",
          p.Geste ? "X" : "",
          p.Dauer,
          p.Konzentration ? "X" : "",
          p.Ritual ? "X" : ""
      ])
);

// Apply CSS to center headers and column content
const table = this.container.querySelector("table");
table.style.width = "100%";

// Center align headers and table cells
const headers = table.querySelectorAll("th");
headers.forEach(header => header.style.textAlign = "center");

const cells = table.querySelectorAll("td");
cells.forEach(cell => cell.style.textAlign = "center");

```

## Grad 6
```dataviewjs
const diceRoller = (damage) => {
    // If damage is not defined, return a placeholder
    if (!damage) return "";
    // Otherwise, format it as a dice roller command
    return `\`dice: ${damage}|none|noform\``;
};

dv.table(
    ["Zauber", "Schule", "Zeitaufwand", "Schadensart", "Schaden", "Ziel", "Reichweite", "Verbal", "Geste", "Dauer", "Konzentration", "Ritual"],
    dv.pages("#Zauber")
      .where(p => p.Grad == 6 && dv.current().Zauber.some(link => link.path === p.file.path))
      .sort(p => p.file.name)
      .map(p => [
          p.file.link,
          p.Schule,
          p.Zeitaufwand,
          p.Schadensart,
          diceRoller(p.Schaden),   // Schaden as dice roller command
          p.Ziel,
          p.Reichweite,
          p.Verbal ? "X" : "",
          p.Geste ? "X" : "",
          p.Dauer,
          p.Konzentration ? "X" : "",
          p.Ritual ? "X" : ""
      ])
);

// Apply CSS to center headers and column content
const table = this.container.querySelector("table");
table.style.width = "100%";

// Center align headers and table cells
const headers = table.querySelectorAll("th");
headers.forEach(header => header.style.textAlign = "center");

const cells = table.querySelectorAll("td");
cells.forEach(cell => cell.style.textAlign = "center");

```

## Grad 7
```dataviewjs
const diceRoller = (damage) => {
    // If damage is not defined, return a placeholder
    if (!damage) return "";
    // Otherwise, format it as a dice roller command
    return `\`dice: ${damage}|none|noform\``;
};

dv.table(
    ["Zauber", "Schule", "Zeitaufwand", "Schadensart", "Schaden", "Ziel", "Reichweite", "Verbal", "Geste", "Dauer", "Konzentration", "Ritual"],
    dv.pages("#Zauber")
      .where(p => p.Grad == 7 && dv.current().Zauber.some(link => link.path === p.file.path))
      .sort(p => p.file.name)
      .map(p => [
          p.file.link,
          p.Schule,
          p.Zeitaufwand,
          p.Schadensart,
          diceRoller(p.Schaden),   // Schaden as dice roller command
          p.Ziel,
          p.Reichweite,
          p.Verbal ? "X" : "",
          p.Geste ? "X" : "",
          p.Dauer,
          p.Konzentration ? "X" : "",
          p.Ritual ? "X" : ""
      ])
);

// Apply CSS to center headers and column content
const table = this.container.querySelector("table");
table.style.width = "100%";

// Center align headers and table cells
const headers = table.querySelectorAll("th");
headers.forEach(header => header.style.textAlign = "center");

const cells = table.querySelectorAll("td");
cells.forEach(cell => cell.style.textAlign = "center");

```

## Grad 8
```dataviewjs
const diceRoller = (damage) => {
    // If damage is not defined, return a placeholder
    if (!damage) return "";
    // Otherwise, format it as a dice roller command
    return `\`dice: ${damage}|none|noform\``;
};

dv.table(
    ["Zauber", "Schule", "Zeitaufwand", "Schadensart", "Schaden", "Ziel", "Reichweite", "Verbal", "Geste", "Dauer", "Konzentration", "Ritual"],
    dv.pages("#Zauber")
      .where(p => p.Grad == 8 && dv.current().Zauber.some(link => link.path === p.file.path))
      .sort(p => p.file.name)
      .map(p => [
          p.file.link,
          p.Schule,
          p.Zeitaufwand,
          p.Schadensart,
          diceRoller(p.Schaden),   // Schaden as dice roller command
          p.Ziel,
          p.Reichweite,
          p.Verbal ? "X" : "",
          p.Geste ? "X" : "",
          p.Dauer,
          p.Konzentration ? "X" : "",
          p.Ritual ? "X" : ""
      ])
);

// Apply CSS to center headers and column content
const table = this.container.querySelector("table");
table.style.width = "100%";

// Center align headers and table cells
const headers = table.querySelectorAll("th");
headers.forEach(header => header.style.textAlign = "center");

const cells = table.querySelectorAll("td");
cells.forEach(cell => cell.style.textAlign = "center");

```

## Grad 9
```dataviewjs
const diceRoller = (damage) => {
    // If damage is not defined, return a placeholder
    if (!damage) return "";
    // Otherwise, format it as a dice roller command
    return `\`dice: ${damage}|none|noform\``;
};

dv.table(
    ["Zauber", "Schule", "Zeitaufwand", "Schadensart", "Schaden", "Ziel", "Reichweite", "Verbal", "Geste", "Dauer", "Konzentration", "Ritual"],
    dv.pages("#Zauber")
      .where(p => p.Grad == 9 && dv.current().Zauber.some(link => link.path === p.file.path))
      .sort(p => p.file.name)
      .map(p => [
          p.file.link,
          p.Schule,
          p.Zeitaufwand,
          p.Schadensart,
          diceRoller(p.Schaden),   // Schaden as dice roller command
          p.Ziel,
          p.Reichweite,
          p.Verbal ? "X" : "",
          p.Geste ? "X" : "",
          p.Dauer,
          p.Konzentration ? "X" : "",
          p.Ritual ? "X" : ""
      ])
);

// Apply CSS to center headers and column content
const table = this.container.querySelector("table");
table.style.width = "100%";

// Center align headers and table cells
const headers = table.querySelectorAll("th");
headers.forEach(header => header.style.textAlign = "center");

const cells = table.querySelectorAll("td");
cells.forEach(cell => cell.style.textAlign = "center");

```