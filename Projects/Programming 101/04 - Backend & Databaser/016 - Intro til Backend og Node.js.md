---
Uke: 4
Dag: 22
Emne: Backend, Node.js
tags:
  - Backend
  - Nodejs
  - CLI
---
### 🎯 Mål:

- Forstå hva backend-utvikling er og hvordan det henger sammen med frontend
- Installere og sette opp Node.js + Express    
- Lage din første webserver    

### 📚 Ressurser:

- [What is Backend Development? (freeCodeCamp)](https://www.youtube.com/watch?v=ENrzD9HAZK4)
- [Node.js crash course – Traversy Media](https://www.youtube.com/watch?v=fBNz5xF-Kx4)

### 🛠 Oppgaver:

- Installer Node.js og npm
- Lag et prosjekt med `npm init -y`
- Installer Express: `npm install express`
- Lag en fil `index.js` og skriv en enkel webserver:

```
const express = require('express');
const app = express();

app.get('/', (req, res) => {
  res.send('Hello from the backend!');
});

app.listen(3000, () => {
  console.log('Server running on http://localhost:3000');
});
```

### ❓ Spørsmål å svare på:

- Hva skjer når du går til `http://localhost:3000`?
- Hva er forskjellen på frontend og backend?