# Formelsammlung — Ubiquitous Computing

> Alle quantitativen Inhalte des Kurses auf einen Blick. Herleitungen/Erklärungen in `summary/`.

---

## 1. Interaktionsmodelle (V5)

### Fitts' Law (Shannon-Form, MacKenzie 1992)
$$T = a + b \cdot \log_2\!\left(1 + \frac{D}{W}\right) \qquad ID = \log_2\!\left(1 + \frac{D}{W}\right)$$
- **T** = Bewegungszeit · **a** = Start/Stopp-Zeit (s) · **b** = Gerätegeschwindigkeit (s/bit) · **D** = Distanz zum Ziel · **W** = Zielbreite · **ID** = Index of Difficulty (bit).
- Höheres ID = schwieriger. ID ist geräteunabhängig.
- Ränder/Ecken = „unendliche" Zielbreite; Pie Menus = sehr niedrige Fehlerrate.

### Law of Steering (Accot-Zhai 1997 / Rashevsky 1959)
$$\text{Einfacher Tunnel: } T = a + b \cdot \frac{D}{W} \qquad \text{Beliebiger Tunnel: } T = a + b \int_C \frac{ds}{W(s)}$$
- **Wichtiger Unterschied zu Fitts:** Schwierigkeitsterm ist **linear** (D/W), bei Fitts logarithmisch.

### KLM — Keystroke-Level Model
$$T_{execute} = T_K + T_P + T_B + T_H + T_D + T_M + T_R$$
| Operator | Bedeutung | Zeit |
|---|---|---|
| **K** | Keystroke | 0,12 s (Expert 90 wpm) … 0,28 s (40 wpm) … 1,2 s (worst) |
| **P** | Pointing (Maus) | 0,8–1,5 s (Ø 1,1 s) |
| **B** | Buttonpress | 0,1 s |
| **H** | Homing (Hand wechseln) | 0,4 s |
| **D** | Drawing (nD Segmente, lD Länge) | 0,9·nD + 0,16·lD |
| **M** | Mentaler Akt | 1,35 s |
| **R/W** | System-Response | systemabhängig |

---

## 2. Sensorik & Lokalisierung (V4, V6, Notebooks)

### RSSI — Log-Distance Path Loss
$$RSSI = -50 - 20 \cdot \log_{10}(d) \quad [\text{dBm}]$$
- −50 dBm = Referenz bei 1 m; **−20 dB pro Verzehnfachung** der Distanz.
- Allgemein: $RSSI = A - 10\,n\,\log_{10}(d)$ ; Umkehrung $d = 10^{(A - RSSI)/(10n)}$ (n = Path-Loss-Exponent, ~2 im Freien).

### Beschleunigungs-Magnitude (Feature, V6)
$$|\vec{a}| = \sqrt{x^2 + y^2 + z^2}$$
- Schritt-Erkennung: Schwellwert über der Magnitude (z. B. > 1,3).

### Trilateration (2D, aus 3 Scannern)
Aus Distanzen d₁,d₂,d₃ zu Scannern (x₁,y₁)…(x₃,y₃):
$$A=2(x_2-x_1),\ B=2(y_2-y_1),\ C=d_1^2-d_2^2-x_1^2+x_2^2-y_1^2+y_2^2$$
$$D=2(x_3-x_1),\ E=2(y_3-y_1),\ F=d_1^2-d_3^2-x_1^2+x_3^2-y_1^2+y_3^2$$
$$x = \frac{CE - FB}{EA - BD}, \qquad y = \frac{CD - AF}{BD - AE}$$

---

## 3. Statistik & Datenzusammenfassung (V2)

### Zentralmaße
- **Mean:** $\bar{x} = \frac{1}{n}\sum_{i=1}^n x_i$  (nur Intervall/Ratio, ausreißerempfindlich)
- **Median:** mittlerer Wert nach Sortierung; bei gerader Anzahl Mittel der zwei mittleren (ab ordinal, robust)
- **Mode:** häufigster Wert (auch nominal)
- **Variance:** $\sigma^2 = \frac{1}{n}\sum_{i=1}^n (x_i - \bar{x})^2$  ·  **Std:** $\sigma = \sqrt{\sigma^2}$

