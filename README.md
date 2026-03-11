# 🎮 Critics vs. Consumers
### *Who Really Decides a Game's Success?*

> **An interactive information visualization dashboard** exploring the relationship between critic scores, consumer sales, regional markets, and publisher performance across 2,000+ video game titles from 1985–2016.

[![GitHub](https://img.shields.io/badge/GitHub-7dracoder-181717?style=flat&logo=github)](https://github.com/7dracoder)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![Plotly.js](https://img.shields.io/badge/Plotly.js-3F4F75?style=flat&logo=plotly&logoColor=white)](https://plotly.com/javascript/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

---

## 📖 Overview

**Critics vs. Consumers** is a fully interactive, single-file HTML dashboard built for **Mini-Project 2** of an Information Visualization course. It answers three core research questions:

1. **Do critic scores predict commercial success?** — Or do consumers decide independently?
2. **How have genre preferences shifted over time?** — From the 80s platform era to the 2000s shooter boom
3. **Do regional markets favour different genres?** — NA vs. Europe vs. Japan buying patterns
4. **Which publishers consistently produce quality games?** — By genre specialization

No backend. No build step. Just open an HTML file in your browser.

---

## ✨ Features

- **4 Coordinated Interactive Views** — all charts update together when you apply filters or click
- **Cross-filtering** — click any data point in any view to filter all others simultaneously
- **Dual-handle year range slider** — drag both handles, supports single-year selection
- **Live KPI bar** — total games, global sales, avg critic score, top genre & publisher update in real time
- **Colorblind-safe palette** — Okabe-Ito perceptually uniform colors across all charts
- **Dot size encoding** — scatter plot dot size represents critic review count (not just score)
- **Insight annotations** — contextual takeaways beneath each chart
- **Fully responsive** — works on any screen size
- **Zero dependencies** — only Plotly.js (CDN), no npm, no framework

---

## 📊 The Four Views

| # | View | Chart Type | What It Shows |
|---|------|-----------|---------------|
| 1 | **Genre Dominance Over Time** | Stacked Area | How genre popularity shifted 1985–2016 |
| 2 | **The Critical Disconnect** | Scatter Plot | Critic score vs. global sales (dot = review count) |
| 3 | **A World Divided** | Grouped Bar | Regional sales (NA / EU / Japan) per genre |
| 4 | **Publisher × Genre Matrix** | Heatmap | Avg critic score by publisher and genre |

---

## 🎨 Themes

Five complete visual themes are included — same data, same functionality, different aesthetic:

| File | Theme | Vibe |
|------|-------|------|
| `index.html` | **Default / Retro Arcade** | Neon on dark, Press Start 2P font |
| `index_blueprint.html` | **Blueprint** | Engineering technical drawing, navy + gold |
| `index_cod.html` | **Call of Duty** | Military tactical, olive + orange, Bebas Neue |
| `index_mario.html` | **Super Mario** | Blue sky, brick strips, pixel coins, NES HUD |
| `index_valorant.html` | **Valorant** | Glassmorphism, purple/pink/cyan neon, Orbitron |

---

## 🚀 Getting Started

### Option 1 — Just open it
```bash
# Clone the repo
git clone https://github.com/7dracoder/critics-vs-consumers.git
cd critics-vs-consumers

# Open any theme in your browser
open index_valorant.html      # macOS
start index_valorant.html     # Windows
xdg-open index_valorant.html  # Linux
```

### Option 2 — Serve locally (recommended to avoid CORS issues)
```bash
# Python 3
python -m http.server 8080

# Then open http://localhost:8080/index_valorant.html
```

> ⚠️ **No installation needed.** All dependencies are loaded via CDN (Plotly.js 2.27.0).

---

## 🗂️ Project Structure

```
critics-vs-consumers/
│
├── index.html              # Default retro arcade theme
├── index_blueprint.html    # Blueprint engineering theme
├── index_cod.html          # Call of Duty military theme
├── index_mario.html        # Super Mario theme
├── index_valorant.html     # Valorant theme
│
└── README.md
```

> All logic, styles, and chart rendering are **self-contained** in each HTML file.

---

## 🖱️ How to Use

| Interaction | What Happens |
|---|---|
| **Dropdown — Genre / Publisher / Platform** | Filters all 4 views simultaneously |
| **Year range slider** | Drag left/right handles to set date range; drag both to same point for single year |
| **Click a genre band** in View 1 | Cross-filters all other charts by that genre |
| **Click a dot** in View 2 | Cross-filters by the dot's genre |
| **Click a bar** in View 3 | Cross-filters by that genre |
| **Click a cell** in View 4 | Cross-filters by that genre |
| **"DISENGAGE / CLEAR" badge** | Clears the active cross-filter |
| **↺ Reset button** | Resets all filters to default |

---

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| **HTML5 / CSS3** | Structure & all visual themes |
| **Vanilla JavaScript** | Data generation, state management, event handling |
| **[Plotly.js 2.27.0](https://plotly.com/javascript/)** | All 4 interactive charts (CDN) |
| **Google Fonts** | Press Start 2P, Orbitron, Bebas Neue, Caveat, Share Tech Mono |

---

## 📦 Data

> ⚠️ The current version uses **2,000 simulated data points** generated with a seeded random function to approximate the real dataset's distribution.

To use the **real dataset**:
1. Download from [Kaggle — Video Game Sales with Ratings](https://www.kaggle.com/datasets/rush4ratio/video-game-sales-with-ratings)
2. Replace the `RAW` array generation block in the `<script>` tag with a CSV fetch:

```javascript
fetch('vgsales_with_ratings.csv')
  .then(r => r.text())
  .then(csv => {
    // parse and populate RAW[] here
    redrawAll();
  });
```

---

## 🎓 Academic Context

- **Course:** Information Visualization
- **Assignment:** Mini-Project 2 — Interactive Dashboard
- **Research Questions Addressed:**
  - RQ1: Correlation between critic scores and commercial sales
  - RQ2: Genre popularity trends over time (1985–2016)
  - RQ3: Regional market preferences by genre
  - RQ4: Publisher quality consistency across genres

### Gestalt Principles Applied
- **Proximity** — related views grouped together; filter controls clustered; insight notes directly beneath their charts
- **Enclosure** — each chart enclosed in its own bordered panel; filter group in its own container
- **Similarity** — identical panel border style, same font hierarchy, same chart background across all 4 views

---

## 📄 License

MIT License — feel free to fork, remix, and build on this.

---

<div align="center">
  Made with ☕ by <a href="https://github.com/7dracoder">7dracoder</a>
  <br/>
  <sub>Information Visualization · Mini-Project 2 · 2026</sub>
</div>
