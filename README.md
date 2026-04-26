# Workshop arkitekter

Statisk sajt för korta workshop-övningar. Hostas på GitHub Pages.

## Struktur

```
.
├── index.html              ← landningssida som listar alla övningar
├── ovning-03/
│   └── index.html          ← Övning 03 — "Vad gör jag, och varför ligger det hos mig?"
└── ovning-NN/              ← framtida övningar
    └── index.html
```

## Lägga till en ny övning

1. Skapa en mapp `ovning-NN/` och lägg `index.html` i den.
2. **Använd en egen `STORAGE_KEY`** i form av `workshop_arkitekter_ovning_NN_v1` så svaren från olika övningar inte krockar i `localStorage`.
3. Lägg till en `<li class="item">` i rotens `index.html` som länkar till `./ovning-NN/`.
4. Commit + push till `main` — Pages deployar automatiskt.

## Lokalt

```
python3 -m http.server 8000
# öppna http://localhost:8000
```

Inget byggsteg — varje sida är fristående HTML med React via CDN.
