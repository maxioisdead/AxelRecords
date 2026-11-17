# Changelog — Axel Records

All notable changes to the Axel Records 3D Vinyl Library & Listening Room are documented in this file.

---

## [v1.0.3] — 2026-11-18

### ✨ New Features & Improvements

- **Interactive Release & Song Picker for "Refresh Data":**
  - Clicking **↻ Refresh Data** in the Album Details drawer now opens an inline candidate picker dropdown instead of blindly overwriting metadata.
  - Queries Apple Music Albums, Apple Music Songs, and Deezer in parallel so you can compare cover art, release years, and track matches—or refine the search query—and pick the exact pressing you want.
- **Persistent Album Details Drawer Memory:**
  - The open/closed state of the **Album Details** drawer is now saved across sessions (`localStorage`), remaining consistent when you press `Escape`, click off onto the 3D hall canvas, or switch between records.
- **Smart Shelf-to-Turntable Live Scrobble Matching:**
  - When a song plays live via Last.fm or Spotify, Axel Records checks your physical shelves by album title, artist, or tracklist match.
  - If the record is in your collection, it stages your shelved edition onto the credenza stand, loads its custom vinyl pressing wax color (e.g., Cobalt, Honey Amber, Ruby) onto the turntable platter, highlights its spine in emerald on the bookcase, and displays `ON SHELF LIVE` on the OLED console.
- **Enhanced Duplicate Title & Artist Detection:**
  - Upgraded **🔍 Check Duplicates** to detect both exact album/artist duplicates and normalized title collisions (stripping edition tags like *Deluxe*, *Remastered*, or *Anniversary*), clearly labeling each match reason in the scanner modal.
- **Improved JSON Clipboard & Backup Reliability:**
  - Added a multi-step clipboard fallback to **📋 Copy JSON** so copying your library backup works smoothly even inside sandboxed iframes or local `file://` environments, paired with direct `.json` file export and paste-to-restore support.
- **Shelf Deletion Confirmation & Title Version Bump:**
  - Added a confirmation modal when deleting a bookcase shelf showing how many records will safely transfer to the primary shelf, and updated the UI version badge to **v1.0.3**.

---

## [v1.0.25] — 2026-11-18

### 🚀 Major Improvements & New Features

- **Unobstructed Back Shelf Camera Framing:**
  - Back-row shelf cameras (`bayIdx >= 3`) now position directly inside the aisle in front of the selected shelf so front bookcases never block your view.
- **Ordered Front-to-Back Shelf Replacement:**
  - Bookcases track their physical bay index (`0..N`), so deleting any front shelf opens its bay and newly added shelves automatically fill the earliest open slot from front to back.
- **Interactive Listening Chair & Headphone Mode:**
  - Click the 3D Eames listening chair (or the **Listening Chair** header button) to sit down, lift off the headphones, and engage a warm analog headphone vignette view.
- **Vinyl Dust & Static Particle Toggle:**
  - Added floating golden static motes alongside sunlit dust particles with a dedicated **Dust & Static** toggle button in the top bar.
- **"Digging in the Crates" Minigame:**
  - Click **Crate Dig** to flip open mystery dusty sleeves across Jazz, Soul, Rock, and Electronic crates and claim rare pressings directly onto your shelves.
- **Duplicate Checker & Cleanup Tools:**
  - Added **🔍 Check Duplicates** (which highlights duplicate copies in 3D and lets you remove them individually or all at once) and **🧹 Remove All** (with confirmation) in the shelf toolbar.
- **Glitch-Free Bookcase Backs:**
  - Adjusted internal shelf plank depths, record slot depth clearances, and `polygonOffset` on the rear walnut backboard so there is zero Z-fighting or clipping on the back of shelves.
- **Live Album & Turntable Staging:**
  - When a live song plays via Last.fm or Spotify (or preview/spin), the album cover stands upright on the credenza table and spins as the center label on the turntable platter.
