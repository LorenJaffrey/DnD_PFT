```dataviewjs
//---------------------------------------------------------------------
// ⚙️ Hardcoded-Zauberübersicht mit Tooltip + Sortierung + Stil
//---------------------------------------------------------------------

const headers = [
  "Typ",
  "Zauber",
  `<span title="Aktiv / Verfügbar / Max." style="cursor: help;">🟢/💠/🔢</span>`,
  `<span title="Zeitaufwand / Reichweite / Dauer" style="cursor: help;">⏱️/📏/⏳</span>`,
  "💥 Schaden",
  "🎯 Ziel",
  `<span title="Verbal & Gestik" style="cursor: help;">🗣️💫</span>`,
  `<span title="Konzentration & Ritual" style="cursor: help;">🔮📜</span>`,
  "🌙 Erholung",
  "[[Rettungswurf|RW]]"
];

// Hilfsfunktion: Baut die Anzeige für Aktiv / Verfügbar / Max. mit farbigen Kreisen
function buildAVM(aktiv, verfügbar, max) {
    const style = `
        display:inline-block;
        min-width:1.5em;
        padding:0.2em 0.4em;
        margin:0 0.1em;
        border-radius:0.3em;
        color:white;
        text-align:center;
    `;
    
    let result = "";
    if (aktiv) result += `<span style="${style}">${aktiv}</span>`;
    if (verfügbar) result += `<span style="${style}">${verfügbar}</span>`;
    if (max) result += (verfügbar ? " / " : (result ? " " : "")) + `<span style="${style}">${max}</span>`;
    return result;
}

// 🧩 Hardcoded Tabelleninhalte (optimiert)
const rows = [
  [
    "[[Offensivzauber|Angriff]]",
    "[[Drakonische Odemwaffe|Blitz-Odem]]",
    buildAVM("`INPUT[toggle:InputData.BlitzOdemAktiv]`", "`INPUT[number():InputData.BlitzOdem]`", "`=ceil(this.Stufe/4)+1`"),
    "[[Aktion]] / Linie: 9 m ~ [[Kegel]]: 4.5 m",
    "`$=\"```dice: \" + (dv.current().Stufe < 5 ? \"1d10\" : dv.current().Stufe < 11 ? \"2d10\" : dv.current().Stufe < 17 ? \"3d10\" : \"4d10\") + \" |none|noform```\"`",
    "AoE",
    " ",
    " ",
    "[[Lange Rast]]",
    "[[Geschicklichkeit|GES]]"
  ],
  [
    "[[Buff]]",
    "[[Intuitive Zauberei]]",
    buildAVM("`INPUT[toggle:InputData.IntuitiveZaubereiAktiv]`", "`INPUT[number():InputData.IntuitiveZaubereiLadungen]`", "2"),
    "[[Bonusaktion]] / Selbst / 1 Minute",
    " ",
    "Selbst",
    "<span title='Verbal' style='cursor: help;'>🗣️</span><span title='Gestik' style='cursor: help;'>💫</span>",
    " ",
    "[[Lange Rast]]",
    " "
  ],
  [
    "[[Fortbewegung|Move]]",
    "[[Drakonischer Flug]]",
    buildAVM("`INPUT[toggle:InputData.DrakonischerFlugAktiv]`", "`INPUT[number():InputData.DrakonischerFlugLadungen]`", "1"),
    "[[Bonusaktion]] / Selbst / 10 Minuten",
    " ",
    "Selbst",
    " ",
    " ",
    "[[Lange Rast]]",
    " "
  ],
  [
    "[[Positionskontrolle|POS-Ctrl]]",
    "[[Tempestuskristall - Fragment des Donners|Druckwelle]]",
    buildAVM(null, "`INPUT[number():InputData.DruckwelleLadungen]`", "1"),
    "[[Bonusaktion]] / AoE ~ Radius: 3 m",
    "[[Schallschaden]]",
    "AoE",
    "<span title='Gestik' style='cursor: help;'>💫</span>",
    " ",
    "[[Kurze Rast]],</br>[[Lange Rast]]",
    "[[Stärke|STA]]"
  ],
  [
    "[[Defensivzauber|Abwehr]]",
    "[[Klingenbann]]",
    buildAVM("`INPUT[toggle:InputData.Klingenbann]`", null, null),
    "[[Aktion]] / Selbst / 1 Minute",
    "`dice:1d4`<span title='Angriffswurf des Gegners' style='cursor: help;'>⚔️👿</span>",
    "Selbst",
    "<span title='Verbal' style='cursor: help;'>🗣️</span><span title='Gestik' style='cursor: help;'>💫</span>",
    " ",
    " ",
    " "
  ],
  [
    "[[Defensivzauber|Abwehr]]",
    "[[Magierrüstung]]",
    buildAVM("`INPUT[toggle:InputData.MagierRüstung]`", null, null),
    "[[Aktion]] / Selbst / 8 Stunden",
    " ",
    "Selbst",
    "<span title='Verbal' style='cursor: help;'>🗣️</span><span title='Gestik' style='cursor: help;'>💫</span>",
    " ",
    " ",
    " "
  ],
  [
    "[[Defensivzauber|Abwehr]]",
    "[[Spiegelbilder]]",
    buildAVM("`INPUT[toggle:InputData.SpiegelbilderAktiv]`", "`INPUT[number():InputData.SpiegelbilderLadungen]`", "3"),
    "[[Aktion]] / Selbst / 1 Minute",
    " ",
    "Selbst",
    "<span title='Verbal' style='cursor: help;'>🗣️</span><span title='Gestik' style='cursor: help;'>💫</span>",
    " ",
    " ",
    "`dice:1d6`</br>`dice:1d6`</br>`dice:1d6`"
  ]
];

// 🪄 Tabelle ausgeben
dv.table(headers, rows);

// -------------------------------------------------------------
// ✨ Styling & Sortierfunktion
// -------------------------------------------------------------
const table = this.container.querySelector("table");
table.style.width = "100%";
table.querySelectorAll("td").forEach(td => {td.style.textAlign = "center"; td.style.verticalAlign = "middle";});
table.querySelectorAll("th").forEach((header, i) => {
  header.style.textAlign = "center";
  header.style.cursor = "pointer";
  header.addEventListener("click", () => {
    const rows = Array.from(table.querySelectorAll("tr")).slice(1);
    const asc = !header.classList.contains("ascending");
    rows.sort((a, b) => {
      const A = a.children[i].textContent.trim();
      const B = b.children[i].textContent.trim();
      return asc ? A.localeCompare(B) : B.localeCompare(A);
    });
    rows.forEach(r => table.appendChild(r));
    table.querySelectorAll("th").forEach(h => h.classList.remove("ascending", "descending"));
    header.classList.toggle("ascending", asc);
    header.classList.toggle("descending", !asc);
  });
});

```