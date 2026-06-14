# 04 · Wireless Sensor Networks / Smart Dust

## Worum geht's
Von der Smart-Dust-Vision zur Praxis: Treiber → Anwendungen → Herausforderungen → Software-Konzepte (Polling/Interrupts/Protothreads/Watchdogs) → Contiki-OS & MAC.

## Kernkonzepte
- **Smart Dust** (Kris Pister, 1997): winzige, drahtlos vernetzte Sensoren über ein Gebiet verteilt.
- **3 Treiber:** **Moore's Law** (kleinere Prozessoren, Verdopplung alle 2 J.) · **MEMS** (billige/kleine/digitale Sensoren, 0,001–0,1 mm; erster Markt: Airbag) · **Kommunikationsstandards**.
- **Accelerometer-Modell:** Kugel im Röhrchen an Federn — misst **dynamische** (Translation) & **statische** (Rotation/Gravitation, 1g). Wichtig: Sampling Rate (Hz), Interval (ms), Range (±g).
- **5 WSN-Herausforderungen:** Power · Processing (8/16-bit µC, **kein Floating Point**) · Communication · Data Storage · Deployment.

## Software-Konzepte (Kernteil)
- **Polling** (READY-Bit prüfen → Busy Waiting, schnell aber CPU blockiert) vs. **Interrupts** (bei IRQ: CPU-Kontext **PC+Register auf den Stack** → **ISR** → RETURN; ISRs kurz halten).
- **Interrupt-Begriffe:** Masking · Priority · **NMI** (höchste Prio, nicht deaktivierbar) · Vector Numbers.
- **Software-Interrupts:** **Aborts** (HW-Fehler) · **Faults** (vor Instruktion, z. B. Div/0) · **Traps** (während/nach, z. B. Overflow, Breakpoint).
- **Shared-Data-Problem** → **atomic section** (`disable_int/enable_int`); beste Praxis merkt vorherigen Interrupt-Zustand.
- **Faustregel:** generell Interrupts > Polling; Polling nur bei Shared-Data-Vermeidung oder nsec–µsec-Ereignissen.
- **Protothreads** (Adam Dunkels): stapellose, extrem speicherarme Threads in **6 Zeilen C** (switch/`__LINE__`-Trick); lesbarer als Zustandsmaschine, aber **lokale Variablen gehen verloren** (außer `static`).
- **Watchdog:** Timer, der den µC **resettet**, wenn nicht regelmäßig „gestreichelt"; 3 Lösungen bei Long-running Tasks: `PROCESS_PAUSE()` · `watchdog_stop/start` · `watchdog_periodic`.

## Contiki & Networking
- **Contiki:** speichereffizientes OS (~2 kB RAM, 40 kB ROM), IPv6, Protothreads, `PROCESS_*`-Makros.
- **Energie:** Networking ist am teuersten — **TX 600, RX 680 Zyklen/Bit**, Sleep 1/100 Zyklus → **Radio so oft wie möglich aus**.
- **MAC (Low-Duty-Cycle):** **X-MAC** (wiederholte **Preamble** mit Zieladresse) vs. **ContikiMAC** (broadcastet **Datenpaket** direkt). Railroad: „Radio on" 100 % → X-MAC 10,4 % → **ContikiMAC 1,5 %**. (802.15.4-Kanal 26 = Contiki-Default, interferenzarm zwischen 802.11-Kanälen 1/6/11.)

## Klausur-Kernaussagen
Smart Dust (Pister) · 3 Treiber (Moore+MEMS+Comm) · statisch/dynamisch beim Accelerometer · 5 Herausforderungen (kein Float) · Interrupt-Ablauf (Stack/ISR) · Aborts/Faults/Traps · atomic section · Protothreads (6 Zeilen, switch-Trick) · Watchdog (3 Lösungen) · TX/RX teurer als Sleep · ContikiMAC spart ~98 %.

→ Praxis-Notebook: `exercises/Locationing_Tags_in_Wireless_Sensor_Networks.ipynb`, `exercises/Bangle.ipynb`
