# 07 · Critical Systems, Security & Privacy

## Worum geht's
Systeme sind nie von Anfang an perfekt — bei **safety-critical** Systemen ist der Impact riesig (Menschenleben, Infrastruktur). **Incident Reports** als „teachable moments". 4 Fallstudien + Privacy/Krypto-Outline.

## Grundbegriffe
- **Safety-critical system:** Fehler → nicht nur Patch, sondern hoher (oft lebensgefährlicher) Impact.
- **SCADA** = Supervisory Control And Data Acquisition (steuert Pumpen/Ventile/Alarme).
- **PLC** = Programmable Logic Controller. **Airgap** = keine Internetanbindung. **0-day** = unbekannte/ungepatchte Lücke. **Insider attack**. **Human Factors**.

## Die 4 Fallstudien
- **Maroochy Water Breach (2000):** Insider **Vitek Boden** rekonfigurierte über **unsichere Funkverbindungen** ein SCADA-Abwassersystem (142 Pumpstationen) → 47 Fehler, **>1 Mio. Liter** Abwasser freigesetzt. Aufdeckung: angeblich deaktivierte Station-ID tauchte weiter auf → Impersonation. *Lehre:* wake-up call für kritische Infrastruktur/Funknetze.
- **Therac-25:** Strahlentherapie (AECL). **Software ersetzte Hardware-Interlocks** + **variable overflow** + fehlende Modul-Tests → Elektronenstrahl ohne Target („lightning"), **16.500–25.000 rads in <1 s**. Überkonfidenz beidseitig; erst nach mehreren Toten FDA-Eingriff (Update mit 20 Änderungen). *Lehre:* keine reine Software-Sicherheit bei safety-critical Systemen.
- **Fluorouracil (2006):** schlechtes **Pumpen-/UI-Design** (gleiche Taste für Dezimalpunkt & Pfeil; „mL" = mL/Stunde) → Dosis über **4 Stunden statt 4 Tage**. Human-Factors-Studie: 100 % der Schwestern verwirrt. *Lehre:* Designfehler ≠ Bedienerversagen.
- **Stuxnet:** Wurm gegen Siemens-PLCs (Vacon/Fararo Paya, 807–1210 Hz); erster mit **4 0-day-Vulnerabilities** + **2 kompromittierten Zertifikaten**; verbreitete sich über **USB-Sticks** (überwand **Airgap**); programmierte PLCs um und **maskierte den Output**. Meiste Infektionen: **Iran**. *Lehre:* Meilenstein der Cyber Warfare.

## Privacy / Kryptographie (Outline)
Defining Privacy · Anonymity vs. Pseudonymity · AOL-Search-Beispiel · Krypto-Grundlagen: mono-/polyalphabetische Chiffren, Stream- vs. Block-Cipher, Public-Key, Hash, Signaturen.

## Übergeordnete Lehre
Kritische Systeme versagen durch ein **Zusammenspiel** von Designfehlern, fehlenden Tests/Interlocks, Human Factors und Sicherheitslücken (intern wie extern) → robuste Sicherheit + sorgfältige Evaluation essenziell.

## Klausur-Kernaussagen
SCADA-Definition · Maroochy (Insider/Funk) · Therac-25 (Interlocks/overflow, „lightning") · Fluorouracil (UI-Design) · Stuxnet (4 0-days/2 Zertifikate/USB/Airgap/Iran) · übergeordnete Lehre.
