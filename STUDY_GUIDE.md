# Ubiquitous Computing — Klausur-Lernzusammenfassung

> Dozent: Kristof Van Laerhoven (Uni Siegen). Diese Zusammenfassung deckt alle 7 Vorlesungen, die 9 Paper/Lesetexte und die Notebooks ab. Aufbau: **Roter Faden → 7 Vorlesungen → Paper → Notebooks → Querverbindungen → Lernplan (10 Einheiten)**.

---

## TEIL 0 — Der rote Faden: Wo die Reise hingeht

Der Kurs erzählt **eine durchgehende Geschichte**: vom *Traum unsichtbarer Computer* bis zur *Frage, wie man solchen Systemen (und ihren Daten) trauen kann*.

```
(1) VISION            Was ist UbiComp?           Weiser: Computer verschwinden, 3. Ära
        │
(2) METHODE           Wie beweise ich, dass es    Experimente, Statistik, Studiendesign
        │             funktioniert?
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

**Die eine Leitidee:** Mark Weiser sagt — *"The most profound technologies are those that disappear."* Alle 7 Kapitel sind Antworten auf die Frage, **was nötig ist, damit Computer in den Alltag verschwinden können**:
- Damit sie verschwinden, müssen sie **am Körper** (3) oder **in der Umwelt** (4) sitzen,
- müssen über **gute Interfaces** bedienbar sein (5),
- müssen **Kontext verstehen** (6),
- und dürfen dabei **nicht versagen oder ausspionieren** (7).
- Und damit wir das überhaupt *behaupten* dürfen, brauchen wir **saubere empirische Methodik** (2) — der heimliche Star des Kurses, weil "die Hälfte der Klausurfragen aus den Übungen kommt".

**Drei Querthemen ziehen sich durch alles:** (a) *Sensing & Machine Learning* auf Menschen/Umwelt, (b) *Datenvisualisierung & Datenethik* ("traue keinen Daten/Labels blind"), (c) *Evaluation in the wild* statt nur im Labor.

---

## TEIL 1 — Die 7 Vorlesungen

### Vorlesung 1 — Introduction to Ubiquitous Computing

**Story:** Welche Computer nutzen wir täglich? → mehr als Technik (soziale Aspekte, Design) → Weisers Vision unsichtbarer Computer.

**Kernkonzepte:**
- **3 Eras of Computing** (Weiser): **Mainframe** (1950, ein Computer/viele Menschen) → **PC** (1975, ein Computer/eine Person) → **Ubiquitous Computing** (2000, viele Computer/eine Person, "nearly invisible").
- **3 Definitions-Säulen:** (1) 3. Ära, (2) unsichtbare Technologie, (3) Fortschritt aus Embedded Systems.
- **"Good technology is invisible"** — gute Technik tritt hinter die Aufgabe zurück (Bleistift, Auto). UbiComp = **Umkehrung der Virtual Reality**: VR bringt die Welt in den Computer, UbiComp bringt den Computer in die Welt; **der Mensch steht im Zentrum**.
- **Affordance:** geprägt von **Gibson (1979)**, in die HCI gebracht von **Norman (1988)** — ein Designhinweis, der die Nutzung ohne Erklärung erkennbar macht.
- **Embedded Systems** (Marwedel) vs. **Cyber-Physical Systems / Embedded Software** (Lee, UC Berkeley — Kernproblem: Management von Zeit & Nebenläufigkeit).
- **UbiComp vs. KI:** nicht eine konzentrierte Intelligenz, sondern viele **"smarte" Komponenten** (winziger Weltausschnitt); Sinn entsteht durch Vernetzung — "smart verhält sich zu intelligent wie Neuronen zu Gehirnen".
- **3 PARC-Prototypen (1992):** **Tab** (Post-It-groß, mehrere/Nutzer), **Pad** (Tablet, eines/Nutzer), **Board** (LiveBoard, eines/Büro) = drei Größenklassen.
- **Users-Computers-Reality:** GUI (1 C) · VR (C umschließt U) · AR (C zwischen U und R) · UbiComp (viele C). **Mediated Reality** (Mann): VR ⊂ AR ⊂ Mixed ⊂ Mediated.
- **Methoden:** Prototype-driven, **Living Lab** (Prototypen im realen Alltag einsetzen).

**Merksatz:** *Mainframe → PC → UbiComp; unsichtbar; Tab/Pad/Board; Umkehrung der VR.*

---

### Vorlesung 2 — Designing Experiments for UbiComp

**Story:** Wozu Studien? → Kausalität → Variablen/Hypothesen → Zufall & Daten zusammenfassen → Signifikanz → Designtypen → was UbiComp-Evaluation schwer macht. **(Übungsstoff = klausurrelevant!)**

**Kernkonzepte:**
- **Kausalität (Mill, 1843):** Ursache geht voraus + korreliert + alle anderen Erklärungen ausgeschlossen. Vergleich **experimental vs. control condition**.
- **Variablen:** **unabhängige** (manipuliert; Anzahl Werte = **Level**) vs. **abhängige** (gemessen — objektiv: Zeit/Fehler; subjektiv: Bedienbarkeit).
- **Nullhypothese:** "kein Effekt"; Ziel der Studie = **Nullhypothese widerlegen** (leichter, als die Hypothese direkt zu beweisen).
- **Qualitativ/Formativ** (während Design, findet Problembereiche) vs. **Quantitativ/Summativ** (Qualitätssicherung des fertigen Produkts).
- **Zentralmaße:** **Mode** (häufigster Wert, auch nominal) · **Median** (mittlerer Wert, robust gegen Ausreißer, ab ordinal) · **Mean** (Summe/Anzahl, alle Werte, nur Intervall/Ratio, empfindlich gegen Ausreißer).
- **Verteilung darstellen:** Histogramm, Quantile (Quartile=4, Perzentile=100), **Boxplot** (Max, Q3, Median, Q1, Min; IQR), Scatterplot.
- **Signifikanz: p ≤ 5 %** (unwahrscheinlich zufällig) — **nicht** = praktisch relevant. Tests: **Permutationstest, t-Test, ANOVA**. Große **Standardabweichungen** → Verteilungen überlappen → kein signifikanter Unterschied.
- **Designtypen:** **Observational** (natürlich, unkontrolliert) · **Experimental** (kontrolliert → einziger Weg zu Kausalität) · **Quasi-experimentell** (keine zufällige Zuordnung, z.B. aus Ethik).
  - **4 Quasi-Designs:** one-group post-test · one-group pre/post-test · interrupted time-series (anfällig für **History-Threat**) · static group comparison.
  - **Within-subject** (jeder alle Bedingungen, Reihenfolge randomisieren, Carry-over-Gefahr, weniger n) vs. **Between-group** (separate Gruppen, kein Carry-over, mehr n).
  - **3 Between-Group-Designs:** post-test-only · pre/post-test control · **Solomon-4-Gruppen** (trennt Treatment- von Pre-Test-Effekt, aber teuer).
- **Randomisierung ist kritisch:** **Lanarkshire-Milk-Experiment (1930)** — 20.000 Kinder, aber wertlos, weil Lehrer arme Kinder bevorzugt der Milchgruppe zuteilten.
- **Reale Daten sind "wild"** (Alan Dix): scheinbare Unterschiede können Zufall sein → große Stichproben, mitteln, Signifikanz.
- **UbiComp-spezifisch:** **"In the wild"** (Rogers — Labor erklärt nur ~20 % der Alltagsvarianz); Lösungen: **Wizard of Oz** (Experimenter-in-the-Loop), **Living Lab**, **Participatory Design**.

**Merksatz:** *Nullhypothese widerlegen; p≤5%; within vs. between; randomisieren (Lanarkshire!); in the wild.*

---

### Vorlesung 3 — Wearable Computing

**Story:** Geschichte (Mensch augmentiert sich seit je) → Definition → Input → Output → **Intelligence Augmentation** → Wearability/Ergonomie → Privacy.

**Kernkonzepte:**
- **Definition:** elektronisches, am Körper tragbares Gerät zum Speichern/Verarbeiten von Daten.
- **Eigenschaften (Rhodes 1996):** portable while operational, hands-free, Umgebungssensoren, proaktiv, always on. **+ Mann (1998):** reconfigurable, always ready. → *Tricky Question:* Sind Smartphones Wearables?
- **Erster Wearable Computer: Thorp & Shannon (1955–66)** zum Schlagen des Roulettes — 12 Transistoren, Lautsprecher hinterm Ohr (Output), Zehenschalter (Input).
- **Intelligence Augmentation (IA) vs. AI:** IA **verbessert** den Menschen, AI **ersetzt** ihn (Vordenker: Ashby, Licklider, Bush, Engelbart).
- **Memex** (Vannevar Bush, 1945, "As We May Think"): Proto-Hypertext-/Gedächtnismaschine; sagte Hypertext, PC, Internet, WWW voraus.
- **Remembrance Agents** (Rhodes 1996): zeigen in Echtzeit kontextrelevante Dokumente → Vorläufer heutiger KI-Assistenten.
- **Affective Computing** (Healey & Picard): Emotion/Stress per physiologischer Sensorik.
- **AR**: benannt 1992 von Caudell & Mizell; **Mediated Reality** (Mann) modifiziert die Realität (nicht nur ergänzen). **Sensory remapping:** BrainPort (Bach-y-Rita 2004 — Gleichgewicht auf die Zunge).
- **Wearability = 3 Fragen:** Wo platzieren? Wie komfortabel? Wie funktional?
- **3 Ergonomie-Messmethoden:** **REBA** (objektiv, Haltung, Score 1=gut…15=schlecht) · **Borg CR-10** (physiologische Anstrengung, 0–10) · **Comfort Rating Scales** (subjektiv, 6 Dimensionen: Emotion, Attachment, Harm, Perceived change, Movement, Anxiety).
- **Texteingabe:** akkordbasierte Tastaturen ~60 WPM (Twiddler Expert 65.3). **Fitts' Law gilt auch beim Gehen**; **Tippen beim Gehen: >35 % langsamer**.
- **Designing for Intimacy (Google Glass):** Attention (→ **Micro-Interactions**) · Social interaction (graceful, multiple Zugangswege) · UX (Informationsdichte ↓, **Glanceability**, eine Aufgabe). Ahonen: Smartwatch = **3-Sekunden-Gerät**. NHTSA: Blick weg < 2 s, kumulativ < 12 s. **"Fashion first"** — nur 12 % würden AR-Brillen tragen.
- **Privacy:** Wearables ("der Nutzer trackt die Welt") vs. Smart Environments ("die Welt trackt den Nutzer"). **Sousveillance** (Mann): "watch the watchers".

**Merksatz:** *Rhodes-5-Eigenschaften; IA≠AI; Memex; REBA/Borg/CRS; Micro-Interactions; Fashion first.*

---

### Vorlesung 4 — Wireless Sensor Networks / Smart Dust

**Story:** Vision (Smart Dust) → Anwendungen → Herausforderungen → Software-Konzepte (Polling/Interrupts/Protothreads/Watchdogs) → Contiki-OS & MAC.

**Kernkonzepte:**
- **Smart Dust** (Kris Pister, 1997): winzige, drahtlos vernetzte Sensoren über ein Gebiet verteilt.
- **3 Treiber:** **Moore's Law** (kleinere Prozessoren) · **MEMS** (billige/kleine/digitale Sensoren, 0.001–0.1 mm; erster Markt: Airbag) · **Kommunikationsstandards**.
- **Accelerometer-Modell:** Kugel im Röhrchen an Federn — misst **dynamische** (Translation) und **statische** (Rotation/Gravitation, 1g) Beschleunigung. Wichtig: Sampling Rate (Hz), Interval (ms), Range (±g).
- **5 WSN-Herausforderungen:** Power · Processing (8/16-bit µC, **kein Floating Point**) · Communication · Data Storage · Deployment.
- **Polling** (READY-Bit ständig prüfen → Busy Waiting, schnell aber blockiert) vs. **Interrupts** (bei IRQ: CPU-Kontext PC+Register auf **Stack**, **ISR** ausführen, RETURN — ISRs kurz halten).
- **Interrupt-Konzepte:** Masking, Priority, **NMI** (höchste Prio, nicht deaktivierbar), Vector Numbers. **Software-Interrupts:** Aborts / Faults (vor Instruktion, z.B. Div/0) / Traps (während/nach, z.B. Overflow).
- **Shared-Data-Problem** → **atomic section** (disable_int/enable_int); beste Praxis merkt vorherigen Interrupt-Zustand.
- **Faustregel:** generell Interrupts statt Polling; Polling nur bei Shared-Data-Vermeidung oder nsec–µsec-Ereignissen.
- **Protothreads** (Adam Dunkels): extrem speicherarme, stapellose Threads — in **6 Zeilen C** via switch/`__LINE__`-Trick; lesbarer als Zustandsmaschine, aber lokale Variablen gehen verloren (außer `static`).
- **Watchdog:** Timer, der den µC **resettet**, wenn nicht regelmäßig "gestreichelt"; 3 Lösungen bei Long-running Tasks: `PROCESS_PAUSE()` · `watchdog_stop/start` · `watchdog_periodic`.
- **Contiki:** speichereffizientes OS (~2 kB RAM, 40 kB ROM), IPv6, Protothreads, `PROCESS_*`-Makros.
- **Energie:** Networking ist am teuersten — TX 600, RX 680 Zyklen/Bit, Sleep 1/100 Zyklus → **Radio so oft wie möglich aus**.
- **MAC (Low-Duty-Cycle):** **X-MAC** (wiederholte Preamble mit Zieladresse) vs. **ContikiMAC** (broadcastet Datenpaket direkt). Railroad-Versuch: "Radio on" 100 % → X-MAC 10,4 % → **ContikiMAC 1,5 %**. (802.15.4-Kanal 26 = Contiki-Default, liegt interferenzarm zwischen 802.11-Kanälen 1/6/11.)

**Merksatz:** *Smart Dust; Moore+MEMS+Comm; Interrupt>Polling; Protothreads (6 Zeilen); Watchdog; ContikiMAC spart 98%.*

---

### Vorlesung 5 — Physical & Tangible Interfaces

**Story:** Erst **menschliche Physiologie** verstehen (Sehen/Hören/Haptik/Gedächtnis) → dann Interaktion **vorhersagbar** machen (Fitts, Steering, KLM) → **Norman's 7 Stages** → **Tabletop & Tangibles**.

**Kernkonzepte:**
- **Auge:** ~100–120 Mio. **Stäbchen** (Nachtsicht, außerhalb Fovea), ~7–8 Mio. **Zapfen** (Tagsicht, in Fovea; S/M/L = 10% blau/48% grün/42% rot). **Fovea** = schärfste Sicht.
- **Pre-attentive (parallel, <200–250 ms, unabhängig von Distraktorenzahl)** vs. attentive (seriell). **Gestaltprinzipien:** Emergence, Reification, Invariance, Multi-stability, Closure, Symmetry.
- **Selective Attention** (Gorilla-Experiment, Simons 1999) & **Change Blindness** (Door Study, ~50 %) → relevant für "calm technology".
- **Hören:** empfindlichste bei **1000–6000 Hz**; Fletcher-Munson-Kurven.
- **Haptik:** 4 Mechanorezeptoren — **Pacinian** (Hochfrequenz-Vibration), **Meissner** (Flattern/Schlupf), **Merkel** (Form/Rauheit), **Ruffini** (Hautdehnung). Propriozeption/Kinästhesie = Muskeln/Gelenke/Bewegung.
- **Gedächtnis:** **Modal Model** (Atkinson & Shiffrin 1968: Sensory → Short-term ↔ Long-term, mit Rehearsal). Working Memory: **7±2 Chunks** (Miller 1956). Langzeit: episodisch (Ereignisse) vs. semantisch (Fakten). Vergessen: Decay + Interferenz (retroaktiv/proaktiv). Recall (mit Cues) vs. Recognition.
- **Fitts' Law (Shannon-Form, MacKenzie 1992):**
  $$T = a + b \cdot \log_2\!\left(1 + \tfrac{D}{W}\right), \quad ID = \log_2\!\left(1 + \tfrac{D}{W}\right)$$
  a = Start/Stopp-Zeit, b = Gerätegeschwindigkeit, D = Distanz, W = Zielbreite. **Implikationen:** größere/nähere Ziele, Pie Menus, Ränder/Ecken (unendlich groß).
- **Law of Steering** (Rashevsky 1959 / Accot-Zhai 1997): Tunnel $T = a + b\cdot\frac{D}{W}$ (ID **linear**!), beliebig: $T = a + b\int_C \frac{ds}{W(s)}$.
- **KLM (Keystroke-Level Model):** $T = T_K+T_P+T_B+T_H+T_D+T_M+T_R$. Werte: H=0,4 s · B=0,1 s · **M=1,35 s** · K=0,12–1,2 s. Sagt Ausführungszeit **vor** Implementierung voraus.
- **Norman's Seven Stages of Action:** Goals → Intention → Sequence → Execution → Perceiving → Interpreting → Evaluation. **Gulf of Execution** (Lücke wahrgenommene↔nötige Aktionen) und **Gulf of Evaluation** (Lücke beim Interpretieren des Displays). **Affordance** vs. **Signifier** (wahrnehmbarer Teil der Affordance) vs. **Mapping** vs. **Constraints**.
- **Direct Manipulation** (Shneiderman 1983): kontinuierliche Objektrepräsentation, physische Aktionen statt Befehlssyntax, schnelle umkehrbare Aktionen mit Feedback.
- **Tabletop** (Digital Desk 1991; MS Surface 2011) & **Tangible/Graspable UIs** (Fitzmaurice): space-multiplex (Input+Output), concurrent/bi-manual, application-specific, spatially aware, re-configurable. Beispiele: Topobo, ZeroN.

**Merksatz:** *Stäbchen/Zapfen; pre-attentive<250ms; 7±2; Fitts (log) vs. Steering (linear); KLM-Zeiten; 7 Stages + 2 Gulfs; Affordance≠Signifier.*

---

### Vorlesung 6 — Context Awareness & Activity Recognition

**Story:** Warum Kontext? → Definitionen → frühe Systeme → **Klassifikations-Pipeline** (Daten → Features → Klassifikator → Evaluation → Ground Truth).

**Kernkonzepte:**
- **Context-aware computing** (Schilit & Theimer 1994): Fähigkeit, Umgebungsänderungen zu entdecken und darauf zu reagieren. **Context** (Dey & Abowd 2000): "jede Information, die die Situation einer Entität charakterisiert" (breiteste Definition).
- **Nutzen von Kontext:** gemeinsames Verständnis · **implizite Interaktion** · Vermeidung von Fehlinterpretationen.
- **Frühe Systeme:** **Active Badge** (Ultraschall-Lokalisierung) · **Stick-e Notes** (kontextabhängige Dokumente) · **Cooltown** (HP, Web-Präsenz für Dinge) · **TEA** (Sensoren im Telefon-Akku → Profil-Switching).
- **Activity Recognition:** Erkennen von **Actions & Goals** aus einer Serie von Beobachtungen. Schwerpunktverschiebung: **Machbarkeit → Genauigkeit → Usability/Durability** (Deployments mit echten Nutzern über Zeit).
- **Labor ≠ Realität:** Sloth-Beispiel (15,85 h vs. 9,63 h Schlaf), White-Coat-Hypertension. **4 Pitfalls:** wrong environment, intrusive sensors, wrong users, insufficient samples.
- **Curse of Dimensionality:** mehr Sensoren = bessere Trennbarkeit, aber exponentiell wachsendes Volumen → Daten sparser.
- **Feature** = messbare, möglichst **discriminating** Eigenschaft. Basis: Magnitude $\sqrt{x^2+y^2+z^2}$; über Sliding Window Min/Max/**Mean/Variance**.
- **Klassifikatoren:** **kNN** (nächster Nachbar, euklidische Distanz; k Nachbarn → Voting) · **weighted kNN** (Distanzen als Gewichte, argmax) · **Gauss-Modell** (nur μ und Σ pro Klasse speichern).
- **Evaluation — Konfusionsmatrix (TP/TN/FP/FN):**
  - **Accuracy** = (TP+TN)/alle
  - **Precision** = TP/(TP+FP) — "wie oft war eine Detektion richtig?"
  - **Recall** = TP/(TP+FN) — "wie gut auf der Zielklasse?"
  - **F1** = 2·P·R/(P+R) — harmonisches Mittel.
  - **Accuracy täuscht bei Class Imbalance!** (Rauchen: Dummy-Klassifikator 99,3 % Accuracy, aber Precision/Recall/F1 = 0 %.)
- **n-Fold Cross Validation:** jeder Teil wird mal Trainings-, mal Testdaten (3-fold: 2 trainieren, 1 testen, mitteln).
- **Ground Truth:** **Time Diary** · **Experience Sampling** (Alarm alle 15–30 min) · **Self Recall** (abends annotieren). Verzerrungen: Peak-End-Rule, Mood-congruent, Digit Bias.

**Merksatz:** *Dey&Abowd-Definition; Pipeline Daten→Feature→Klassifikator→Eval; kNN/Gauss; Precision/Recall/F1 schlägt Accuracy; Cross-Validation; Ground Truth.*

---

### Vorlesung 7 — Critical Systems, Security & Privacy

**Story:** Systeme sind nie von Anfang an perfekt → bei safety-critical ist der Impact riesig → **4 Fallstudien** als "teachable moments". (Outline kündigt zusätzlich Privacy & Kryptographie an.)

**Kernkonzepte & Fallstudien:**
- **Maroochy Water Breach (2000):** Insider-Angriff (Vitek Boden) auf **SCADA**-Abwassersystem über **unsichere Funkverbindungen** → 47 Fehler, >1 Mio. Liter Abwasser freigesetzt. Aufdeckung: angeblich deaktivierte Station-ID tauchte weiter auf → Impersonation. *Lehre:* wake-up call für kritische Infrastruktur/Funknetze.
- **Therac-25:** Strahlentherapie; **Software ersetzte Hardware-Interlocks** + **variable overflow** + fehlende Modul-Tests → Elektronenstrahl ohne Target ("lightning"), **16.500–25.000 rads in <1 s**. Überkonfidenz auf beiden Seiten; erst nach mehreren Toten FDA-Eingriff. *Lehre:* keine reine Software-Sicherheit bei safety-critical Systemen.
- **Fluorouracil (2006):** schlechtes **Pumpen-/UI-Design** (gleiche Taste für Dezimalpunkt und Pfeil; "mL" = mL/Std) → Dosis über **4 Stunden statt 4 Tage**. Human-Factors-Studie: 100 % der Schwestern verwirrt. *Lehre:* Designfehler ≠ Bedienerversagen.
- **Stuxnet:** Wurm gegen Siemens-PLCs (Vacon/Fararo Paya, 807–1210 Hz); erster mit **4 0-day-Vulnerabilities** + **2 kompromittierten Zertifikaten**; verbreitete sich über **USB-Sticks** (überwand **Airgap**); programmierte PLCs um und **maskierte den Output**. Meiste Infektionen im **Iran**. *Lehre:* Meilenstein der Cyber Warfare.
- **SCADA** = Supervisory Control And Data Acquisition. **Übergeordnete Lehre:** kritische Systeme versagen durch Zusammenspiel von Designfehlern, fehlenden Tests/Interlocks, Human Factors und Sicherheitslücken (intern wie extern).
- **Privacy (Outline):** Definitionen, Anonymity vs. Pseudonymity, AOL-Search-Beispiel; **Kryptographie-Grundlagen:** mono-/polyalphabetische Chiffren, Stream- vs. Block-Cipher, Public-Key, Hash, Signaturen.

**Merksatz:** *SCADA; Maroochy (Insider/Funk); Therac-25 (Interlocks/overflow); Fluorouracil (UI); Stuxnet (4 0-days/USB/Airgap).*

---

## TEIL 2 — Paper & Lesematerial

| # | Quelle | Kernaussage | Klausur-Anker |
|---|--------|-------------|---------------|
| 1 | **Weiser, "The Computer for the 21st Century"** (1991) | Gründungsdokument. Computer verschwinden; **Tabs/Pads/Boards** = Inch/Foot/Yard; embodied virtuality = Gegenteil von VR | 2 Probleme: **Location + Scale**; Active Badge; warnt früh vor Privacy |
| 2 | **Healey & Picard, Stress Detection in Driving** (~2005) | Physiologische Sensoren erkennen Fahrerstress mit **97,4 %** | 4 Sensoren: **EKG, EMG, Skin Conductivity, Respiration**; 3 Level Rest/Highway/City; 22 Features, Fisher + Leave-one-out; **Hautleitfähigkeit + Herzrate = beste Korrelate** |
| 3 | **Abowd, "What next, Ubicomp?"** (2012) | "Ubicomp is dead! Long live (ubiquitous) computing!" — verschwindet durch Erfolg | 3 Markenzeichen: real-world hacking, **"your noise is my signal"** (RADAR WiFi), Multidisziplinarität; 4. Generation = "conjoined"; "What is ubicomp's HyperCard?" |
| 4 | **Knight & Baber, "Comfort Assessment of Wearable Computers"** (`download.pdf`, ~2002) | Komfort ist **mehrdimensional** → **Comfort Rating Scales** | **6 CRS-Dimensionen:** Emotion, Attachment, Harm, Perceived change, Movement, Anxiety; basieren auf MDS, NASA-TLX-nah; **Feld>Labor** (Emotion/Anxiety steigen) |
| 5 | **Van Laerhoven, "The Data Dilemma"** (2025) | Daten sammeln ist trivial — aber **traue Daten/Labels nicht blind**; inspizieren & interpretieren | **WESAD** (Stress, ~93 %), **WEAR** (Outdoor-Sport, IMU+Video); selbst MNIST/ImageNet haben Label-Fehler; **7-Schritte-uPlot-Rezept** |
| 6 | **Streit & Gehlenborg, "Bar charts and box plots"** (Nature Methods 2014) | **Bar charts = Counts, Box plots = Verteilungen** | Boxplot kodiert 5 Werte (Q1/Q3/IQR, Median, ±1.5·IQR-Whisker); Bar+Error-Bar irreführend (Baseline-0); max. 8–12 Farben |
| 7 | **Fry, "When Graphs Are a Matter of Life and Death"** (New Yorker 2021) | Visualisierung kann über Leben/Tod entscheiden; **frag nach den fehlenden Daten** | **Challenger:** die 17 nicht gezeigten "kein Ausfall"-Punkte; Van Langren (1628) erster Stat-Graph; **Playfair** (Linie/Balken/Torte); Ibry (Zug-Zeit-Distanz); Scatter = Ähnlichkeit |
| 8 | **Exercise 01 — Steps in Designing a Study** | 5-Schritte-Gerüst am Beispiel "Kaffee → Schritte/Tag" | Variablen → Treatment → Hypothese/Nullhypothese → **between/within** → Messung + Statistik (p<0.05, Boxplot); Confounder mitdenken |
| 9 | **Gresham Lecture, Matt Jones, "AI and Humanity"** | Mensch- vs. LLM-Kognition | beide **prädiktiv**; Working Memory ~4 Chunks, LLMs "lost in the middle"; KI = semantisch, kein **episodisches/emotionales** Gedächtnis |

---

## TEIL 3 — Notebooks (praktischer Übungsstoff)

- **Fitts'_Law.ipynb** — interaktiv Klickdaten sammeln → Regression $T = a + b\cdot ID$ fitten. Versteht den **Index of Difficulty** praktisch (V5).
- **Locationing_Tags...ipynb** — BLE-Indoor-Lokalisierung: **RSSI log-distance path-loss** ($RSSI = -50 - 20\log_{10}(d)$), **Trilateration** aus 3 Scannern. Bezug: V4 (Sensornetze) + V6 (Lokalisierung).
- **Bangle.ipynb** — Wearable-Firmware-Prototyping (Espruino Bangle.js): JS auf dem µC via WebBLE, Minify/RAM/compiled/JIT/inline-C, Herzrate über BLE-Advertisement broadcasten. Bezug: V3 (Wearables) + V4 (Embedded).
- **interactive.ipynb** — große Sensor-Timeseries inspizieren: matplotlib/Plotly skalieren nicht → **uPlot** mit quantisierten Daten. Bezug: V6 + "Data Dilemma" (V/Paper 5).

---

## TEIL 4 — Querverbindungen (für Verständnis-/Transferfragen)

- **Sensing-Strang:** Weiser (Vision) → Knight (Komfort/Akzeptanz) → Healey-Picard (Stress, 4 Sensoren) → WESAD/WEAR (Data Dilemma) → Activity-Pipeline (V6).
- **Methodik-Strang:** Studiendesign-Übung liefert das Gerüst (Variablen, Hypothesen, between/within, p<0.05) → angewandt in Healey-Picard (ANOVA) und Knight (t-Tests).
- **Visualisierung/Ethik-Strang:** Nature Methods (Bar/Box) → New Yorker (fehlende Daten/Challenger) → Data Dilemma (Inspect/Interpret, Label-Fehler) → Studiendesign-Boxplot.
- **Reflexion/Zukunft:** Abowd (Verschwinden, 4. Generation "conjoined") ↔ Matt Jones (Mensch-KI-Kognition).
- **Wiederkehrende Konzepte:** Fitts' Law (V3 beim Gehen, V5 als Modell, Notebook) · Affordance (V1 Definition, V5 Design) · Living Lab / In-the-wild (V1, V2, V6) · "Labor ≠ Realität" (V2, V6, Knight, Data Dilemma).

---

## TEIL 5 — Lernplan: 10 Lerneinheiten (je ~90–120 min)

> Strategie: **erst Überblick & Methodik festziehen** (die "halbe Klausur" aus Übungen), dann Vorlesungen einzeln, dann Paper-Querbezüge, dann zwei Wiederholungsrunden mit aktivem Abruf. Beende jede Einheit mit 3–5 selbstgestellten Prüfungsfragen.

| LE | Thema | Inhalt | Aktives Lernziel |
|----|-------|--------|------------------|
| **1** | **Big Picture & V1** | Roter Faden (Teil 0) + Vorlesung 1 (Weiser-Vision, 3 Eras, Tab/Pad/Board, Affordance, UbiComp vs. VR/KI) + Weiser-Paper | Aus dem Kopf: die 3 Eras + die 3 Definitions-Säulen erklären; "warum UbiComp = Umkehrung der VR?" |
| **2** | **Methodik I — Studiendesign** | Vorlesung 2 (Kausalität, Variablen, Null-Hypothese, qualitativ/quantitativ) + Exercise 01 | Eine eigene Mini-Studie entwerfen (5 Schritte) zu frei gewähltem Thema |
| **3** | **Methodik II — Statistik & Designtypen** | Vorlesung 2 (Mode/Median/Mean, Signifikanz p≤5 %, t-Test/ANOVA, Quasi-/Between/Within, Solomon-4, Lanarkshire) | Boxplot von Hand zeichnen; within vs. between gegenüberstellen; "warum war Lanarkshire wertlos?" |
| **4** | **V3 — Wearables** | Geschichte, Rhodes/Mann-Eigenschaften, IA vs. AI, Memex, REBA/Borg/CRS, Micro-Interactions, Privacy/Sousveillance | Die 5+2 Eigenschaften + die 3 Ergonomie-Methoden aufzählen; "Smartphone = Wearable?" argumentieren |
| **5** | **V4 — Sensornetze / Smart Dust** | Smart Dust, 3 Treiber, WSN-Herausforderungen, Polling vs. Interrupts, Protothreads, Watchdog, Contiki, MAC | Interrupt-Ablauf (Stack/ISR) skizzieren; Protothread-Idee erklären; X-MAC vs. ContikiMAC |
| **6** | **V5 — Physical/Tangible Interfaces** | Physiologie (Auge/Ohr/Haptik/Gedächtnis), **Fitts** vs. **Steering** vs. **KLM**, Norman's 7 Stages + 2 Gulfs, Direct Manipulation, Tangibles | Fitts- & Steering-Formel hinschreiben + Unterschied (log vs. linear); 7 Stages aus dem Kopf |
| **7** | **V6 — Context & Activity Recognition** | Definitionen (Dey & Abowd), Pipeline, Features, kNN/Gauss, **Precision/Recall/F1**, Cross-Validation, Ground Truth | Konfusionsmatrix + alle 4 Metriken berechnen (Rauchen-/Lunch-Beispiel); "warum täuscht Accuracy?" |
| **8** | **V7 — Critical Systems & Security** | 4 Fallstudien (Maroochy, Therac-25, Fluorouracil, Stuxnet), SCADA, Privacy/Krypto-Outline | Jede Fallstudie in 2 Sätzen: was war die Ursache + die Lehre? |
| **9** | **Paper-Vertiefung & Querbezüge** | Healey-Picard (4 Sensoren, 97 %), Abowd, Knight (6 CRS), Data Dilemma (WESAD/WEAR), Nature Methods, Fry/New Yorker, Matt Jones + Teil 4 | Jedes Paper einer Vorlesung zuordnen + eine Querverbindung formulieren; Notebooks-Bezug |
| **10** | **Prüfungssimulation & Lückenschluss** | Alle "Merksätze" abdecken; selbst erstellte Fragenliste durchgehen; schwache Stellen aus LE 1–9 nacharbeiten | Geschlossener Probe-Test (ohne Unterlagen), danach gezielt Lücken füllen |

**Tipps für den Endspurt:**
- Die **Übungen sind ~50 % der Klausur** → Methodik (LE 2–3) und die Activity-Pipeline-Rechnungen (LE 7) doppelt ernst nehmen.
- **Formeln aktiv können:** Fitts ($\log_2(1+D/W)$), Steering (linear), KLM-Zeiten, Precision/Recall/F1, RSSI-Modell.
- **Namen & Jahre** als Karteikarten: Weiser/PARC, Gibson/Norman, Pister, Dunkels, Fitts/MacKenzie, Shneiderman, Dey & Abowd, Healey & Picard, Mann.
- **Transferfragen** üben: Teil 4 enthält die wahrscheinlichsten "Verbinde X mit Y"-Fragen.
