# P6 · Streit & Gehlenborg — „Bar charts and box plots" (Nature Methods)

**Marc Streit** (JKU Linz) & **Nils Gehlenborg** (Harvard) · *Nature Methods* 11(2), Feb 2014, „Points of View" · PDF: `papers/streit-gehlenborg-bar-box-plots.pdf` (= ehem. `nmeth.2807.pdf`)

## Kernaussage
Die Wahl des Diagramms hängt von **Natur der Daten und Aufgabe** ab: **Bar charts für Counts, Box plots für Verteilungen.**

## Bar charts (kodieren Menge über **Länge**)
- **Stacked:** Gesamtmengen über Items + Beitrag der Kategorien.
- **Layered:** Vergleich **innerhalb** einer Kategorie (gemeinsame Baseline).
- **Grouped:** Werte über Kategorien innerhalb eines Items.
- **Pie chart** (winkelbasiert) **vermeiden** — Länge wird genauer wahrgenommen als Winkel.

## Box plot (box-and-whiskers) — kodiert **5 Werte**
- Box von **Q1 bis Q3** = **IQR**; Linie = **Median**; Whiskers typ. bis **Q1−1,5·IQR** und **Q3+1,5·IQR**; Ausreißer als Einzelmarken.
- **Whisker-Range immer annotieren.**

## Wichtiger Fehler
**Bar chart + Error Bar** für gesampelte Daten ist **irreführend**: der Balken startet bei 0 und suggeriert, der ganze Bereich sei beobachtet — Teile davon wurden evtl. nie gemessen. → Für Verteilungen Box plot nutzen.

## Empfehlungen
Balken nach Höhe / Boxen nach Median ordnen · Null als Baseline für Bars · Tick Marks / leichte Gridlines · solide Füllung ohne Outlines · **max. 8–12 Farben**.

## Klausur-Kernpunkte
1. **Bar = Counts, Box = Verteilungen.**
2. Box plot kodiert 5 Werte: Q1, Q3 (IQR), Median, 2 Whisker-Enden (±1,5·IQR).
3. Stacked/Layered/Grouped unterscheiden.
4. Länge > Winkel (Bar statt Pie).
5. **Bar + Error Bar für gesampelte Daten = irreführend** (Baseline-0-Problem).
6. Whisker-Range immer angeben; max. 8–12 Farben.

> Bezug: Vorlesung 02 (Boxplot/Verteilungen) & 06; verwandt mit Fry (P7) und Data Dilemma (P5).
