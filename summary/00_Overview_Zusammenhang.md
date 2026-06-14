# Ubiquitous Computing — Themenübersicht & Zusammenhänge

**Uni Siegen · Kristof Van Laerhoven**

Diese Datei gibt den roten Faden. Einzelzusammenfassungen liegen im selben Ordner (`01_…` bis `07_…`), die **Paper-Summaries** (Klausur-Schwerpunkt!) in `summary/papers/`. Lernplan: `../LERNPLAN_KLAUSUR.md`, Übungsfragen: `../EXAM_PRACTICE.md`.

> ⚠️ **Klausur-Hinweis:** Laut Vorlesung 1 kommt **~½ der Klausur aus den Übungen** (Forschungsmethoden, Paper-Lesen, …), und **insbesondere die Paper werden abgefragt** → `summary/papers/` doppelt ernst nehmen.

---

## Die große Struktur: eine durchgehende Geschichte

```
(1) VISION            Was ist UbiComp?           Weiser: Computer verschwinden, 3. Ära
        │
(2) METHODE           Wie beweise ich, dass es    Experimente, Statistik, Studiendesign
        │             funktioniert?               (≈ halbe Klausur!)
        │
   ┌────┴─────────── DIE HARDWARE-WELT ───────────────┐
(3) AM KÖRPER         Wearables                   Intelligence Augmentation, Ergonomie
(4) IN DER UMWELT     Sensornetze / Smart Dust    Energie, Protothreads, MAC
        │
(5) SCHNITTSTELLE     Physical/Tangible Interfaces Mensch-Physiologie, Fitts, Norman
        │
(6) BEDEUTUNG         Context & Activity          Sensordaten → Klassifikation → Aktivität
        │
(7) VERANTWORTUNG     Critical Systems / Security  Therac-25, Stuxnet, Privacy
```

**Leitidee (Weiser):** *„The most profound technologies are those that disappear."* Alle 7 Kapitel beantworten, **was nötig ist, damit Computer in den Alltag verschwinden**: sie müssen am Körper (3) oder in der Umwelt (4) sitzen, gut bedienbar sein (5), Kontext verstehen (6) und dürfen nicht versagen/spionieren (7) — und alles muss empirisch sauber belegt sein (2).

---

## Wie die Themen zusammenhängen (rote Fäden)

| Roter Faden | Tritt auf in | Kerngedanke |
|---|---|---|
| **„Unsichtbar / verschwinden"** | 01, Paper Weiser & Abowd | Vision (Weiser) → ist erfüllt, weil Ideen das ganze Computing durchdringen (Abowd) |
| **Fitts' Law** | 03 (beim Gehen), 05 (Modell), Notebook | `T=a+b·log₂(1+D/W)`; gilt auch mobil (−35 % beim Gehen) |
| **Affordance** | 01 (Definition), 05 (Design) | Gibson 1979 → Norman (HCI); Designhinweis ohne Erklärung |
| **Labor ≠ Realität / „in the wild"** | 02, 06, Paper Knight & Data Dilemma | Labor erklärt ~20 % der Alltagsvarianz; Feld>Labor (Komfort, Stress) |
| **Sensing-Pipeline** | 06, Paper Healey-Picard & Data Dilemma | Rohdaten → Features → Klassifikator (kNN/Gauss) → Eval (P/R/F1) |
| **Datenvisualisierung & -ethik** | 02, Paper Nature Methods, Fry, Data Dilemma | Bar=Counts/Box=Verteilung; „frag nach den fehlenden Daten"; Labels nicht blind trauen |
| **Statistik/Studiendesign** | 02, Exercise 01 | Variablen, Nullhypothese, within/between, p≤5 %, Boxplot |
| **Privacy/Security** | 03 (Sousveillance), 07 (Stuxnet, SCADA) | Wer trackt wen? + Versagensmuster kritischer Systeme |

---

## Die drei Querthemen des Kurses

1. **Sensing & Machine Learning** auf Menschen/Umwelt (V3, V4, V6 + Healey-Picard, Data Dilemma).
2. **Datenvisualisierung & Datenethik** — „traue Daten/Labels nicht blind" (V2 + Nature Methods, Fry, Data Dilemma).
3. **Evaluation in the wild** statt nur im Labor (V2, V6 + Knight, Data Dilemma).

---

## Paper → Vorlesung (für „Ordne zu"-Fragen)

| Paper (Datei in `papers/`) | gehört zu | wichtigste Zahl/Fakt |
|---|---|---|
| Weiser, *Computer for the 21st Century* | V1 | Tabs/Pads/Boards; Location + Scale |
| Healey & Picard, *Stress Driving* | V3/V6 | 4 Sensoren, **97,4 %** |
| Abowd, *What next, Ubicomp?* | V1 (Reflexion) | „your noise is my signal"; 4. Gen = conjoined |
| Knight & Baber, *Comfort of Wearables* | V3 | **6 CRS-Dimensionen**; Feld>Labor |
| Van Laerhoven, *Data Dilemma* | V6 | WESAD ~93 %; Label-Fehler MNIST/ImageNet |
| Streit & Gehlenborg, *Bar/Box* (Nature Methods) | V2/V6 | Bar=Counts, Box=Verteilung; 5 Box-Werte |
| Fry, *Graphs Life & Death* (New Yorker) | V2 | Challenger: 17 fehlende Punkte |
| Gresham/Matt Jones, *AI and Humanity* | V1/V5 | prädiktiv; kein episodisches Gedächtnis |
| Exercise 01, *Study Design* | V2 | 5 Schritte; Nullhypothese; p<0,05 |

---

## Ordnerstruktur

```
lectures/   ubicomp_01..07_*.pdf       (Foliensätze)
papers/     <autor>-<thema>.pdf        (Lesematerial — Klausur-Schwerpunkt)
exercises/  exercise_01_study_design.pdf + 4 Notebooks
summary/    00_Overview + 01..07 Lecture-Summaries
summary/papers/  00_papers_overview + P1..P8 Paper-Summaries
LERNPLAN_KLAUSUR.md · EXAM_PRACTICE.md · anki_papers.tsv
```
