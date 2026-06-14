# Ubiquitous Computing

Kursmaterialien & Klausur-Lernunterlagen für **Ubiquitous Computing** (Uni Siegen, Kristof Van Laerhoven) — Vorlesungsfolien, Paper und Notebooks, plus eine ausführliche modulare Zusammenfassung mit rotem Faden, Lernplan, Übungsfragen und Anki-Karteikarten.

## Ordnerstruktur

```
lectures/    Foliensätze ubicomp_01..07_*.pdf
papers/      Lesematerial (Klausur-Schwerpunkt), <autor>-<thema>.pdf
exercises/   exercise_01_study_design.pdf + 4 Jupyter-Notebooks
summary/     Modulare Zusammenfassung (st2-Stil):
               00_Overview_Zusammenhang.md   ← roter Faden, hier starten
               01..07_*.md                   ← eine Summary pro Vorlesung
               papers/                        ← ⭐ Paper-Summaries (P1..P8)
LERNPLAN_KLAUSUR.md   10-Einheiten-Lernplan
EXAM_PRACTICE.md      Übungsfragen mit Lösungen (inkl. Paper-Tiefenfragen)
anki_papers.tsv       50 Anki-Karteikarten zu den Papern
anki_lectures.tsv     71 Anki-Karteikarten zu den Vorlesungen (V1–V7)
requirements.txt      Python-Abhängigkeiten der Notebooks
```

## Wo anfangen?
1. **`summary/00_Overview_Zusammenhang.md`** — der rote Faden und wie alle Themen zusammenhängen.
2. **`LERNPLAN_KLAUSUR.md`** — 10 Lerneinheiten mit Reihenfolge und Lernzielen.
3. **`summary/papers/`** — die Paper-Summaries (im Exam besonders gefragt).
4. **`EXAM_PRACTICE.md`** + **`anki_papers.tsv`** — zum Selbsttesten.

## Vorlesungen (`lectures/`)
| Datei | Thema | Summary |
|---|---|---|
| `ubicomp_01_introduction.pdf` | Einführung, Weiser-Vision | `summary/01_introduction.md` |
| `ubicomp_02_experiments.pdf` | Studiendesign & Statistik | `summary/02_experiments.md` |
| `ubicomp_03_wearables.pdf` | Wearable Computing | `summary/03_wearables.md` |
| `ubicomp_04_sensor_networks.pdf` | Sensornetze / Smart Dust | `summary/04_sensor_networks.md` |
| `ubicomp_05_physical_interfaces.pdf` | Physical/Tangible Interfaces | `summary/05_physical_interfaces.md` |
| `ubicomp_06_context_activity.pdf` | Context & Activity Recognition | `summary/06_context_activity.md` |
| `ubicomp_07_critical_systems.pdf` | Critical Systems, Security & Privacy | `summary/07_critical_systems.md` |

## Paper (`papers/`) — ⭐ Klausur-Schwerpunkt
Weiser (Computer for the 21st Century) · Healey & Picard (Stress Driving) · Abowd (What next, Ubicomp?) · Knight & Baber (Comfort of Wearables) · Van Laerhoven (Data Dilemma) · Streit & Gehlenborg (Bar/Box, Nature Methods) · Fry (Graphs Life & Death, New Yorker) · Gresham/Matt Jones (AI and Humanity). Summaries: `summary/papers/`.

## Notebooks (`exercises/`)
- `Fitts'_Law.ipynb` — Fitts' Law praktisch (Index of Difficulty, Regression).
- `Locationing_Tags_in_Wireless_Sensor_Networks.ipynb` — BLE-Lokalisierung (RSSI, Trilateration).
- `Bangle.ipynb` — Wearable-Firmware (Espruino Bangle.js).
- `interactive.ipynb` — große Sensor-Timeseries mit uPlot.

## Setup (für die Notebooks)
```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook
```

> `.venv/` und Jupyter-Checkpoints sind git-ignoriert. `interactive.ipynb` importiert `google.colab` (Colab-only) für den finalen Download-Schritt.
