# EWAS – Explore with All Senses

Digitální desková hra pro 2–6 hráčů. Po spuštění se na titulní straně vybere mapa hry.

Adresa hry: https://racekrob.github.io/EWAS/

## Struktura
- `index.html` – titulní strana s výběrem mapy (+ `manifest.json`, ikony)
- `italia/` – hra Italia (offline i online hra přes Firebase, karty políček a speciální karty)
- `cesko/` – hra Česko (offline i online hra přes Firebase, karty políček v `cesko/karty/`)

## Přidání další mapy
1. Nahrajte hru do nové složky, např. `francie/index.html`.
2. V `index.html` doplňte do rozbalovacího pole řádek
   `<option value="francie/index.html">Francie</option>`.

## Online hra (Italia, Česko)
Data jsou ve Firebase projektu Immigrants pod `ewas/italia/<KÓD>` a `ewas/cesko/<KÓD>`. Pravidla databáze musí povolit větev `ewas`:
```json
"ewas": { "$country": { "$code": { ".read": "auth != null", ".write": "auth != null" } } }
```

## Zveřejnění na GitHub Pages
Settings → Pages → Source: *Deploy from a branch* → Branch `main`, složka `/ (root)` → Save.
