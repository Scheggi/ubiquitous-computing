# P5 · Van Laerhoven — „The Data Dilemma" (Wellness-Tracking-Wearables)

**Kristof Van Laerhoven** (Uni Siegen — der Kursleiter) · Nov 2025 · PDF: `papers/vanlaerhoven-data-dilemma.pdf`

## Kernaussage
Sensordaten lassen sich heute ubiquitär leicht sammeln — die Gefahr liegt im **„blinden" Vertrauen in Daten und Annotationen (Labels)**. Nötig sind Fähigkeiten zum **Inspizieren** und **Interpretieren** von Rohdaten („Mind the Gap").

## Zentrale These
Datensammlung ist trivial geworden, doch entscheidend sind die Fragen: Wurde **korrekt** aufgenommen? Was ist **drin**? Gab es **Ausfälle (outages)**? Sowohl **Datenfehler** als auch **Label-Fehler** unterminieren sonst die Ergebnisse.

## Zwei Beispiel-Datensätze
- **WESAD** (Wearable Stress and Affect Detection): 15 Teilnehmer, Zustände **Baseline / Amusement / Meditation / Stress**; Modalitäten ACC, ECG/BVP, EDA, EMG, RESP, TEMP (Wrist + Chest). Ergebnisse: Stress vs. Non-Stress bis **93,1 %**; 3-Klassen bis 80,3 %. (Schmidt, Reiss, … , Van Laerhoven, ICMI 2018 — direkter Bezug zu Healey-Picard.)
- **WEAR** (Outdoor-Sport): >19 h, 22 Teilnehmer, 18 Workout-Aktivitäten, 11 Locations, 4 Jahreszeiten; **egozentrisches Video + IMU**. (ACM IMWUT 2024.)

## Weitere Punkte
- **Label-Errors** auch in „Goldstandard"-Datensätzen: **MNIST** (70k) und **ImageNet** (14,2 M) enthalten falsche Labels.
- **Visual-Inspection-Rezept (7 Schritte):** Python (1. Daten lesen, 2. komprimieren, 3. handhabbares JS-Array) → JavaScript (4. laden, 5. uPlot-Optionen, 6. zeichnen) → 7. **interaktiver HTML-Plot** (= Notebook `exercises/interactive.ipynb`).
- **Homework-Idee:** „data hunting" in WESAD/WEAR — wer hat Sensor-Ausfall, falsche Annotation, sichtbare Herzschläge im Brust-Accelerometer.

## Klausur-Kernpunkte
1. „Data Dilemma": einfache Sammlung ≠ vertrauenswürdige Daten.
2. **Blindes Vertrauen in Daten UND Labels** ist die Gefahr.
3. **WESAD** (Stress, ~93 %) und **WEAR** (Outdoor-Sport, IMU+Video).
4. Selbst MNIST/ImageNet haben Label-Fehler.
5. Lösung: **inspect + interpret** (7-Schritte-uPlot-Rezept).

> Bezug: Vorlesung 06; verbindet Wearable Sensing (P2), Visualisierung (P6/P7) und Datenethik.
