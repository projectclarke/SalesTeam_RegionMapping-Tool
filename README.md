# UK Sales Territory Planner — Single-File App

A lightweight, **single HTML file** for plotting and assigning **UK sales territories**. Supports three layers:

- **Counties & Unitary Authorities** (ONS, Dec 2023 BUC — fetched live)
- **Postcodes** (embedded KML you provide)
- **Regions** (derived from postcode **areas** via an editable mapping)

You can **select areas**, **assign rep + colour**, manage assignments (**Clear ALL**, **per-rep Clear**), and **export** the current map as **JPG** or **A1 PDF**. Assignments **persist locally** between sessions.

There is an example JSON file that will demonstrate the function of the app by highlighting the UK regions when loaded.  

---

## ✨ Features

- **Zero-install**: open a single `.html` file in Chrome/Edge — no build, no server.
- **Layers**:
  - *Counties & UAs*: live fetch from ONS Open Geography (Dec 2023, BUC).
  - *Postcodes*: embedded KML (kept private to you — not redistributed).
  - *Regions*: dynamically grouped from postcode areas (e.g., `AB`, `NW`, `YO`).
- **Selection & Assignment**:
  - Click polygons; **Shift/Ctrl** for multi-select.
  - Assign selected to **Rep (name)** with a **colour**; centroid labels render the rep’s name.
- **Legend / Summary**:
  - Per-rep count + **“Clear”** button to remove just that rep’s territories.
  - **Clear ALL** nukes all assignments across all layers.
- **Persistence & Export**:
  - Saves to `localStorage` (survives close/reopen).
  - **Export / Import JSON** (round-trip), **Export CSV** (summary).
  - **High-res Export JPG** and **A1 PDF** (594×841 mm) with scale control (1×–4×).
- **No zoom jump**: the app auto-fits once when you press **USE** for a layer; clicks never change zoom.

---

## 🚀 Quick Start

1. **Download** the single-file build (e.g., `uk-territory-planner-preloaded-v1.5.1.html`).
2. **Open** it in a modern browser (Chrome or Edge recommended).
3. Choose a layer:
   - **Use Counties** (ONS live)
   - **Use Postcodes** (embedded KML)
   - **Use Regions** (derived from postcodes)
4. Type a **Rep name**, choose a **colour**, select areas (list or map), then click **Assign selected**.
5. **Export** as needed:
   - Assignments: **JSON / CSV**
   - Map: **JPG / A1 PDF** (use the **Resolution scale** dropdown for higher detail)

> Tip: Very high export scales (3×–4×) can be memory heavy. Start at **2×**.

---

## 🧭 UI Overview

- **Toolbar**
  - **Use Counties / Postcodes / Regions**
  - **Import JSON** (restore a previous plan)
  - **Export JSON / CSV**
  - **Clear ALL** (removes every assignment)
- **Select areas**
  - Search filter, list (multi-select with Shift/Ctrl), and map clicks
- **Assign to Sales Rep**
  - Name + Colour → **Assign selected**
  - **Unassign selected** (only selected features)
- **Legend / Summary**
  - Per-rep colour swatch + count + **Clear** (just that rep)
- **Export**
  - **JPG** and **A1 PDF** with scale control (1×–4×)

---

## 💾 Persistence

Assignments are stored as a serialised `Map` in browser **localStorage**:

