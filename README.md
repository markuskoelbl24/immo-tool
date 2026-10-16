# immo-tool

Zwei Einzeldatei-Werkzeuge, kein Build, keine externen Abhängigkeiten.

| Tool | Live |
|---|---|
| **Objektrechner** (`index.html`) | <https://markuskoelbl24.github.io/immo-tool/> |
| **Mietspiegel Landshut 2025** (`mietspiegel-landshut.html`) | <https://markuskoelbl24.github.io/immo-tool/mietspiegel-landshut.html> |

---

## Mietspiegel Landshut 2025

Adresse eintippen → Wohnlagezuschlag, Basiswert nach Tabelle 1, Merkmale ankreuzen →
ortsübliche Vergleichsmiete, Mietpreisbremse-Grenze (+10 %, § 556d BGB) und
Zweidrittel-Spanne (± 22 %).

Enthält den vollständigen qualifizierten Mietspiegel der Stadt Landshut 2025
(gültig 01.03.2025 – 28.02.2027): **15.051 Adressen** aus dem Straßenverzeichnis
(auf 771 Straßen verdichtet), Tabelle 1 mit 9 Größen- × 12 Baujahrsklassen,
Tabelle 2 mit 24 Ausstattungsmerkmalen und 5 Lagekriterien.

Läuft offline, der Stand liegt im localStorage. Gegenprobe am amtlichen Rechner:
<https://online-mietspiegel.de/landshut/>

⚠️ Keine Rechtsberatung. Der Lagewert ist der häufigste Wert der Straße, solange die
Hausnummer keine eigene Ausnahme hat — das Tool weist aus, welcher Fall vorliegt.

*Quelle: Stadt Landshut, Kommunale Statistikstelle. Amtliches Werk, § 5 UrhG.*

---

## Objektrechner

Vergleichsrechner für den Kauf einer vermieteten Eigentumswohnung. Eine einzelne HTML-Datei,
kein Build, keine externen Abhängigkeiten.

## Was er rechnet

| Bereich | Inhalt |
|---|---|
| Kennzahlen | €/m², Kaufpreisfaktor, Brutto- und Nettomietrendite, Hebel (Nettorendite − Sollzins) |
| Cashflow | Miete → Bewirtschaftung → Annuität → Steuer, monatlich und über den Anlagehorizont |
| Zielpreis | Welcher Kaufpreis ergibt Faktor 25/28, neutralen Hebel oder ausgeglichenen Cashflow |
| Finanzierung | Darlehensvarianten nebeneinander, Tilgungsplan bis zur Volltilgung, Anschlusszins |
| Depot-Hürde | Ab welcher jährlichen Wertsteigerung das Objekt einen Sparplan schlägt |
| Bewertung | Stärken, Schwächen, offene Fragen, Sanierungsrisiko nach Miteigentumsanteil |

## Rechenannahmen

Voreingestellt auf Bayern 2026: Grunderwerbsteuer 3,5 %, Notar 1,5 %, Grundbuch 0,5 %,
AfA 2 % linear (2,5 % bei Fertigstellung vor 1925, § 7 Abs. 4 Nr. 2b EStG). Alle Werte in der
Kopfleiste sind überschreibbar.

Zwei bewusste Abweichungen von gängigen Kalkulationstabellen:

- **Grenzsteuersatz realistisch ansetzen.** Viele Vorlagen rechnen mit dem Tarif 2017 samt
  vollem Solidaritätszuschlag und überzeichnen den Steuervorteil aus Vermietungsverlusten.
- **Rücklagenzuführung ist nicht sofort Werbungskosten**, sondern erst bei Verausgabung.
  Angesetzt werden hier nur die Verwaltungskosten.

Die Mietentwicklung kann wahlweise der Kappungsgrenze folgen (15 % in drei Jahren bis zur
ortsüblichen Vergleichsmiete) statt gleichmäßig zu steigen — das bildet ab, wie langsam sich
eine Mietlücke bei laufendem Mietverhältnis tatsächlich schließen lässt.

## Daten

Alles liegt im `localStorage` des jeweiligen Browsers. Über **Sync** lässt sich optional ein
**privates** GitHub-Repo als gemeinsamer Speicher eintragen; dann arbeiten mehrere Geräte am
selben Stand. Beim Zusammenführen gewinnt je Objekt der neuere Stand, gelöschte Objekte bleiben
über Tombstones gelöscht.

Der Zugangstoken bleibt ausschließlich im Browser und wird nie in die synchronisierte Datei
geschrieben. Dieses Repo enthält ausschließlich Programmcode — keine Objekte, keine Finanzdaten.

## Keine Beratung

Modellrechnungen mit selbst gesetzten Annahmen. Ersetzt keine Steuer-, Rechts- oder
Anlageberatung; Steuerfragen gehören zum Steuerberater.
