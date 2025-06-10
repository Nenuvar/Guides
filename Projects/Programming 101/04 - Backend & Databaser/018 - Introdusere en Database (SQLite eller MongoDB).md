---
Uke: 04
Dag: 26
---
### 🎯 Mål:

- Installere og bruke en database for å lagre data.
- Bytte ut den midlertidige `notes`-lista med ekte lagring.

### 📚 Ressurser:

- SQLite: [better-sqlite3 docs](https://github.com/WiseLibs/better-sqlite3)
- MongoDB Atlas: [Set up free cluster](https://www.mongodb.com/cloud/atlas)
- Intro to SQLite in Node.js


### 🛠 Oppgaver (SQLite):

- Installer: `npm install better-sqlite3`
- Opprett en database og en `notes`-tabell
- Endre `/notes`-ruter slik at de henter/lagrer fra databasen

```
const Database = require('better-sqlite3');
const db = new Database('notes.db');

db.prepare('CREATE TABLE IF NOT EXISTS notes (id INTEGER PRIMARY KEY, content TEXT)').run();

app.get('/notes', (req, res) => {
  const stmt = db.prepare('SELECT * FROM notes');
  const allNotes = stmt.all();
  res.json(allNotes);
});

app.post('/notes', (req, res) => {
  const { content } = req.body;
  const stmt = db.prepare('INSERT INTO notes (content) VALUES (?)');
  const info = stmt.run(content);
  res.status(201).json({ id: info.lastInsertRowid, content });
});
```

### ❓ Spørsmål:

- Hva er fordelene med å bruke en database?
- Hva er forskjellen mellom en GET og en POST-request?