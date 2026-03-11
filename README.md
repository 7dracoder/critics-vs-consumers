# 🎮 Critics vs. Consumers
### Video Game Market Intelligence Dashboard

> *Does a higher critic score actually sell more games? This dashboard finds out.*

![Dashboard](https://img.shields.io/badge/Status-Live-00ff88?style=for-the-badge)
![HTML](https://img.shields.io/badge/Built%20With-HTML%2FJS-ff2d78?style=for-the-badge)
![Plotly](https://img.shields.io/badge/Charts-Plotly.js-00e5ff?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-ffe600?style=for-the-badge)

---

## 🕹️ Live Demo

👉 **[View Dashboard](https://YOUR-USERNAME.github.io/critics-vs-consumers)**
*(Replace with your actual GitHub Pages URL after deploying)*

---

## 📌 About

**Critics vs. Consumers** is an interactive information visualization dashboard exploring 40+ years of video game sales data (1985–2016). It investigates the tension between **critical acclaim** and **commercial success** across genres, publishers, platforms, and global regions.

Built for **Mini-Project 2** of an Information Visualization course, applying:
- Gestalt principles (proximity, enclosure, similarity)
- Cleveland & McGill visual encoding hierarchy
- Expressiveness & Effectiveness principles

---

## 🔬 Research Questions

1. How has genre popularity evolved over time in terms of global sales?
2. Is there a measurable correlation between critic scores and commercial success?
3. How do regional markets (NA, EU, Japan) differ in genre preferences?
4. Which publishers consistently achieve high critic scores across multiple genres?

---

## 📊 Dashboard Views

| View | Chart Type | What It Shows |
|------|-----------|---------------|
| **① Genre Dominance Over Time** | Stacked Area | Genre sales trends 1985–2016 |
| **② The Critical Disconnect** | Scatter Plot | Critic score vs. global sales per game |
| **③ A World Divided** | Grouped Bar | NA / EU / Japan sales split by genre |
| **④ Publisher × Genre Matrix** | Heatmap | Avg critic score per publisher per genre |

---

## 🕹️ Interactions

| Control | What It Does |
|---------|-------------|
| **Genre dropdown** | Cross-filters all 4 views |
| **Publisher dropdown** | Cross-filters all 4 views |
| **Platform dropdown** | Cross-filters all 4 views |
| **Year Min / Max sliders** | Narrows the time window across all views |
| **Click genre band (View 1)** | Highlights that genre across all views |
| **↺ Reset button** | Clears all filters instantly |
| **Hover any chart** | Shows detailed tooltip for that data point |

---

## 🗂️ Project Structure

```
critics-vs-consumers/
│
├── index.html        ← Entire dashboard (self-contained, no build step)
├── README.md         ← This file
└── vercel.json       ← Optional: Vercel deployment config
```

---

## 🚀 Run Locally

No installation required. Just:

```bash
# Option 1 — Simply double-click index.html in your file explorer

# Option 2 — Serve with Python
python -m http.server 8000
# Then open http://localhost:8000
```

---

## 🌐 Deploy to GitHub Pages

1. Push this repo to GitHub (must be **Public**)
2. Go to **Settings → Pages**
3. Set Source to **`main` branch → / (root)**
4. Click **Save** — live in ~60 seconds at:
   `https://YOUR-USERNAME.github.io/critics-vs-consumers`

---

## 📦 Replace Simulated Data with Real Data

This dashboard currently uses procedurally generated data. To use real data:

1. Download the dataset from Kaggle:
   [Video Game Sales with Ratings](https://www.kaggle.com/datasets/rush4ratio/video-game-sales-with-ratings)

2. Convert `vgsales-12-4-2019.csv` to JSON:
```python
import pandas as pd, json
df = pd.read_csv('vgsales-12-4-2019.csv').dropna()
df.to_json('data.json', orient='records')
```

3. In `index.html`, replace the `// SIMULATED DATA` block with:
```javascript
const response = await fetch('data.json');
const RAW = await response.json();
```

---

## 🎨 Design Decisions

| Principle | Application |
|-----------|------------|
| **Proximity** | Filter controls grouped tightly; insight notes directly below each chart |
| **Enclosure** | Each panel boxed with neon border; filter bar enclosed separately |
| **Similarity** | All 4 panels share identical border/tag style |
| **Visual Hierarchy** | Title → KPIs → Section Labels → Charts → Insight Notes |
| **Effectiveness** | Position (most important) used for sales/score axes |
| **Expressiveness** | Color hue for categorical genre; position for quantitative sales |

---

## 🛠️ Built With

- [Plotly.js](https://plotly.com/javascript/) — interactive charts
- [Press Start 2P](https://fonts.google.com/specimen/Press+Start+2P) — pixel font
- [Share Tech Mono](https://fonts.google.com/specimen/Share+Tech+Mono) — monospace body font
- Pure HTML / CSS / JavaScript — zero dependencies, no build step

---

## 📄 License

MIT — free to use, modify, and distribute.

---

<div align="center">
  <strong>INSERT COIN TO CONTINUE ▮</strong><br/>
  Made with 🎮 for Information Visualization · 2026
</div>
