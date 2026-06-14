# 06 · Context Awareness & Activity Recognition

## Worum geht's
Vom abstrakten Kontext zur konkreten Aktivitätserkennung: Definitionen → frühe Systeme → vollständige **Klassifikations-Pipeline** (Daten → Features → Klassifikator → Evaluation → Ground Truth).

## Kernkonzepte
- **Context-aware computing** (Schilit & Theimer 1994): Fähigkeit, Umgebungsänderungen zu entdecken und darauf zu reagieren.
- **Context (Dey & Abowd 2000):** „jede Information, die die Situation einer Entität (Person, Ort, Objekt) charakterisiert" — breiteste/anerkannteste Definition.
- **Nutzen von Kontext:** gemeinsames Verständnis · **implizite Interaktion** (keine langen Befehle nötig) · Vermeidung von Fehlinterpretationen.
- **Frühe Systeme:** **Active Badge** (Ultraschall-Lokalisierung) · **Stick-e Notes** (kontextabhängige Dokumente) · **Cooltown** (HP, Web-Präsenz für Dinge) · **TEA** (Sensoren im Telefon-Akku → Profil-Switching).
- **Activity Recognition:** Erkennen von **Actions & Goals** aus einer Beobachtungsserie. Schwerpunktverschiebung: **Machbarkeit → Genauigkeit → Usability/Durability**.
- **Labor ≠ Realität:** Sloth (15,85 h vs. 9,63 h Schlaf), White-Coat-Hypertension. **4 Pitfalls:** wrong environment, intrusive sensors, wrong users, insufficient samples.

## Pipeline
- **Curse of Dimensionality:** mehr Sensoren = bessere Trennbarkeit, aber exponentiell wachsendes Volumen → Daten sparser.
- **Feature** = messbare, möglichst **discriminating** Eigenschaft. Magnitude `√(x²+y²+z²)`; über Sliding Window: Min/Max/**Mean/Variance**.
- **Klassifikatoren:**
  - **kNN:** nächster Nachbar (euklidische Distanz); k Nachbarn → Voting.
  - **weighted kNN:** Distanzen als Gewichte, **argmax** der Gewichtssummen pro Klasse.
  - **Gauss-Modell:** pro Klasse nur **μ und Σ** speichern.
- **Evaluation — Konfusionsmatrix (TP/TN/FP/FN):**
  - **Accuracy** = (TP+TN)/alle
  - **Precision** = TP/(TP+FP) — „wie oft war eine Detektion richtig?"
  - **Recall** = TP/(TP+FN) — „wie gut auf der Zielklasse?"
  - **F1** = 2·P·R/(P+R) — harmonisches Mittel.
  - **Accuracy täuscht bei Class Imbalance!** (Rauchen: Dummy-Klassifikator 99,3 % Accuracy, aber P/R/F1 = 0 %.)
- **n-Fold Cross Validation:** jeder Teil wird mal Trainings-, mal Testdaten (3-fold: 2 trainieren, 1 testen, mitteln).
- **Ground Truth:** **Time Diary** · **Experience Sampling** (Alarm alle 15–30 min) · **Self Recall** (abends). Verzerrungen: Peak-End-Rule, Mood-congruent, Digit Bias.

## Klausur-Kernaussagen
Dey-&-Abowd-Definition · implizite Interaktion · 4 Pitfalls · Curse of Dimensionality · discriminating Features · kNN/weighted kNN/Gauss · **P/R/F1 schlägt Accuracy bei Imbalance** · Cross-Validation · 3 Ground-Truth-Methoden.

→ Paper: `summary/papers/P2_healey_picard.md`, `P5_data_dilemma.md`; Praxis: `exercises/interactive.ipynb`
