# 🎮 Critics vs. Consumers
### *Who Really Decides a Game's Success?*

> An interactive information visualization dashboard exploring the relationship between critic scores, consumer sales, regional markets, and publisher performance across 2,000+ video game titles from 1985–2016.

[![GitHub](https://img.shields.io/badge/GitHub-7dracoder-181717?style=flat&logo=github)](https://github.com/7dracoder)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![Plotly.js](https://img.shields.io/badge/Plotly.js-3F4F75?style=flat&logo=plotly&logoColor=white)](https://plotly.com/javascript/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

---

## 📖 Overview

**Critics vs. Consumers** is a fully interactive, single-file HTML dashboard built for **Mini-Project 2** of an Information Visualization course. It answers four core research questions:

1. **Do critic scores predict commercial success?** — Or do consumers decide independently?
2. **How have genre preferences shifted over time?** — From the 80s platform era to the 2000s shooter boom
3. **Do regional markets favour different genres?** — NA vs. Europe vs. Japan buying patterns
4. **Which publishers consistently produce quality games?** — By genre specialization

No backend. No build step. Just open `index.html` in your browser.

---

## 📊 The Four Views

| # | View | Chart Type | What It Shows |
|---|------|-----------|---------------|
| 1 | **Genre Dominance Over Time** | Stacked Area | How genre popularity shifted 1985–2016 |
| 2 | **The Critical Disconnect** | Scatter Plot | Critic score vs. global sales · dot size = review count |
| 3 | **A World Divided** | Grouped Bar | Avg sales per game across N. America, Europe & Japan |
| 4 | **Publisher × Genre Matrix** | Heatmap | Avg critic score by publisher and genre |

---

## ✨ Features

- **4 coordinated interactive views** — all charts update together on every filter change
- **Cross-filtering from any view** — click a genre band, scatter dot, bar, or heatmap cell to filter all others
- **Dual-handle year range slider** — drag both handles independently; supports single-year selection
- **Live KPI bar** — total games, global sales, avg critic score, top genre & top publisher update in real time
- **Colorblind-safe palette** — Okabe-Ito perceptually uniform colors across all charts
- **Dot size encoding** — scatter plot dot size encodes critic review count
- **Active cross-filter badge** — shows which genre is locked with a one-click dismiss button
- **Fully responsive layout** — adapts to any screen size
- **Zero dependencies** — only Plotly.js via CDN, no npm, no framework, no build tools

---

## 🚀 Getting Started

### Option 1 — Just open it
```bash
git clone https://github.com/7dracoder/critics-vs-consumers.git
cd critics-vs-consumers
open index.html        # macOS
start index.html       # Windows
xdg-open index.html    # Linux
```

### Option 2 — Serve locally *(recommended)*
```bash
python -m http.server 8080
# Then visit: http://localhost:8080
```

> ⚠️ No installation required. Plotly.js 2.27.0 is loaded from CDN.

---

## 🖱️ Interactions

| Action | Effect |
|--------|--------|
| **Genre / Publisher / Platform dropdowns** | Filters all 4 views simultaneously |
| **Year range slider — left handle** | Sets the start year |
| **Year range slider — right handle** | Sets the end year |
| **Drag both handles to same point** | Shows data for a single year |
| **Click a genre band** in View 1 | Cross-filters all charts by that genre |
| **Click a dot** in View 2 | Cross-filters all charts by that genre |
| **Click a bar** in View 3 | Cross-filters all charts by that genre |
| **Click a cell** in View 4 | Cross-filters all charts by that genre |
| **DISENGAGE button** | Clears the active cross-filter |
| **↺ RESET button** | Resets all filters and cross-filters to default |

---

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| **HTML5 / CSS3** | Structure and all visual styling |
| **Vanilla JavaScript** | Data generation, state management, event handling |
| **[Plotly.js 2.27.0](https://plotly.com/javascript/)** | All 4 interactive charts (loaded via CDN) |
| **Google Fonts** | Bebas Neue, Oswald, Share Tech Mono |

---

## 📦 Data

> ⚠️ The current version uses **2,000 simulated data points** generated with a seeded random function that approximates the real dataset's distribution (genre weights, publisher biases, regional sales ratios).

To use the **real Kaggle dataset**:
1. Download from [Video Game Sales with Ratings — Kaggle](https://www.kaggle.com/datasets/rush4ratio/video-game-sales-with-ratings)
2. Replace the `RAW` array generation block in the `<script>` tag with a CSV fetch:

```javascript
fetch('vgsales_with_ratings.csv')
  .then(r => r.text())
  .then(csv => {
    // parse rows into RAW[] with fields:
    // { yr, genre, pub, plat, cs, cc, na, eu, jp, gs }
    redrawAll();
  });
```

---

## 🎓 Academic Context

- **Course:** Information Visualization
- **Assignment:** Mini-Project 2 — Interactive Dashboard
- **Research Questions:**
  - RQ1: Does critic score correlate with global sales?
  - RQ2: How has genre dominance changed from 1985–2016?
  - RQ3: Do regional markets (NA / EU / Japan) favour different genres?
  - RQ4: Which publishers score highest in which genres?

### Design Principles Applied
- **Gestalt — Proximity:** Filter controls grouped together; insight notes placed directly beneath their charts; related views grouped under section labels
- **Gestalt — Enclosure:** Each chart enclosed in its own bordered panel; filter group in its own container
- **Gestalt — Similarity:** Identical panel style, font hierarchy, and chart background across all 4 views
- **Visual Hierarchy:** Title → KPI bar → Section labels → Charts → Insight notes
- **Effective Whitespace:** Generous padding between sections; grouped views separated from each other

---

## 📁 File Structure

```
critics-vs-consumers/
│
├── index.html      # Complete dashboard — open this in your browser
└── README.md
```

---

## 📄 License

MIT License — free to fork, remix, and build on.

---

<div align="center">
  Made by <a href="https://github.com/7dracoder">7dracoder</a>
  <br/>
  <sub>Information Visualization · Mini-Project 2 · 2026</sub>
</div>
