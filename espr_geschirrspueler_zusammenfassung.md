# ESPR Gewerbliche Geschirrspüler — Zusammenfassung

Stand: 21.07.2026 (aktualisiert: REC und Tabelle 2 waren anfangs fälschlich
als "offen" gemeldet, siehe Abschnitt "REC und Tabelle 2 (Haube)")

## Regulatorischer Status

Die EU bereitet zwei zusammengehörige Verordnungen für gewerbliche
Geschirrspüler vor (Rahmen: ESPR, Ecodesign for Sustainable Products
Regulation):

- **Ecodesign (ED)** — Mindestanforderungen für Marktzulassung
- **Energy Labelling (EL)** — Energieeffizienzlabel A–G

Beide liegen aktuell nur als **Entwurf** vor (Stand des Online-Stakeholder-Meetings
vom 23. Juni 2026). Zeitplan laut EU-Kommission / VITO-Vorstudie:

- Feedback-Frist zu den aktuellen Entwürfen: **13. September 2026**
- Öffentliche Konsultation (OPC): Herbst 2026
- Ecodesign-Forum-Treffen: Oktober 2026
- Abschluss der Vorstudie: Dezember 2026

Es handelt sich also um ein laufendes, nicht abgeschlossenes
Gesetzgebungsverfahren — Werte und Fristen im Entwurf können sich noch ändern.

