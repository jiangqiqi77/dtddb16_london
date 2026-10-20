# Soho Cholera Map, 1854

An interactive teaching map of John Snow's 1854 Broad Street cholera outbreak in Soho, London.

It plots all 578 deaths Snow recorded, the 13 water pumps and the street network. Three "interesting facts" are highlighted for discussion:

- **Lion Brewery** – right next to the pump, yet none of its ~70 workers died (they drank beer; the brewery had its own well).
- **Poland Street workhouse** – only 5 deaths among ~535 residents (it had its own well).
- **The Hampstead widow** – died about 4 miles away after having Broad Street water delivered daily.

## Use it

- Open `index.html` in any browser. Everything is in that one file and it works offline (fonts fall back to system fonts without internet).
- Drag to pan, scroll or pinch to zoom, and use the home button to reset.
- Toggle layers in the sidebar; click a pump or an interesting fact for details.

## Publish on GitHub Pages

1. Create a new repository and upload `index.html`, `README.md` and the `data` folder.
2. Go to **Settings → Pages**, set the source to **Deploy from a branch**, choose `main` and `/ (root)`, and save.
3. After a minute the map is live at `https://<your-username>.github.io/<repository-name>/`.

## Data

`data/snow-1854.json` holds the same data that is embedded in `index.html`:

- `deaths` – `[x, y]` for each death
- `pumps` – `[name, x, y]`
- `streets` – a list of polylines, each `[[x, y], ...]`
- `cells` – nearest-pump (Voronoi) areas, one polygon per pump

Coordinates are in the units of Snow's original map, not latitude and longitude.

### Sources

- Snow, J. (1855). *On the Mode of Communication of Cholera*, 2nd edition.
- Deaths, pumps and streets digitized by Waldo Tobler, distributed in the R package [HistData](https://github.com/friendly/HistData) (Friendly & Dalal; GPL-2 licensed). Please keep this attribution if you reuse the data.
- The brewery and workhouse outlines are approximate positions added for teaching; they are not part of Snow's digitized data.