### Quantile / Boxplot
- **Quartile** = Quantil/4 · **Perzentile** = Quantil/100 · **IQR** = Q3 − Q1
- Boxplot kodiert **5 Werte:** Min/Whisker, Q1, Median, Q3, Max/Whisker. Standard-Whisker: Q1 − 1,5·IQR und Q3 + 1,5·IQR; Ausreißer als Punkte.

### Signifikanz
- Signifikant gdw. **p ≤ 0,05** (5 % Zufallswahrscheinlichkeit). p ≠ praktische Relevanz.
- Tests: Permutationstest, t-Test, ANOVA. Große SD → Verteilungen überlappen → nicht signifikant.

---

## 4. Klassifikations-Metriken (V6)

### Konfusionsmatrix → Metriken (pro Klasse)
$$\text{Accuracy} = \frac{TP + TN}{TP + TN + FP + FN}$$
$$\text{Precision} = \frac{TP}{TP + FP} \qquad \text{Recall} = \frac{TP}{TP + FN}$$
$$F_1 = \frac{2 \cdot P \cdot R}{P + R} \quad (\text{harmonisches Mittel})$$
- **TP** = richtig erkannt · **FP** = fälschlich erkannt · **FN** = übersehen · **TN** = richtig abgelehnt.
- **Accuracy täuscht bei Class Imbalance** → Precision/Recall/F1 nutzen.

### Gauss-Klassifikator (N-dimensional)
$$G(x) = \frac{1}{(2\pi)^{N/2}\,|\Sigma|^{1/2}} \exp\!\left(-\tfrac{1}{2}(x-\mu)^\top \Sigma^{-1} (x-\mu)\right)$$
- Pro Klasse nur **μ** (Mittel) und **Σ** (Kovarianz) speichern.

### kNN
- **kNN:** Klasse des/der k nächsten Nachbarn (euklidische Distanz), Mehrheits-Voting.
- **weighted kNN:** Distanzen als Gewichte; pro Klasse Gewichte summieren, dann **argmax**.

---

## 5. Hardware-Kennzahlen (V4)

### Energie pro Operation (TmoteSky, Richtwerte)
| Operation | Energie | ≈ Zyklen |
|---|---|---|
| Compute 1 Tclk | 1200 pJ | 1 |
| **Transmit 1 bit** | 720 000 pJ | **600** |
| **Receive 1 bit** | 810 000 pJ | **680** |
| Listen 1 Tclk | 15 000 pJ | 13 |
| **Sleep 1 Tclk** | 9 pJ | **1/100** |
→ RX > TX > Listen ≫ Sleep. **Radio so oft wie möglich aus.**

### MAC-Energieersparnis (Railroad, „Radio on")
null 100 % → **X-MAC 10,4 %** → **ContikiMAC 1,5 %**.

### Moore's Law
Transistorzahl verdoppelt sich alle **2 Jahre**.

---

## 6. Wichtige Zahlen/Schwellen (gern abgefragt)

| Wert | Kontext |
|---|---|
| **7 ± 2 Chunks** | Kurzzeitgedächtnis (Miller 1956) |
| **< 200–250 ms** | pre-attentive processing |
| **1000–6000 Hz** | empfindlichster Hörbereich |
| **> 35 %** | Tempoverlust beim Tippen während des Gehens |
| **< 2 s / < 12 s** | NHTSA: Blick weg / kumulativ (In-Car) |
| **97,4 %** | Healey & Picard Stress-Klassifikation |
| **6** | Comfort-Rating-Dimensionen (Knight & Baber) |
| **4** | Sensoren bei Healey & Picard / 4 Pitfalls / Stuxnet 0-days |
| **17** | fehlende „kein Ausfall"-Punkte (Challenger) |
| **p ≤ 0,05** | Signifikanzschwelle |