- **Clickable GitHub & Discord Links Box:**
  - Added a dedicated glassmorphic link card next to the Axel Records logo with direct links to `https://github.com/maxioisdead/AxelRecords/` and `https://discord.gg/e78Y7ttbv`.

---

## [v1.0.1] — 2026-11-17

### ✨ New Features & Integrations

- **Multi-Source Album Search & Batch Selection:**
  - Added provider selector supporting Apple Music, Deezer, MusicBrainz, Discogs, and an All Sources unified search mode.
  - Added batch selection checkboxes (☐ / ☑) to search results, allowing collectors to select and shelve multiple albums at once.
  - Added inline ▶ Preview playback directly from search results before adding a record to the library.
- **Automated Metadata Refresh Engine:**
  - Added ↻ Refresh Metadata for individual records inside the details drawer and ↻ Refresh All Album Metadata in Library Archive & Backup.
  - Queries multiple regional Apple Music storefronts (JP, US, GB, KR, AU), Deezer, MusicBrainz/Cover Art Archive, Spotify, Discogs (with optional personal access token support), and Rate Your Music to automatically populate missing cover art, release years, labels, genres, and tracklists.
- **Rate Your Music (RYM) CSV Importer:**
  - Added direct Import Rate Your Music CSV support in Library Tools, parsing titles, localized/standard artist names, release dates, ratings (converted to 5-star scale), reviews, and ownership notes.
- **Live Turntable "Now Playing" Display:**
  - Upgraded the 3D mid-century hi-fi credenza with a dynamic canvas display showing currently spinning tracks.
  - Added Last.fm live scrobble polling alongside Spotify currently-playing integration.
- **Expanded Hall Customization & Shelf Management:**
  - Added dynamic bookcase management: Add Shelf (up to 36 additional 4-tier bookcases), Rename Shelf (via button or double-clicking shelf tabs), Delete Shelf, and Move to Shelf inside album details.
  - Added a Custom Hall Poster creator allowing users to hang framed artwork on the back and side walls of the listening hall.
- **Interactive Controls Tutorial & Keyboard Navigation:**
  - Added a 5-step interactive Tutorial HUD guiding new users through camera movement, browsing, inspecting, and customizing records.
  - Added full keyboard browsing (Arrow Keys to navigate records, Enter to inspect, Space to flip sleeve, F to favorite, P to preview, R for random pick, ? for shortcut hints).

### 🎨 UI & Visual Enhancements

- **Refined Record-Shop UI Hierarchy:** Updated typography to Space Grotesk and DM Sans with higher-contrast glassmorphic panels and responsive mobile drawer layouts.
- **Advanced Library Filtering & Sorting:**
  - Added physical shelf sorting by Manual Order, Album Name, Artist, Genre, or Year.
  - Added real-time filtering by Genre, Artist, Decade, and ★ Favorites.
- **Spine-Out Shelving & Drag Reordering:**
  - Positioned shelved records spine-out (72 records per tier / 288 per bookcase) with procedural spines featuring miniature cover art thumbnails.
  - Enabled click-and-drag reordering along shelf tiers.
- **Full In-Drawer Album Editor:** Added direct editing for album title, artist, year, genre, label, cover URL, Spotify link, tracklist lines, accent color, and spin count.

### ⚡ Performance & Rendering Optimizations

- **Throttled Raycasting:** Capped pointer hover raycasting to 24 Hz (1/24s intervals) to eliminate main-thread stutters during camera panning.
- **Renderer & Shadow Tuning:** Capped pixel ratio to 1.0, disabled costly default WebGL multisample antialiasing (antialias: false), and reduced spotlight shadow map resolution to 256x256 for smoother framerates on integrated GPUs.
- **Memory & Texture Cleanup:** Added explicit `.dispose()` cleanup for geometries, materials, and canvas textures when rebuilding shelves, updating artwork, or removing albums.
- **Zero-Allocation Frame Loops:** Replaced per-frame `THREE.Color` instantiations and vector allocations in the render loop with reusable scratch vectors and direct RGB channel interpolation.
