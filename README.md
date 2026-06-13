# Ubiquitous Computing

Course materials for a **Ubiquitous Computing** class — interactive Jupyter notebooks, lecture slides, and foundational research papers covering sensing, wearables, indoor localization, human–computer interaction, and data visualization.

## Setup

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook
```

> `.venv/` and Jupyter checkpoints are git-ignored (see `.gitignore`).

## Notebooks

| Notebook | Topic |
|---|---|
| [`Fitts'_Law.ipynb`](Fitts'_Law.ipynb) | Interactive HCI demo. A click-the-target canvas records movement times, then derives **Fitts' Law** `T = a + b·log₂(1 + D/W)` via linear regression, with sliders to explore the `a`/`b` parameters. |
| [`Locationing_Tags_in_Wireless_Sensor_Networks.ipynb`](Locationing_Tags_in_Wireless_Sensor_Networks.ipynb) | BLE indoor positioning simulation. Uses the **RSSI log-distance path-loss model** and **trilateration** to estimate a moving tag's position from three scanners, with an animated heatmap. |
| [`Bangle.ipynb`](Bangle.ipynb) | Wearable firmware prototyping on the **Espruino Bangle.js** smartwatch. JavaScript running on-device via WebBLE: a buzzer/stopwatch app, code minifying, RAM/compiled/JIT/inline-C performance, and broadcasting heart rate over BLE advertisements. |
| [`interactive.ipynb`](interactive.ipynb) | Inspecting large multi-modal sensor data. Shows why matplotlib/Plotly don't scale to long timeseries, then offloads to the lightweight **uPlot** JS library with pre-quantized data to render millions of points smoothly. (Originally a Colab notebook.) |

## Lecture slides

- `UbiComp_01.pdf` … `UbiComp_07.pdf` — the main course lecture series.
- `02-weiser-computer-21st-century.pdf` — Mark Weiser's *The Computer for the 21st Century*, the founding paper of the field.
- `Gresham Lecture by Matt Jones.pdf`, `whatnext.pdf` — talks / essays.

## Papers & readings

- `05.healey-picard.pdf` — Healey & Picard, affective computing / stress detection while driving.
- `2025_10_DataDilemma.pdf` — data ethics and privacy.
- `nmeth.2807.pdf` — *Nature Methods* paper on data presentation.
- `When Graphs Are a Matter of Life and Death _ The New Yorker.pdf` — data-visualization essay.
- `Exercise_01_StudyDesign.pdf` — study-design exercise sheet.
- `download.pdf`, `UbiComp_03_.pdf` — additional course readings.

## Dependencies

See [`requirements.txt`](requirements.txt): numpy, matplotlib, plotly, ipywidgets, jsmin, jupyter, notebook.

> Note: `interactive.ipynb` imports `google.colab` for its final download step, which only runs on Google Colab; the rest works locally.
