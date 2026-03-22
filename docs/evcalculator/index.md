
# EV Manual Calculation

Eine iOS-App zur manuellen Berechnung von Reichweite, Energiebedarf und Ladeplanung für Elektrofahrzeuge — mit Kartenansicht, automatischer Ladestopplanung und Apple CarPlay-Unterstützung.

---

## Features

### Rechner (`CalculatorView`)
- **Drei Berechnungsmodi:**
  - **Reichweite:** Wie weit komme ich mit X kWh (oder X % Ladestand)?
  - **Energiebedarf:** Wie viel kWh brauche ich für X km?
  - **Maximale Distanz:** Wie weit reicht der volle Akku?
- Berücksichtigung verschiedener Verbrauchsprofile (WLTP, Stadt, Land, Autobahn)
- Automatischer Fallback auf WLTP wenn ein Profil nicht gesetzt ist
- Kostenberechnung basierend auf Strompreis pro kWh
- Anzeige benötigter Ladestops bei unzureichender Reichweite
- Eingabe wahlweise in kWh oder Prozent (bei Reichweiten-Modus)

### Batterietabelle (`BatteryTableView`)
- Übersicht: Ladestand → Reichweite in einstellbaren Schritten (1%, 5%, 10%)
- Vergleichsmodus für zwei Verbrauchsprofile nebeneinander
- Farbkodierte Zeilen nach Ladestand:
  - Grün: 80–100%
  - Blau: 50–79%
  - Orange: 20–49%
  - Rot: unter 20% oder unter Mindestladestand
- Anzeige der Energiereserve bei gesetztem Mindestladestand

### Karte & Routenplanung (`MapTabView`)
- **Reichweitenanzeige** als Kreis (Luftlinie) oder richtungsbasiertes Polygon (echte Straßenrouten via MKDirections)
- **Adresssuche** mit automatischer Routenberechnung (Geocoding + MKDirections)
- **Automatische Ladestopplanung** mit intelligentem 2-Pass-Algorithmus (siehe [Ladestop-Algorithmus](#ladestop-algorithmus))
- **Detaillierte Route** über alle Ladestops als separate grüne Polyline
- **Ladestationen auf der Karte** mit Leistungs-Farbkodierung und Clustering
- **Routeninfo-Overlay:** Distanz, Dauer, Energiebedarf, Ankunft-Ladestand, Umwege, Gesamtreisezeit
- **Navigation:** Übergabe der Route mit Wegpunkten an Apple Maps (Unified Maps Links)
- **Straßentyp-Klassifizierung:** Analyse von MKRoute-Steps für segmentbasierten Verbrauch

### Fahrzeugverwaltung (`VehicleListView`)
- Mehrere Fahrzeugprofile mit SwiftData-Persistierung
- Konfigurierbar: Batteriekapazität, Verbrauch (WLTP/Stadt/Land/Autobahn), Ladeleistung (max/Ø), Ladestände (Mindest/Ziel/Ankunft), Strompreis
- Demo-Fahrzeug beim ersten Start vorinstalliert
- Berechnete Reichweite und Kosten in der Detailansicht

### Apple CarPlay (`CarPlaySceneDelegate`)
- **Ladestationen-Tab:** Nahegelegene Ladestationen als Points of Interest auf der Karte
- **Fahrzeug-Tab:** Aktuelle Fahrzeugdaten und Reichweiten pro Verbrauchsmodus
- Automatische Aktualisierung bei Fahrzeugwechsel in der iOS-App
- Navigation zu Ladestationen direkt aus CarPlay heraus

### Einstellungen (`SettingsView`)
- Sprache: Deutsch / Englisch
- Einheiten: Kilometer / Meilen
- Währung: EUR, USD, GBP, CHF
- Verbrauchsmodus (WLTP/Stadt/Land/Autobahn)
- Reichweitenanzeige (Aus/Kreis/Routenbasiert)
- Standard-Fahrzeug
- Ladestation-Datenquelle und Filter
