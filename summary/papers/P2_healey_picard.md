# P2 · Healey & Picard — „Detecting Stress During Real-World Driving Tasks"

**Jennifer Healey** (HP) & **Rosalind Picard** (MIT, Begründerin des **Affective Computing**) · ~2005, IEEE Trans. Intelligent Transportation Systems · PDF: `papers/healey-picard-stress-driving.pdf`

## Kernaussage
Physiologische Sensoren können den Stresslevel eines Autofahrers unter **realen** Fahrbedingungen zuverlässig bestimmen — drei Stresslevel mit **97,4 %** Genauigkeit; **Hautleitfähigkeit + Herzrate** korrelieren am stärksten mit Fahrerstress.

## Setup — Sensoren (4 Typen / 5 Sensoren)
| Sensor | Stelle | Abtastrate |
|---|---|---|
| **EKG** (Herz, HR + HRV) | modif. Lead-II | 496 Hz |
| **EMG** (Muskel) | Trapezius/Schulter | 15,5 Hz |
| **Skin Conductivity / EDA / GSR** | Handfläche **und** Fußsohle (2 Stellen) | 31 Hz |
| **Respiration** (Atmung) | Hall-Sensor ums Zwerchfell | 31 Hz |

Hardware: FlexComp-ADC, eingebetteter Rechner in modifiziertem **Volvo S70**.

## Fahrprotokoll & Validierung
- **3 Stresslevel:** **Rest** (niedrig, 2×15 min Stand, Augen zu) · **Highway** (mittel) · **City** (hoch). >20 Meilen Boston; 24 vollständige Datensätze.
- **Validierung 1 — Fragebogen:** Rest 1,16 / Highway 2,00 / City 2,55 (ANOVA signifikant).
- **Validierung 2 — Video-Coding:** Stressindikatoren/min **13,6 / 61,4 / 87,7**; Inter-Coder-Reliabilität α = 0,91–1,0.

## Analyse I — Klassifikation
- 5-Minuten-Segmente, **22 Features** (9 Statistik + 4 Respirations-Spektralbänder + 8 Skin-Conductivity-Orienting-Response + 1 HRV = LF/HF-Ratio).
- **112 Segmente**, **Leave-one-out**, **Fisher-Projektion + linearer Diskriminant**.
- **Ergebnis (Confusion Matrix):** Low **100 %**, Medium **94,7 %**, High **97,4 %** → **Gesamt 97,4 %**. Rest perfekt von beiden Fahrbedingungen getrennt.

## Analyse II — kontinuierliche Korrelation
- Kontinuierliche Stress-Metrik aus Video (Faltung mit 100-s-Hanning-Fenster).
- **Hautleitfähigkeit = bestes Echtzeit-Korrelat**, gefolgt von HRV und Herzrate.

## Bedeutung & Anwendung
Kanonisches **Affective-Computing**-Beispiel; Auto als „intelligente Umgebung". Anwendung: adaptives Management **nicht-kritischer** In-Vehicle-Systeme (Anrufe → Voicemail, weniger Navi-Infos, Musik anpassen). Brücke zu WESAD (`P5_data_dilemma.md`).

## Klausur-Kernpunkte
1. **4 Sensortypen:** EKG, EMG, Skin Conductivity, Respiration.
2. **3 Level** = Rest/Highway/City = niedrig/mittel/hoch.
3. **97,4 %**, 22 Features, **Fisher + Leave-one-out**.
4. **Skin Conductance + Herzrate** = beste Korrelate → erste in Autos zu integrierende Sensoren.
5. Validierung: Fragebogen + Video-Coding (13,6/61,4/87,7).
6. „Stress" = Distress (negativ).

> Bezug: Vorlesungen 03 & 06.
