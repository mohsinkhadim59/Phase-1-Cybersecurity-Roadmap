> [!Info] What is SSH? 
> Hi this is to tell you this is the cheat sheet of SSH.

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
        let cmdPlain = parts[1];   // plain text command
        let desc = parts[2];
        let catField = parts[3];
        let cmdRaw = cmdPlain;     // keep it plain, no link
        let from = `[${p.file.name}](${p.file.name}.md)`; // source clickable

        // Handle multiple categories
        let cats = catField.split(",").map(c => c.trim()).filter(c => c);
        for (let c of cats) {
          if (c.toLowerCase() !== "ssh") continue; // only keep SSH
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

// Render SSH-only table
let rows = Array.from(merged.values())
  .sort((a,b) => a.cmdPlain.localeCompare(b.cmdPlain)) // sort alphabetically
  .map(r => [
    r.cmdRaw,   // plain text command
    r.desc,
    Array.from(r.froms).join("<br>")
  ]);

dv.table(["Command", "Description", "From"], rows);
```


