# PrevView

Point your phone at a landscape and see how it looked 100, 200, 300, 400 and 500 years ago
(1926, 1826, 1726, 1626, 1526): land cover, rivers and wetlands, villages and the wildlife of each era.

## Beta (v0.1)

A single-page web app, no build step.

| File | Purpose |
|---|---|
| `web/prevview.html` | App source (published as a Claude artifact) |
| `docs/index.html` | Standalone copy with a full HTML wrapper, for GitHub Pages or any HTTPS host |

**Use it**
1. Take a photo (or, on the standalone copy, use **Live camera**).
2. Drag the dashed line onto the horizon.
3. Pick a year on the ruler. The slider blends between *now* and *then*. Tap an animal for its story.
4. Inside Claude: **Ask Claude about this place** sends the photo and place to Claude, which returns a
   location-specific reconstruction for every era (land-cover mix, haze, species with status, modern
   structures to hide) as JSON.

**Location**: device GPS when the browser allows it, otherwise GPS from the photo's EXIF data, otherwise the chosen place.
Presets: Central German lowland, Dessau (Middle Elbe), Bitterfeld (Goitzsche), Bernburg (Strenzfeld), Harz.

**Live camera on GitHub Pages**: Settings → Pages → Deploy from branch → `main` / `/docs`.

## How the reconstruction works (beta)

- Built-in, indicative land-cover mix per era for Central Germany with regional modifiers
  (grounded on BfN potential natural vegetation, HYDE 3.3/LUH2, Prussian Urmesstischblätter).
- Wildlife status per era from documented regional dates (e.g. Harz bear 1705, Harz lynx 1818, Elbe beaver relict population, aurochs 1627).
- The landscape is painted procedurally on a canvas and blended over the camera image.

This is not yet a measured reconstruction. Next steps: real raster lookups (HYDE/LUH2, PNV, historical maps),
species distribution models, geospatial anchoring (ARCore Geospatial API) and 3D assets.
