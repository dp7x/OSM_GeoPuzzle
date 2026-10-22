# GeoPuzzle — OSM Edition 🗺️

Puzzle single-file con **mappe reali di OpenStreetMap**: scegli un'area sulla mappa, scarica le tile e ricomponile. Tutto in un solo file `index.html` — nessuna build, nessuna dipendenza locale (Leaflet arriva da CDN e serve solo per il selettore dell'area).

🔗 **Gioca (GitHub Pages):** _inserisci URL Pages dopo l'attivazione_

## Come si gioca

1. **Esplora la mappa** nel selettore e scegli l'area (il riquadro verde mostra i tile della zona)
2. Scegli la difficoltà: **FACILE 3×3** · **MEDIO 4×4** · **INTERMEDIO 5×5** · **ESPERTO 6×6**
3. Premi **🏗 USA QUEST'AREA**: le tile reali vengono scaricate e mischiate
4. Trascina le tile (mouse o touch) per ricomporre la mappa:
   - le tile al posto giusto si **illuminano di verde** (solo indicazione, restano spostabili!)
   - appoggiando una tile su una già occupata, l'occupante scivola nella tua slot di partenza
5. 💡 **INDIZIO** (3 per partita): mostra l'immagine completa in primo piano
6. Vittoria: la **mappa completa resta a schermo** con banner e coriandoli, finché non premi un tasto → poi le statistiche e il record locale (per difficoltà)

## Caratteristiche tecniche

- **Single-file HTML/CSS/JS**: apribile con doppio click, embeddabile in blog
- Tile reali da `<template tile>` configurabile (default `https://tile.openstreetmap.org/{z}/{x}/{y}.png`) — retry automatico senza CORS
- Selettore area con **Leaflet** (CDN) + modalità manuale (lat/lon/zoom) se Leaflet non carica
- Canvas composita N×N tile → puzzle 600×600, drag & drop pointer-events (mouse + touch)
- Audio WebAudio (pick/snap/vittoria), record in `localStorage`, reveal vittoria con coriandoli
- Nessun server richiesto: tutto nel browser

## Licenza / attribuzione

Le mappe sono generate da dati **© contributori OpenStreetMap (ODbL)**. L'attribuzione è mostrata in gioco (riquadro canvas) e a pagina. Se pubblichi o modifichi questa pagina, conserva l'attribuzione come da [OSM carto policy](https://operations.osmfoundation.org/policies/tiles/) (volume basso: N×N tile per partita, zoom ≤ 19).

Codice di gioco: libero. Non ha dipendenze oltre a Leaflet (BSD-2).

## Sviluppo

Il gioco vive tutto in `index.html` (una sezione `<style>` e una `<script>` inline).
Per contribuire/non build:

```bash
# modifica index.html a piacere e aggiorna
git add . && git commit -m "descrizione modifica"
git push
```

GitHub Pages pubblica automaticamente il ramo `main`.
