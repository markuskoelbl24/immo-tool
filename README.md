# Objektrechner

Vergleichsrechner für den Kauf einer vermieteten Eigentumswohnung. Eine einzelne HTML-Datei,
kein Build, keine externen Abhängigkeiten.

**Live:** https://markuskoelbl24.github.io/immo-tool/

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
