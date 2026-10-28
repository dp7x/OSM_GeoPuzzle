# GeoPuzzle — OSM Edition 🗺️

A single-file puzzle game with **real OpenStreetMap maps**: pick an area on the map, download the tiles and put them back together. Everything lives in one `index.html` file — no build step, no local dependencies (Leaflet is only loaded from a CDN for the area picker).

🔗 **Play (GitHub Pages):** https://dp7x.github.io/OSM_GeoPuzzle/

## How to play

1. **Explore the map** in the picker and position your area (the green frame shows which tiles will be used)
2. Pick a difficulty: **EASY 3×3** · **MEDIUM 4×4** · **HARD 5×5** · **EXPERT 6×6**
3. Hit **Start puzzle →**: the real tiles get downloaded and shuffled
4. Drag the tiles (mouse or touch) to rebuild the map:
   - tiles in the right spot light up **green** (it's just a hint — they stay draggable!)
   - dropping a tile on an occupied spot slides the previous occupant to your tile's original spot
5. 💡 **HINT** (3 per game): shows the complete picture on top of the pieces
6. Win: the **full map stays on screen** with banner and confetti until you press a key or click → then the stats and your local best time (per difficulty)

## Technical features

- **Single-file HTML/CSS/JS**: open it with a double click, easy to embed in a blog
- Real tiles from a configurable `<tile template>` (default `https://tile.openstreetmap.org/{z}/{x}/{y}.png`) — automatic retry without CORS
- Area picker with **Leaflet** (CDN) + manual mode (lat/lon/zoom) when Leaflet can't load
- N×N tile compositing into a 600×600 canvas, drag & drop with pointer events (mouse + touch)
- WebAudio sound effects (pick/snap/win), local best times in `localStorage`, win reveal with confetti
- Responsive interface with touch-friendly controls, labelled fields and inline search feedback
- No server required: everything runs in the browser

## License / attribution

Map imagery is generated from data **© OpenStreetMap contributors (ODbL)**. The attribution is shown in-game (canvas corner) and on the page. If you publish or modify this page, keep the attribution intact, following the [OSM tile usage policy](https://operations.osmfoundation.org/policies/tiles/) (low volume: N×N tiles per game, zoom ≤ 19).

Game code: [MIT License](LICENSE), © 2025 dp7. Leaflet is distributed under BSD-2; map data and styles retain their own attribution and licenses.

## Development

The whole game lives in `index.html` (one inline `<style>` section and one inline `<script>` section — no build, no bundler). Edit the file and publish; GitHub Pages automatically serves the `main` branch.

## License

© 2025 **dp7**@[OpenStreetMap](https://www.openstreetmap.org/user/dp7). Licensed under the [MIT License](LICENSE).

Map imagery follows [OSM policy](https://operations.osmfoundation.org/policies/tiles/) (© OpenStreetMap contributors, ODbL). OpenTopoMap cartography is licensed under CC-BY-SA; these map licenses are separate from the game code.

