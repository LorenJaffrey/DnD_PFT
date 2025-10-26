```dataviewjs
//---------------------------------------------------------------------
// 🧙 Zauberliste – kompakt + Emojis für Schadensarten + Tooltips
//---------------------------------------------------------------------

// 🎲 Dice Roller
const diceRoller = (damage) => {
  if (!damage) return " ";
  return `\`dice: ${damage}|none|noform\``;
};

// 🧮 Dynamische Schadensberechnung für Zaubertricks
const getDamageByLevel = (level, p) => {
  if (level >= 17 && p.SchadenLv17) return diceRoller(p.SchadenLv17);
  if (level >= 11 && p.SchadenLv11) return diceRoller(p.SchadenLv11);
  if (level >= 5 && p.SchadenLv5)  return diceRoller(p.SchadenLv5);
  return diceRoller(p.Schaden);
};

// ✨ Schadensart → Emoji-Mapping
const damageEmoji = (type) => {
  if (!type) return ""; // kein Schaden angegeben

  // Datei-Name aus Dataview-Link extrahieren
  const name = type?.fileName() ?? null;
  if (!name) return "";

  // Mapping der Schadensarten zu Emojis
  const map = {
    "Blitzschaden": "⚡",
    "Energieschaden": "🔋",
    "Feuerschaden": "🔥",
    "Giftschaden": "☠️",
    "Gleißender Schaden": "🌟",
    "Hiebschaden": "🗡️",
    "Kälteschaden": "❄️",
    "Nekrotischer Schaden": "💀",
    "Psychischer Schaden": "🧠",
    "Säureschaden": "🧪",
    "Schallschaden": "🔊",
    "Stichschaden": "🏹",
    "Wuchtschaden": "💥",
    "Zufallsschaden": "🎲",
    "Chaospfeil Schadensarten": "🌈",
    "Explosion der Zauberei Schadensarten": "☄️"
  };

  // Emoji auswählen oder Fallback
  const emoji = map[name] ?? "❔";

  // Tooltip + klickbarer Link + Fallback für kaputte Links
  const linkPath = type?.path ?? "";
  return linkPath
    ? `<a href="${linkPath}" class="internal-link no-hcl" title="${name}" style="text-decoration: none; cursor: help;">${emoji}</a>`
    : `<span title="${name}" style="cursor: help;">${emoji}</span>`;
};

// 🧩 Tabellen-Header (reduziert & mit Icons + Tooltips)
const headers = [
  "Typ",
  "Zauber",
  `<span title="Zeitaufwand / Reichweite / Dauer" style="cursor: help;">⏱️/📏/⏳</span>`,
  "💥 Schaden",
  "🎯 Ziel",
  `<span title="Verbal & Gestik" style="cursor: help;">🗣️💫</span>`,
  `<span title="Konzentration & Ritual" style="cursor: help;">🔮📜</span>`,
  "[[Rettungswurf|RW]]"
];

// ✨ Helper-Funktion: Icons mit Tooltip & Cursor
const icon = (symbol, tooltip) =>
  `<span title="${tooltip}" style="cursor: help;">${symbol}</span>`;

// -------------------------------------------------------------
// Helper: kombiniert Konzentration & Ritual sauber
// -------------------------------------------------------------
const concRitual = (p) => {
  const c = p.Konzentration ? icon("🔮","Konzentration") : "";
  const r = p.Ritual ? icon("📜","Ritual") : "";
  if (c && r) return `${c} • ${r}`;
  return c || r || " ";
};

// -------------------------------------------------------------
// GRAD 0 – Zaubertricks
// -------------------------------------------------------------
const cantrips = dv.pages("#Zauber")
  .where(p => p.Grad == 0 && dv.current().Zauber.some(link => link.path === p.file.path))
  .sort(p => p.file.name)
  .sort(p => p.Typ);

if (cantrips.length > 0) {
  dv.header(2, "Zaubertricks");
  dv.table(
    headers,
    cantrips.map(p => [
      p.Typ ?? " ",
      p.file.link ?? " ",
      `${p.Zeitaufwand ?? " "} / ${p.Reichweite ?? " "} / ${p.Dauer ?? " "}`,
      p.Schadensart
        ? `${damageEmoji(p.Schadensart)} ${getDamageByLevel(dv.current().Stufe, p)}`
        : getDamageByLevel(dv.current().Stufe, p),
      p.Ziel ?? " ",
      `${p.Verbal ? icon("🗣️","Verbal") : ""}${p.Geste ? icon("💫","Gestik") : ""}` || " ",
      concRitual(p),
      p.Rettungswurf ?? " "
    ])
  );
}

// -------------------------------------------------------------
// GRAD 1–9 Zauber
// -------------------------------------------------------------
for (let magicRank = 1; magicRank <= 9; magicRank++) {

  const spells = dv.pages("#Zauber")
    .where(p => p.Grad == magicRank && dv.current().Zauber.some(link => link.path === p.file.path))
    .sort(p => p.file.name)
    .sort(p => p.Typ);

  if (spells.length > 0) {
    dv.header(2, `Grad ${magicRank}`);
    dv.table(
      headers,
      spells.map(p => [
        p.Typ ?? " ",
        p.file.link ?? " ",
        `${p.Zeitaufwand ?? " "} / ${p.Reichweite ?? " "} / ${p.Dauer ?? " "}`,
        p.Schadensart
          ? `${damageEmoji(p.Schadensart)} ${diceRoller(p.Schaden)}`
          : diceRoller(p.Schaden),
        p.Ziel ?? " ",
        `${p.Verbal ? icon("🗣️","Verbal") : ""}${p.Geste ? icon("💫","Gestik") : ""}` || " ",
        concRitual(p),
        p.Rettungswurf ?? " "
      ])
    );
  }
}

// -------------------------------------------------------------
// ✨ Styling & Sortierfunktion
// -------------------------------------------------------------
const tables = this.container.querySelectorAll("table");
tables.forEach(table => {
  table.style.width = "100%";
  table.querySelectorAll("td").forEach(td => td.style.textAlign = "center");
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
});

```
