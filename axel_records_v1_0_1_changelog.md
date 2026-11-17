# Changelog — Axel Records

All notable changes to the **Axel Records** 3D Vinyl Library & Listening Room are documented in this file.

---

## [v1.0.1] — 2026-11-17

### ✨ New Features & Integrations
* **Multi-Source Album Search & Batch Selection**:
  * Added provider selector supporting **Apple Music**, **Deezer**, **MusicBrainz**, **Discogs**, and an **All Sources** unified search mode.
  * Added batch selection checkboxes (`☐` / `☑`) to search results, allowing collectors to select and shelve multiple albums at once.
  * Added inline **▶ Preview** playback directly from search results before adding a record to the library.
* **Automated Metadata Refresh Engine**:
  * Added **↻ Refresh Metadata** for individual records inside the details drawer and **↻ Refresh All Album Metadata** in Library Archive & Backup.
  * Queries multiple regional Apple Music storefronts (`JP`, `US`, `GB`, `KR`, `AU`), Deezer, MusicBrainz/Cover Art Archive, Spotify, Discogs (with optional personal access token support), and Rate Your Music to automatically populate missing cover art, release years, labels, genres, and tracklists.
* **Rate Your Music (RYM) CSV Importer**:
  * Added direct **Import Rate Your Music CSV** support in Library Tools, parsing titles, localized/standard artist names, release dates, ratings (converted to 5-star scale), reviews, and ownership notes.
* **Live Turntable "Now Playing" Display**:
  * Upgraded the 3D mid-century hi-fi credenza with a dynamic canvas display showing currently spinning tracks.
  * Added **Last.fm** live scrobble polling alongside **Spotify** currently-playing integration.
* **Expanded Hall Customization & Shelf Management**:
  * Added dynamic bookcase management: **Add Shelf** (up to 36 additional 4-tier bookcases), **Rename Shelf** (via button or double-clicking shelf tabs), **Delete Shelf**, and **Move to Shelf** inside album details.
  * Added a **Custom Hall Poster** creator allowing users to hang framed artwork on the back and side walls of the listening hall.
* **Interactive Controls Tutorial & Keyboard Navigation**:
  * Added a 5-step interactive **Tutorial HUD** guiding new users through camera movement, browsing, inspecting, and customizing records.
  * Added full keyboard browsing (`Arrow Keys` to navigate records, `Enter` to inspect, `Space` to flip sleeve, `F` to favorite, `P` to preview, `R` for random pick, `?` for shortcut hints).

### 🎨 UI & Visual Enhancements
* **Refined Record-Shop UI Hierarchy**: Updated typography to **Space Grotesk** and **DM Sans** with higher-contrast glassmorphic panels and responsive mobile drawer layouts.
* **Advanced Library Filtering & Sorting**:
  * Added physical shelf sorting by **Manual Order**, **Album Name**, **Artist**, **Genre**, or **Year**.
  * Added real-time filtering by **Genre**, **Artist**, **Decade**, and **★ Favorites**.
* **Spine-Out Shelving & Drag Reordering**:
  * Positioned shelved records spine-out (`72` records per tier / `288` per bookcase) with procedural spines featuring miniature cover art thumbnails.
  * Enabled click-and-drag reordering along shelf tiers.
* **Full In-Drawer Album Editor**: Added direct editing for album title, artist, year, genre, label, cover URL, Spotify link, tracklist lines, accent color, and spin count.

### ⚡ Performance & Rendering Optimizations
* **Throttled Raycasting**: Capped pointer hover raycasting to `24 Hz` (`1/24s` intervals) to eliminate main-thread stutters during camera panning.
* **Renderer & Shadow Tuning**: Capped pixel ratio to `1.0`, disabled costly default WebGL multisample antialiasing (`antialias: false`), and reduced spotlight shadow map resolution to `256x256` for smoother framerates on integrated GPUs.
* **Memory & Texture Cleanup**: Added explicit `.dispose()` cleanup for geometries, materials, and canvas textures when rebuilding shelves, updating artwork, or removing albums.
* **Zero-Allocation Frame Loops**: Replaced per-frame `THREE.Color` instantiations and vector allocations in the render loop with reusable scratch vectors and direct RGB channel interpolation.