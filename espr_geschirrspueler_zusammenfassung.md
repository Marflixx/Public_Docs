# ESPR Gewerbliche Geschirrspüler — Zusammenfassung

Stand: 21.07.2026

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
| REC | Reference Energy Consumption (kWh/Teller) | von der EU festzulegender Referenzwert je Gerätetyp |
| EEI | Energy Efficiency Index (%) | EEI = SPEC / REC · 100 |

EEI wird anschliessend über Tabelle 1 (Untertisch, vollständig definiert) bzw.
Tabelle 2 (Haube, nur Klasse A ≤100 fixiert, B–G noch offen) auf die
Buchstabenklasse A–G abgebildet.

## Zentrale offene Lücke: REC fehlt

**REC ist im geprüften Entwurf für beide Gerätetypen nur als Platzhalter
angegeben** ("REC = [ kWh/plate]") — kein offizieller Zahlenwert existiert
aktuell irgendwo öffentlich. Ohne REC lässt sich kein EEI und damit **keine
Energieeffizienzklasse (A–G) berechnen.**

Möglicher Präzedenzfall: Bei der **Haushalts**-Geschirrspüler-Verordnung
(EU 2019/2022) ist REC keine feste Zahl, sondern eine Formel abhängig von der
Rated Capacity (Anzahl Gedecke). Ob das bei gewerblichen Geräten analog
gehandhabt wird, ist im aktuellen Entwurf nicht spezifiziert — unbestätigte
Vermutung, kein Fakt.

## Was schon jetzt (ohne REC) auswertbar ist

Die **Ecodesign-Mindestanforderung** ist im Entwurf bereits fix und
unabhängig von REC/EEI:

- Under-counter: SPEC < **0,021 kWh/Teller**
- Hood-type: SPEC < **0,023 kWh/Teller**

Zusätzlich: Reinigungsleistung (xclean) > 90 %, sowie Mindest-Hygieneanforderungen
(Bioindikator-Reduktionsraten).

## Umgesetztes Werkzeug

`eu_energielabel.py` (im Repo `Marflixx/egs-eartheffect`, Commit `9ee1df1`,
Doku in `docs/konzept_eu_energielabel.md`):

- Liest read-only Geschirrspüler-Geräte aus der EcoGastro Datenbank (`device` ⨝
  `device_listing` ⨝ `measure_category`), erkennt Gerätetyp über den
  Kategorienamen ("haube" → hood_type, "untertisch" → under_counter)
- Prüft Ecodesign-Konformität (SPEC-Grenzwert) — funktioniert bereits heute
- Berechnet EEI/Klasse **nur**, wenn REC explizit als Parameter übergeben wird
  (`--rec-under-counter`, `--rec-hood-type`) — sonst `label_class=None` mit
  Hinweis, statt einen falschen Wert zu raten
- Keine Schreiboperation, keine Schema-/Migrationsänderung

## Fazit

Eine verlässliche A–G-Label-Zuordnung ist **aktuell nicht möglich**, da der
zentrale Referenzwert REC von der EU noch nicht veröffentlicht wurde
(Verordnung befindet sich in der Konsultationsphase, siehe oben). Sobald REC
final feststeht, ist das Skript direkt einsatzbereit — nur `REC_VALUES` in
`eu_energielabel.py` muss dann aktualisiert werden. Bis dahin ist nur die
Ecodesign-Pass/Fail-Prüfung (Mindestanforderung) belastbar auswertbar.

## Anhang: Auswertung der EcoGastro Datenbank (Stand 21.07.2026)

Read-only-Abfrage der Produktions-DB (`device` ⨝ `device_listing` ⨝
`measure_category`, Feld `energieverbrauch_pro_teller` = SPEC) gegen die
Ecodesign-Mindestanforderung (SPEC < 0,023 kWh/Teller bei Haube, < 0,021
kWh/Teller bei Untertisch).

**95 eindeutige Geschirrspüler-Modelle** mit hinterlegtem SPEC-Wert
ausgewertet:

- **87 Modelle erfüllen** die Ecodesign-Mindestanforderung (62 Haube-, 25
  Untertisch-Modelle)
- **8 Modelle erfüllen sie nicht** (siehe Tabelle unten)

### Modelle, die die Mindestanforderung NICHT erfüllen

| ID | Hersteller | Modell | Kategorie | Typ | SPEC (kWh/Teller) |
|---|---|---|---|---|---|
| 416 | Gehrig Group | GTW 3700 | Haubenspülmaschine 1 Korb, 500x500mm | Haube | 0,023 |
| 452 | Meiko | M-iClean HL | Haubenspülmaschine 1 Korb, 500x650mm | Haube | 0,027 |
| 454 | Meiko | M-iClean HL AirConcept | Haubenspülmaschine 1 Korb, 500x650mm | Haube | 0,026 |
| 453 | Meiko | M-iClean HL WWHR | Haubenspülmaschine 1 Korb, 500x650mm | Haube | 0,026 |
| 455 | Meiko | M-iClean HL AirConcept/WWHR | Haubenspülmaschine 1 Korb, 500x650mm | Haube | 0,024 |
| 590 | Meiko | M-iClean HXL WWHR | Haubenspülmaschine 2 Körbe | Haube | 0,024 |
| 383 | Meiko | M-iClean US ComfortAir | Untertischspülmaschinen, 400x400 mm Korb (Gläser) | Untertisch | 0,022 |
| 386 | Winterhalter | UC-S Energy | Untertischspülmaschinen, 400x400 mm Korb (Gläser) | Untertisch | 0,023 |

Auffällig: 7 der 8 nicht-konformen Modelle stammen aus den Kategorien „1 Korb,
500x650mm" (4x), „2 Körbe" (1x) oder „400x400 mm Korb (Gläser)" (2x) — also
den grösseren bzw. auf Gläser spezialisierten Varianten. Das bestätigt den
Punkt aus Abschnitt „Nur zwei Gerätekategorien": die EU-Klassierung selbst
kennt diese Unterkategorien nicht (nur Haube/Untertisch), aber die
tatsächlichen SPEC-Werte hängen in der Praxis sichtbar mit Korbgrösse/
Spezialisierung zusammen — genau das, was die Pro-Teller-Normierung
eigentlich ausgleichen soll, hier aber bei den grösseren/Glas-Varianten nicht
ausreicht, um unter den fixen Grenzwert zu kommen.

Die achte Ausnahme (ID 416, Gehrig Group GTW 3700) ist dagegen eine reguläre
„1 Korb, 500x500mm"-Kategorie — derselben Kategorie, in der die meisten
konformen Modelle liegen. Mit SPEC = 0,023 kWh/Teller liegt sie genau auf dem
Grenzwert (Ecodesign-Anforderung: SPEC muss strikt darunter liegen) und ist
damit ein Grenzfall, kein Grössen-/Kategorieeffekt.
