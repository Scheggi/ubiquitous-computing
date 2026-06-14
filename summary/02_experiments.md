# 02 · Designing Experiments for UbiComp

> ⭐ **Übungsstoff = klausurrelevant** (≈ halbe Klausur). Eng verzahnt mit `exercises/exercise_01_study_design.pdf`.

## Worum geht's
Wie evaluiert man UbiComp-Systeme wissenschaftlich? Von Kausalität über Variablen/Hypothesen, Datenzusammenfassung und Signifikanz bis zu Designtypen und „in the wild"-Evaluation.

## Kernkonzepte
- **Kausalität (Mill, 1843):** Ursache geht voraus + korreliert + alle anderen Erklärungen ausgeschlossen. Vergleich **experimental vs. control condition**.
- **Variablen:** **unabhängig** (manipuliert; Anzahl Werte = **Level**) vs. **abhängig** (gemessen — objektiv: Zeit/Fehler; subjektiv: Bedienbarkeit).
- **Nullhypothese:** „kein Effekt"; Ziel = **widerlegen** (leichter als die Hypothese direkt zu beweisen).
- **Formativ/qualitativ** (während Design, findet Problembereiche) vs. **summativ/quantitativ** (QS am fertigen Produkt).

## Zahlen, Maße, Tests
- **Zentralmaße:** **Mode** (häufigster Wert, auch nominal) · **Median** (mittlerer, robust gegen Ausreißer, ab ordinal) · **Mean** (Summe/Anzahl, alle Werte, nur Intervall/Ratio, ausreißerempfindlich).
- **Verteilung:** Histogramm, Quantile (Quartile=4, Perzentile=100), **Boxplot** (Max, Q3, Median, Q1, Min; IQR), Scatterplot.
- **Signifikanz: p ≤ 5 %** (unwahrscheinlich zufällig) — **≠ praktisch relevant**. Tests: **Permutationstest, t-Test, ANOVA**. Große SD → Verteilungen überlappen → nicht signifikant (MacKenzie: t=0,0147 signifikant vs. t=0,388 nicht).

## Designtypen
- **Observational** (natürlich, unkontrolliert) · **Experimental** (kontrolliert → einziger Weg zu Kausalität) · **Quasi-experimentell** (keine zufällige Zuordnung, z. B. Ethik).
- **4 Quasi-Designs:** one-group post-test · one-group pre/post-test · interrupted time-series (**History-Threat!**) · static group comparison.
- **Within-subject** (jeder alle Bedingungen, Reihenfolge randomisieren, Carry-over, weniger n) vs. **Between-group** (separate Gruppen, kein Carry-over, mehr n).
- **3 Between-Group-Designs:** post-test-only · pre/post-test control · **Solomon-4-Gruppen** (trennt Treatment- von Pre-Test-Effekt, aber teuer).

## Schlüsselbeispiele
- **Lanarkshire Milk (1930):** 20.000 Kinder, **wertlos** weil Lehrer arme Kinder bevorzugt der Milchgruppe zuteilten → **Randomisierung ist kritisch**.
- **Reale Daten sind „wild"** (Alan Dix): scheinbare Unterschiede = oft Zufall → große Stichproben, mitteln, Signifikanz.
- **UbiComp „in the wild"** (Rogers): Labor erklärt nur ~20 % der Alltagsvarianz; ganzes System muss erst gebaut werden. Lösungen: **Wizard of Oz** (Experimenter-in-the-Loop), **Living Lab**, **Participatory Design**.

## Die 5 Schritte einer Studie (= Exercise 01)
1. Variablen + Relation · 2. Treatments · 3. Hypothese → Nullhypothese · 4. Zuordnung between/within · 5. Messung + Statistik (p<0,05, Boxplot).

## Klausur-Kernaussagen
Nullhypothese widerlegen · p≤5 % ≠ relevant · Mode/Median/Mean korrekt zuordnen · within vs. between · 4 Quasi-Designs + History-Threat · Solomon-4 · Lanarkshire (Randomisierung) · in-the-wild/Wizard of Oz.

→ Paper: `summary/papers/P6_nature_methods.md`, `P7_fry_newyorker.md`; Exercise 01.