Quellen: [Have your say – Ecodesign requirements for commercial dishwashers](https://ec.europa.eu/info/law/better-regulation/have-your-say/initiatives/16552-Ecodesign-requirements-for-commercial-dishwashers_en),
[ESPR Preparatory Study – Professional Dishwashers](https://ecodesign-commdishwashers.eu/en),
[Dokumente der Vorstudie](https://ecodesign-commdishwashers.eu/en/documents)

## Geprüfte Dokumente (4 total)

1. **EL-Annexe** — Label-Design (Annex III), Effizienzklassen A–G (Annex II),
   Produktdatenblatt (Annex V), technische Dokumentation (Annex VI), Werbe-/
   Fernabsatzvorgaben (Annex VII/VIII), Messmethoden (Annex IV), Verifizierung
   (Annex IX)
2. **ED-Annexe** — Ecodesign-Mindestanforderungen (Annex II): Reinigungsleistung,
   Energie-/Wasserverbrauch, Ersatzteile/Reparatur, Stoffinformationen,
   Hygiene; Messmethoden (Annex III), Verifizierung (Annex IV), Benchmarks
   (Annex V)
3. **ED-Artikel** — Verordnungstext Ecodesign (Art. 1–9): Geltungsbereich,
   Konformitätsbewertung, Umgehungsverbot, Review, Inkrafttreten
4. **EL-Artikel** — Verordnungstext Energy Labelling (Art. 1–9): Pflichten von
   Lieferanten, Händlern und Hosting-Plattformen, Review, Inkrafttreten

## Nur zwei Gerätekategorien — keine weitere Differenzierung

Die Verordnung unterscheidet ausschliesslich:

- **under-counter one-tank dishwasher** (Untertisch-Einbecken)
- **hood-type dishwasher** (Haube — schliesst auch Durchschub-Doppelhauben-Typen mit ein)

Es gibt **keine** separate EU-Kategorie für Durchschub- vs. einfache
Haubenspülmaschinen (beide = "hood-type"), und **keine** grössen-/
korbmassabhängigen Klassen. Grösse wird stattdessen implizit über die
Pro-Teller-Normierung (kWh/Teller, l/Teller) berücksichtigt.

## Zentrale Formeln (Annex IV, EL-Annexe)

| Grösse | Bedeutung | Formel |
|---|---|---|
| SPEC | Standard Programme Energy Consumption (kWh/Teller) | SPEC = EC / pR |
| REC | Reference Energy Consumption (kWh/Teller) | fest definiert je Gerätetyp (siehe unten) |
| EEI | Energy Efficiency Index (%) | EEI = SPEC / REC · 100 |

EEI wird anschliessend über Tabelle 1 (Untertisch) bzw. Tabelle 2 (Haube) auf
die Buchstabenklasse A–G abgebildet — **beide Tabellen sind vollständig
definiert** (siehe nächster Abschnitt).

## REC und Tabelle 2 (Haube) — Korrektur vom 21.07.2026

**Diese Werte wurden in einer früheren Fassung dieser Zusammenfassung
fälschlich als "im Entwurf noch offen" gemeldet.** Martin hat auf den Fehler
hingewiesen (danke).

Ursache: Das Word-Dokument (EL-Annexe) enthält an diesen Stellen Text im
Modus "Änderungen nachverfolgen" (`w:ins`, eingefügt beim Stakeholder-Meeting
vom 23.06.2026). Die ursprüngliche Text-Extraktion hat direkte Textbausteine
eines Word-Absatzes gelesen, aber Text innerhalb solcher
Track-Changes-Einfügungen technisch übersehen — dadurch erschienen die
Platzhalter leer, obwohl die Werte tatsächlich im Dokument standen. Nach
korrigierter Extraktion:

**REC (Referenz-Energieverbrauch):**

| Gerätetyp | REC |
|---|---|
| Under-counter one-tank dishwasher | 0,0130 kWh/Teller |
| Hood-type dishwasher | 0,0167 kWh/Teller |

**Tabelle 2 (Haubenspülmaschinen) ist vollständig definiert** (nicht nur
Klasse A, wie zuvor fälschlich gemeldet):

| Klasse | EEI-Bereich Untertisch (Tabelle 1) | EEI-Bereich Haube (Tabelle 2) |
|---|---|---|
| A | ≤ 100 | ≤ 100 |
| B | 100–110 | 100–106 |
| C | 110–120 | 106–112 |
| D | 120–130 | 112–118 |
| E | 130–140 | 118–124 |
| F | 140–150 | 124–130 |
| G | > 150 | > 130 |

Zusätzlich (ebenfalls über die Korrektur gefunden, ED-Annexe): die
Wasserverbrauchs-Mindestanforderung (SPWC) ist auch nicht mehr offen —
Under-counter < 0,179 l/Teller, Hood-type < 0,169 l/Teller. Diese SPWC-Werte
sind im Skript aktuell nur dokumentiert, nicht automatisch geprüft (dafür
müsste zusätzlich der Wasserverbrauch pro Gerät ausgewertet werden).

## Was jetzt auswertbar ist

Mit den korrigierten Werten lässt sich für jedes Gerät sowohl die
**Ecodesign-Mindestanforderung** (Pass/Fail) als auch die **volle A–G-Label-
Klasse** berechnen:

- Ecodesign-Mindestanforderung: Under-counter SPEC < **0,021 kWh/Teller**,
  Hood-type SPEC < **0,023 kWh/Teller** (zusätzlich: Reinigungsleistung
  (xclean) > 90 %, Mindest-Hygieneanforderungen)
- Label-Klasse: EEI = SPEC/REC·100, dann Tabelle 1 bzw. 2 (siehe oben)

Wichtig: Ecodesign-Konformität und Label-Klasse sind **unabhängig**
voneinander — auch ein Gerät, das die Mindestanforderung nicht erfüllt (und
damit eigentlich nicht in Verkehr gebracht werden dürfte), bekäme rechnerisch
trotzdem eine Klasse zugeordnet, wenn man die Formel einfach durchrechnet.

## Umgesetztes Werkzeug

`eu_energielabel.py` (im Repo `Marflixx/egs-eartheffect`, Doku in
`docs/konzept_eu_energielabel.md`):

- Liest read-only Geschirrspüler-Geräte aus der EcoGastro Datenbank (`device` ⨝
  `device_listing` ⨝ `measure_category`), erkennt Gerätetyp über den
  Kategorienamen ("haube" → hood_type, "untertisch" → under_counter)
- Prüft Ecodesign-Konformität (SPEC-Grenzwert)
- Berechnet EEI und Label-Klasse (A–G, beide Gerätetypen) mit den oben
  genannten REC-Werten als Default — überschreibbar (`--rec-under-counter`,
  `--rec-hood-type`), falls die EU die Werte in einer späteren Entwurfsfassung
  noch ändert
- Keine Schreiboperation, keine Schema-/Migrationsänderung

## Fazit

Die A–G-Label-Zuordnung ist **jetzt berechenbar** — REC und die vollständige
Haube-Klassentabelle waren im Entwurf bereits enthalten, wurden aber initial
durch einen Extraktionsfehler übersehen (siehe Korrektur oben). Die Werte
gelten für den Entwurfsstand vom Stakeholder-Meeting am 23.06.2026 und können
sich bis zum Abschluss der Konsultation (Feedback-Frist 13.09.2026, OPC
Herbst 2026) noch ändern.

## Anhang: Auswertung der EcoGastro Datenbank (Stand 21.07.2026)

Read-only-Abfrage der Produktions-DB (`device` ⨝ `device_listing` ⨝
`measure_category`, Feld `energieverbrauch_pro_teller` = SPEC).
**95 eindeutige Geschirrspüler-Modelle** mit hinterlegtem SPEC-Wert
ausgewertet.

### Ecodesign-Mindestanforderung

- **87 Modelle erfüllen** die Mindestanforderung (62 Haube-, 25
  Untertisch-Modelle)
- **8 Modelle erfüllen sie nicht** (siehe Tabelle unten)

### Label-Klassenverteilung (alle 95 Modelle, mit REC-Werten oben)

| Klasse | Anzahl Modelle |
|---|---|
| A | 7 |
| B | 2 |
| C | 10 |
| D | 23 |
| E | 26 |
| F | 16 |
| G | 11 |

Auffällig: Nur 9 von 95 Modellen (A+B) lägen in den beiden besten Klassen —
die meisten Modelle verteilen sich auf C bis F, auch wenn sie die
Ecodesign-Mindestanforderung locker erfüllen. Das liegt daran, dass REC
(0,0130 / 0,0167 kWh/Teller) deutlich unter den meisten in der Datenbank
vorkommenden SPEC-Werten liegt — REC scheint eher ambitionierte
Referenz-/Zielwerte statt Marktdurchschnitte abzubilden. Auf Wunsch kann ich
die vollständige Geräte-für-Geräte-Tabelle (alle 95, mit EEI und Klasse) als
Anhang oder Spreadsheet nachliefern.

### Modelle, die die Ecodesign-Mindestanforderung NICHT erfüllen

| ID | Hersteller | Modell | Kategorie | Typ | SPEC (kWh/Teller) | EEI | Klasse |
|---|---|---|---|---|---|---|---|
| 416 | Gehrig Group | GTW 3700 | Haubenspülmaschine 1 Korb, 500x500mm | Haube | 0,023 | 137,7 | G |
| 452 | Meiko | M-iClean HL | Haubenspülmaschine 1 Korb, 500x650mm | Haube | 0,027 | 161,7 | G |
| 454 | Meiko | M-iClean HL AirConcept | Haubenspülmaschine 1 Korb, 500x650mm | Haube | 0,026 | 155,7 | G |
| 453 | Meiko | M-iClean HL WWHR | Haubenspülmaschine 1 Korb, 500x650mm | Haube | 0,026 | 155,7 | G |
| 455 | Meiko | M-iClean HL AirConcept/WWHR | Haubenspülmaschine 1 Korb, 500x650mm | Haube | 0,024 | 143,7 | G |
| 590 | Meiko | M-iClean HXL WWHR | Haubenspülmaschine 2 Körbe | Haube | 0,024 | 143,7 | G |
| 383 | Meiko | M-iClean US ComfortAir | Untertischspülmaschinen, 400x400 mm Korb (Gläser) | Untertisch | 0,022 | 169,2 | G |
| 386 | Winterhalter | UC-S Energy | Untertischspülmaschinen, 400x400 mm Korb (Gläser) | Untertisch | 0,023 | 176,9 | G |

Alle 8 nicht-konformen Modelle landen erwartungsgemäss auch in Klasse G
(schlechteste Klasse) — das ist konsistent, da sie den Ecodesign-Grenzwert
überschreiten und REC deutlich darunter liegt.

Auffällig zur Kategorie: 7 der 8 nicht-konformen Modelle stammen aus den
Kategorien „1 Korb, 500x650mm" (4x), „2 Körbe" (1x) oder „400x400 mm Korb
(Gläser)" (2x) — also den grösseren bzw. auf Gläser spezialisierten
Varianten. Die achte Ausnahme (ID 416, Gehrig Group GTW 3700) ist dagegen
eine reguläre „1 Korb, 500x500mm"-Kategorie, in der die meisten konformen
Modelle liegen; mit SPEC = 0,023 kWh/Teller liegt sie genau auf dem
Ecodesign-Grenzwert und ist damit primär ein Grenzfall, kein
Grössen-/Kategorieeffekt.
