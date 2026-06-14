# P7 · Fry — „When Graphs Are a Matter of Life and Death" (The New Yorker)

**Hannah Fry** · *The New Yorker*, 14. Juni 2021 (Rezension von Friendly & Wainer, „A History of Data Visualization") · PDF: `papers/fry-graphs-life-death-newyorker.pdf`

## Kernaussage
Datenvisualisierung ist keine Dekoration — sie macht Unsichtbares sichtbar und kann buchstäblich über **Leben und Tod** entscheiden. „Only a graph speaks directly to the eyes." Aber: **was ein Graph weglässt** (Scope of Relevance), kann fatal sein.

## Schlüsselbeispiel — Challenger (1986) ⭐
- Streudiagramm Temperatur vs. O-Ring-/Engine-Schaden. Die **17 Flüge OHNE Ausfall** wurden **nicht** eingezeichnet.
- Ohne sie war der Trend „Kälte → Versagen" unsichtbar → Start bei Kälte → O-Ringe versagten → **7 Tote**.
- **Edward Tufte** nutzte dies als Paradebeispiel für falsche Datendarstellung.
- **Lehre: immer nach den fehlenden Daten fragen.**

## Weitere historische Stationen
- **Van Langren (1628):** (wahrscheinlich) **erster statistischer Graph** — 1D-Linie mit 12 Längengrad-Schätzungen Toledo–Rom, zeigte deren Streuung.
- **William Playfair (1786):** erfand **Linien-, Balken- und (später) Tortendiagramm**; Zeit auf der x-Achse.
- **Charles Ibry (1847):** Zug-Fahrplan-Graph (Zeit-Distanz); Züge als diagonale Linien, **Kreuzungen = Kollisionen** (2016 noch genutzt, Singapur „rogue train").
- **Scatter Plot** (Tufte: „greatest of all graphical designs"): Distanz kodiert **Ähnlichkeit** (Cluster), nicht physische Nähe → Hertzsprung-Russell-Diagramm; Brücke zu **hochdimensionalem ML/Clustering**.

## Klausur-Kernpunkte
1. **Challenger:** die nicht gezeigten **17 „kein Ausfall"-Punkte** hätten das Risiko sichtbar gemacht.
2. „Only a graph speaks directly to the eyes"; Tufte: Scatter = „greatest of all graphical designs".
3. **Van Langren (1628)** = erster statistischer Graph.
4. **Playfair** = Erfinder von Linien-/Balken-/Tortendiagramm.
5. **Ibry** = Zug-Zeit-Distanz-Graph, Kreuzungen = Kollisionen.
6. Scatter: Distanz = **Ähnlichkeit** → Brücke zum ML.
7. Kernlehre: **immer fragen, welche Daten fehlen.**

> Bezug: Vorlesung 02 (Datenvisualisierung/Studiendesign); verwandt mit Nature Methods (P6) & Data Dilemma (P5).
