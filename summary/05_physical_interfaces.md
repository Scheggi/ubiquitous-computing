# 05 · Physical & Tangible Interfaces

## Worum geht's
Erst **menschliche Physiologie** verstehen (Sehen/Hören/Haptik/Gedächtnis), dann Interaktion **vorhersagbar** machen (Fitts, Steering, KLM), dann **Norman's 7 Stages** und **Tabletop/Tangibles**. Ziel: menschliche Fehler vermeiden.

## Physiologie
- **Auge:** ~100–120 Mio. **Stäbchen** (Nachtsicht, außerhalb Fovea), ~7–8 Mio. **Zapfen** (Tagsicht, in Fovea; S/M/L = 10 % blau/48 % grün/42 % rot). **Fovea** = schärfste Sicht.
- **Pre-attentive** (parallel, **<200–250 ms**, unabhängig von Distraktorenzahl) vs. attentive (seriell). **Gestaltprinzipien:** Emergence, Reification, Invariance, Multi-stability, Closure, Symmetry.
- **Selective Attention** (Gorilla, Simons 1999) & **Change Blindness** (Door Study, ~50 %) → relevant für „calm technology".
- **Hören:** empfindlichste bei **1000–6000 Hz**; Fletcher-Munson-Kurven.
- **Haptik — 4 Mechanorezeptoren:** **Pacinian** (Hochfrequenz-Vibration) · **Meissner** (Flattern/Schlupf) · **Merkel** (Form/Rauheit) · **Ruffini** (Hautdehnung). Propriozeption/Kinästhesie = Muskeln/Gelenke/Bewegung.
- **Gedächtnis:** **Modal Model** (Atkinson & Shiffrin 1968: Sensory → Short-term ↔ Long-term, mit Rehearsal). Kurzzeit: **7±2 Chunks** (Miller 1956). Langzeit: episodisch vs. semantisch. Vergessen: Decay + Interferenz (retro-/proaktiv). Recall (mit Cues) vs. Recognition.

## Prädiktive & deskriptive Modelle
- **Fitts' Law (Shannon-Form, MacKenzie 1992):**
  `T = a + b · log₂(1 + D/W)`,  `ID = log₂(1 + D/W)`
  a = Start/Stopp-Zeit, b = Gerätegeschwindigkeit, D = Distanz, W = Zielbreite. Implikationen: größere/nähere Ziele, Pie Menus, Ränder/Ecken (unendlich groß).
- **Law of Steering** (Rashevsky 1959 / Accot-Zhai 1997): Tunnel `T = a + b·(D/W)` — Schwierigkeit **linear** (vs. Fitts logarithmisch); beliebig: `T = a + b·∫_C ds/W(s)`.
- **KLM (Keystroke-Level Model):** `T = T_K+T_P+T_B+T_H+T_D+T_M+T_R`. Werte: **H=0,4 s · B=0,1 s · M=1,35 s**, K=0,12–1,2 s. Sagt Ausführungszeit **vor** Implementierung voraus.

## Interaktionsdesign
- **Norman's Seven Stages of Action:** Goals → Intention → Sequence → Execution → Perceiving → Interpreting → Evaluation. **Gulf of Execution** (Lücke wahrgenommene↔nötige Aktionen) vs. **Gulf of Evaluation** (Lücke beim Interpretieren des Displays).
- **Affordance** (wahrgenommene+tatsächliche Eigenschaften) vs. **Signifier** (wahrnehmbarer Teil) vs. **Mapping** vs. **Constraint**.
- **Direct Manipulation** (Shneiderman 1983): kontinuierliche Objektrepräsentation, physische Aktionen statt Befehlssyntax, schnelle umkehrbare Aktionen mit Feedback.
- **Tabletop** (Digital Desk 1991; MS Surface 2011) & **Tangible/Graspable UIs** (Fitzmaurice): space-multiplex (Input+Output), concurrent/bi-manual, application-specific, spatially aware, re-configurable (Topobo, ZeroN).

## Klausur-Kernaussagen
Stäbchen/Zapfen + Fovea · pre-attentive <250 ms · 4 Mechanorezeptoren · 7±2 · **Fitts (log) vs. Steering (linear)** · KLM-Zeiten (H/B/M) · 7 Stages + 2 Gulfs · Affordance≠Signifier · Direct Manipulation · Tangible-Eigenschaften.

→ Praxis-Notebook: `exercises/Fitts'_Law.ipynb`; Paper: `summary/papers/P8_matt_jones.md` (Gedächtnis Mensch/KI)
