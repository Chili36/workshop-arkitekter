# Workshop arkitekter

Statisk sajt för korta workshop-övningar. Hostas på GitHub Pages.

## Struktur

```
.
├── index.html                         ← landningssida som listar alla övningar
├── ovning-03/
│   ├── index.html                     ← Övning 03 — "Vad gör jag, och varför ligger det hos mig?"
│   └── admin/
│       └── index.html                 ← live-vägg för facilitator (hårdkodad till ovning-03)
└── ovning-NN/                         ← framtida övningar
    ├── index.html
    └── admin/index.html               ← egen admin per övning
```

Adminsidan är medvetet hårdkodad per övning — den är inte en delad
admin på rot-nivå. När en ny övning läggs till får den sin egen
`admin/` under sin egen mapp.

## Lägga till en ny övning

1. Skapa en mapp `ovning-NN/` och lägg `index.html` i den.
2. **Använd en egen `STORAGE_KEY`** i form av `workshop_arkitekter_ovning_NN_v1` så svaren från olika övningar inte krockar i `localStorage`.
3. Om övningen ska sparas till Supabase: sätt `EXERCISE_ID = 'ovning-NN'` i scriptet, och kopiera `ovning-03/admin/index.html` till `ovning-NN/admin/index.html` och ändra `EXERCISE_ID` även där.
4. Lägg till en `<li class="item">` i rotens `index.html` som länkar till `./ovning-NN/`.
5. Commit + push till `main` — Pages deployar automatiskt.

## Lokalt

```
python3 -m http.server 8000
# öppna http://localhost:8000
```

Inget byggsteg — varje sida är fristående HTML med React via CDN.
