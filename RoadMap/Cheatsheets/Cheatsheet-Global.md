> [!Warning] Important 
> Welcome! To the _Global CheatSheet_


```dataviewjs
let pages = dv.pages().where(p => /^Day-\d+$/i.test(p.file.name));
let merged = new Map();

for (let p of pages) {
  let content = await dv.io.load(p.file.path);
  let lines = content.split("\n");

  let inTable = false;
  for (let line of lines) {
    if (line.trim().startsWith("| Command")) {
      inTable = true;
      continue;
    }
    if (inTable) {
      if (line.trim() === "" || !line.includes("|")) break;
      if (line.includes("---")) continue;

      let parts = line.split("|").map(c => c.trim());
      if (parts.length >= 4) {
        let cmdPlain = parts[1];   // plain text
        let desc = parts[2];
        let catField = parts[3];
        let cmdRaw = cmdPlain;     // keep it plain, no link
        let from = `[${p.file.name}](${p.file.name}.md)`; // source stays clickable

        // Handle multiple categories
        let cats = catField.split(",").map(c => c.trim()).filter(c => c);
        for (let c of cats) {
          let key = c.toLowerCase() + "|" + cmdPlain.toLowerCase();
          if (!merged.has(key)) {
            merged.set(key, { cat: c, cmdPlain, cmdRaw, desc, froms: new Set([from]) });
          } else {
            merged.get(key).froms.add(from);
          }
        }
      }
    }
  }
}

// Group and render
let grouped = {};
for (let [_, r] of merged.entries()) {
  if (!grouped[r.cat]) grouped[r.cat] = [];
  grouped[r.cat].push([
    r.cmdRaw,  // plain text command
    r.desc,
    Array.from(r.froms).join("<br>") // multiple sources
  ]);
}

for (let cat of Object.keys(grouped).sort()) {
  dv.header(3, cat);
  dv.table(["Command", "Description", "From"], grouped[cat]);
}

```


