# Axel Records, 3D Vinyl Library & Listening Room

Axel Records is an immersive, browser-based 3D vinyl record collection and virtual listening room built with **Three.js** and **Tailwind CSS**. It allows music collectors to organize their physical or digital music libraries across grand wooden bookcases, inspect front and back cover art, spin tracks, and curate their dream record collection in an interactive 3D space.



---

## ✨ Features

* **3D Interactive Shelves**: Navigate a warm, acoustically styled listening hall with W/A/S/D movement and orbital controls.

<img width="2533" height="1258" alt="image" src="https://github.com/user-attachments/assets/2a011254-58bf-4130-98a6-e0968f38747e" />

* **Detailed Record Inspection**: Click any record to pull it off the shelf, flip it over to read the back-cover tracklist, or slide out the heavyweight colored vinyl disc.
<img width="1334" height="1041" alt="image" src="https://github.com/user-attachments/assets/415cf3ca-35d1-4a61-8a4c-a7573d3c1456" />
<img width="1096" height="630" alt="axel records" src="https://github.com/user-attachments/assets/3840c82e-5283-48c8-8fc6-f1ed28150642" />


* **Live Catalog Search**: Instantly query albums using built-in integrations with **Apple Music**, **Deezer**, and **MusicBrainz**.

* **Collector Toolkit**: Rate albums, write personal liner notes/memories, log spin counts, customize pressing wax colors, and export/import JSON library backups.
  
---

## Try it out on the website:
https://maxaxel.my.canva.site/axelrecords

---

## 🚀 Installation & Local Development

# **Installation:**

**Just Download the HTML file from releases and run in your browser**

# **For Devlopment:**

Because this project runs as a high-performance static WebGL application with ES modules, you can run it instantly using any local static file server:

1. Clone or download the repository:
```bash
git clone https://github.com/maxioisdead/AxelRecords.git
cd AxelRecords

```


2. Serve via local server (e.g., Python, Node.js http-server, or Live Server in VS Code):
```bash
# Python 3
python3 -m http.server 8000

```


3. Open your browser and navigate to `http://localhost:8000`.

---

## 🔮 Future Vision: Community-Driven Interactive Library

The long-term vision for Axel Records is to transform it from a standalone 3D visualizer into a robust, **community-driven interactive library software**.

We want to empower music collectors, archivists, and crate-diggers to connect directly with external cataloging platforms. The roadmap for the future includes:

* **RateYourMusic (RYM) Integration**: Direct importing of custom RYM CSV exports, lists, and collection URLs so users can seamlessly populate their 3D bookcases with their exact ratings, custom tags, and listening histories.
* **Decentralized Community Sharing**: Allowing users to share custom room configurations, posters, and curated library snapshots with friends.
* **Expanded Metadata Sync**: Deeper integration with music databases for automated liner notes, release variants, and audiophile press details.
* **Collaborative Crate-Digging**: Real-time multi-user listening rooms where friends can browse each other's shelves and drop records onto a shared turntable.

---

## 🛠️ Tech Stack

* **Three.js** (WebGL 3D Rendering Engine & OrbitControls)


* **Tailwind CSS** (Modern UI Styling & Glassmorphism)


* **Web Audio API** (Procedural ambient room soundscapes & vinyl crackle synthesizer)


* **HTML5 Canvas** (Dynamic procedural album covers, spines, back-covers, and colored vinyl wax textures)



---

## 📄 License

Distributed under the **MIT License**. See `LICENSE` for more information.
