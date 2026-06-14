# Lernplan Klausur — Ubiquitous Computing

> 10 Lerneinheiten (je ~90–120 min). Strategie: erst Überblick & Methodik (≈ halbe Klausur aus Übungen), dann Vorlesungen, **Paper-Schwerpunkt**, dann zwei Wiederholungsrunden mit aktivem Abruf. Beende jede Einheit mit 3–5 selbstgestellten Fragen.
>
> Material: `summary/` (Overview + 01–07 + `papers/`), Übungsfragen `EXAM_PRACTICE.md`, Karteikarten `anki_papers.tsv`.

| LE | Thema | Material | Aktives Lernziel |
|----|-------|----------|------------------|
| **1** | Big Picture + V1 | `summary/00_Overview` + `01_introduction` + `papers/P1_weiser` | 3 Eras + 3 Definitions-Säulen erklären; „warum UbiComp = Umkehrung der VR?" |
| **2** | Methodik I: Studiendesign | `summary/02_experiments` + `exercises/exercise_01_study_design.pdf` | Eigene Mini-Studie in 5 Schritten entwerfen |
| **3** | Methodik II: Statistik & Designtypen | `summary/02_experiments` | Boxplot zeichnen; within vs. between; „warum Lanarkshire wertlos?" |
| **4** | V3 Wearables | `summary/03_wearables` + `papers/P2`, `P4` | Rhodes-Eigenschaften + REBA/Borg/CRS; „Smartphone = Wearable?" |
| **5** | V4 Sensornetze / Smart Dust | `summary/04_sensor_networks` | Interrupt-Ablauf, Protothreads, X-MAC vs. ContikiMAC |
| **6** | V5 Physical/Tangible Interfaces | `summary/05_physical_interfaces` + `papers/P8` | Fitts (log) vs. Steering (linear); Norman's 7 Stages |
| **7** | V6 Context & Activity Recognition | `summary/06_context_activity` + `papers/P5` | Konfusionsmatrix + Precision/Recall/F1 rechnen |
| **8** | V7 Critical Systems & Security | `summary/07_critical_systems` | 4 Fallstudien je Ursache + Lehre |
| **9** | ⭐ Paper-Vertiefung (Klausur-Schwerpunkt) | `summary/papers/` komplett + `EXAM_PRACTICE.md` Teil E + Anki | Jedes Paper einer Vorlesung zuordnen + Querverbindung; alle Zahlen sitzen |
| **10** | Prüfungssimulation & Lückenschluss | `EXAM_PRACTICE.md` (geschlossen) | Probe-Test ohne Unterlagen, dann gezielt Lücken füllen |

## Endspurt-Tipps
- **Paper werden besonders abgefragt** → LE 9 doppelt gewichten; `anki_papers.tsv` täglich wiederholen.
- **Übungen = ~½ der Klausur** → Methodik (LE 2–3) + Activity-Pipeline-Rechnungen (LE 7) ernst nehmen.
- **Formeln aktiv können:** Fitts `log₂(1+D/W)`, Steering (linear), KLM-Zeiten, Precision/Recall/F1, RSSI `-50-20·log₁₀(d)`.
- **Karteikarten Namen/Jahre:** Weiser/PARC, Gibson/Norman, Pister, Dunkels, Fitts/MacKenzie, Shneiderman, Dey & Abowd, Healey & Picard, Mann, Bush, Rhodes.
- **Zahlen, die gern drankommen:** 97,4 % (Healey-Picard) · 6 CRS-Dimensionen · 4 Sensoren · 17 Challenger-Punkte · 5 Box-Plot-Werte · 7±2 Chunks.
