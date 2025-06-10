---
Uke: 04
Dag: 23-24
---
### 🎯 Mål:

- Lage API-endepunkter (ruter) for å hente og sende data.
- Forstå hva en JSON-body er.

### 📚 Ressurser:

- [REST API concepts](https://www.youtube.com/watch?v=lsMQRaeKNDk)
- [Postman Intro](https://www.youtube.com/watch?v=VywxIQ2ZXw4)

### 🛠 Oppgaver:

- Lag en route for å hente notater (GET `/notes`)
- Lag en route for å legge til nye notater (POST `/notes`)
- Bruk Postman eller Insomnia for å teste API-et ditt

```
let notes = [];

app.use(express.json());

app.get('/notes', (req, res) => {
  res.json(notes);
});

app.post('/notes', (req, res) => {
  const note = req.body;
  notes.push(note);
  res.status(201).json(note);
});
```

### 📝 Notater:

- JSON brukes ofte til å sende og motta data mellom klient og server.
- Bruk `express.json()` for å parse JSON-bodyer.