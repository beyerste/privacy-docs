
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
- **Grafische Darstellung** der Reichweite als visuelle Übersicht
- Vergleichsmodus für zwei Verbrauchsprofile nebeneinander
- Farbkodierte Zeilen nach Ladestand:
  - Grün: 80–100%
  - Blau: 50–79%
  - Orange: 20–49%
  - Rot: unter 20% oder unter Mindestladestand
- Anzeige der Energiereserve bei gesetztem Mindestladestand

### Karte & Routenplanung (`MapTabView`)
- **Reichweitenanzeige** als Kreis (Luftlinie) oder richtungsbasiertes Polygon (echte Straßenrouten via MKDirections)
- **Ladestand-Slider** direkt auf der Karte — per Batterie-Icon ausklappbar, Wert wird über App-Neustarts gespeichert
- **Hilfe-Button mit Farblegende** — zeigt Bedeutung der Pin-Farben (rot <22 kW AC, orange <50 kW DC, grün <150 kW DC, blau ≥150 kW HPC)
- **Adresssuche** mit automatischer Routenberechnung (Geocoding via MKGeocodingRequest + MKDirections)
- **Automatische Ladestopplanung** mit intelligentem 2-Pass-Algorithmus (siehe [Ladestop-Algorithmus](#ladestop-algorithmus))
- **Manuelle Ladestop-Verwaltung**: Ladestopps können manuell hinzugefügt (aus Karte) und entfernt werden, manuell hinzugefügte Stopps werden mit Cyan-Icon und „Manuell"-Badge hervorgehoben, Route wird automatisch neu berechnet
- **Start und Ziel in Routenübersicht** — werden immer in der Ladestop-Liste angezeigt, auch ohne Ladestopps
- **Detaillierte Route** über alle Ladestops als separate grüne Polyline
- **Ladestationen auf der Karte** mit Leistungs-Farbkodierung und Clustering
- **Routeninfo-Overlay:** Distanz, Dauer, Energiebedarf, Ankunft-Ladestand, Umwege, Gesamtreisezeit
- **Bottom-Sheet nur bei Route** — das untere Sheet wird nur bei geplanter Route angezeigt
- **Navigation:** Übergabe der Route mit Wegpunkten an Apple Maps oder Google Maps (wählbar in Einstellungen)
- **Straßentyp-Klassifizierung:** Analyse von MKRoute-Steps für segmentbasierten Verbrauch

### Fahrzeugverwaltung (`VehicleListView`)
- Mehrere Fahrzeugprofile mit SwiftData-Persistierung
- Konfigurierbar: Batteriekapazität, Verbrauch (WLTP/Stadt/Land/Autobahn), Ladeleistung (max/Ø), Ladestände (Mindest/Ziel/Ankunft), Strompreis
- **Hersteller- und Modellfelder** für jedes Fahrzeug separat erfasst (bei Katalog-Fahrzeugen schreibgeschützt)
- **Eindeutige UUID** (`stableID`) pro Fahrzeug — Grundlage für iCloud-Synchronisierung und Katalog-Beiträge
- **Fahrzeug-Katalog** beim Anlegen: Auswahl aus einer kuratierten Online-Liste (`beyerste/EMC-Vehicle-DB`) mit automatischer Übernahme aller Werte, oder freie manuelle Anlage. Lokales Caching → Picker funktioniert auch offline. Details siehe `VEHICLE_CATALOG.md`
- **iCloud-Synchronisierung** — Fahrzeuge werden via CloudKit Private Database zwischen allen iCloud-Geräten des Nutzers synchronisiert. Voraussetzung: gleiche Apple ID, iCloud Drive aktiv. Bei fehlender iCloud-Verfügbarkeit fällt der Container automatisch auf die lokale DB zurück
- **Anonyme Katalog-Beiträge** (Opt-Out) — Fahrzeugdaten (Hersteller, Modell, technische Werte) werden anonymisiert in eine CloudKit Public Database geschrieben; vom Maintainer kuratiert in den GitHub-Katalog übernommen. Keine User-ID, kein UDID, kein Standort, kein Strompreis, keine User-Präferenzen
- Demo-Fahrzeug beim ersten Start vorinstalliert
- Berechnete Reichweite und Kosten in der Detailansicht

### Apple CarPlay (`CarPlaySceneDelegate`)
- **Route-Tab** *(ganz links, beim Verbinden direkt aktiv)*: Spiegelung der Ladestopps aus der iPhone-Routenplanung
  - Ladestopp-Liste mit Distanz zum vorherigen Stopp (erster Stopp: Distanz zum Start), Ankunfts- → Abfahrts-Ladestand und max. Ladeleistung
  - Letzter Eintrag: Etappe vom letzten Ladestopp (bzw. vom Start) bis zum Ziel
  - Tatsächliche Reststrecke entlang der Route nur am nächsten anstehenden Eintrag (in Klammern), aktualisiert sich alle 60 Sekunden (Projektion der GPS-Position auf die Routen-Polyline)
  - Aktuelle Etappe (= nächster Eintrag) wird mit grünem Pfeil-Icon hervorgehoben
  - Hinweistext, wenn keine Route aktiv ist
  - Aktualisierung über `RoutePlanStore` (`@Observable`-Singleton) + `Notification.Name.routePlanChanged`
- **Ladestationen-Tab:** Sortierte Liste nahegelegener Ladestationen nach Entfernung
  - Betreiber, Ladeleistung (mit Anzahl Ladepunkte) und Entfernung
  - Entfernungen und Sortierung aktualisieren sich automatisch bei Positionsänderung
  - Neue API-Suche alle 500 m, dazwischen nur Neuberechnung der Entfernungen
  - Tap auf Eintrag zeigt Detailansicht (Adresse, Anschlüsse, Kosten, Status)
  - Navigieren-Button mit rotem Icon öffnet Apple Maps direkt in CarPlay
  - Aktive Filter (Min. Leistung, Betreiber) als kompakter Sektions-Header
  - Fallback auf alle Betreiber, wenn kein bevorzugter in der Nähe
  - Aktualisierung bei Änderungen in den Ladeplanungseinstellungen
- **Fahrzeug-Tab:** Aktuelle Fahrzeugdaten, Reichweiten pro Verbrauchsmodus und Ladetabelle
  - Batterietabelle mit Reichweiten bei 100 %, 80 %, 60 %, 40 %, 20 % (+ Mindestladestand)
  - Automatische Verbrauchsmodus-Wahl basierend auf Fahrgeschwindigkeit:
    0–55 km/h → Stadt, 56–105 km/h → Außerorts, ≥ 106 km/h → Autobahn
  - Modus und Geschwindigkeit im Sektions-Header angezeigt
- Automatische Aktualisierung bei Fahrzeugwechsel in der iOS-App (via Notification)
- Navigation zu Ladestationen direkt aus CarPlay heraus

### Einstellungen (`SettingsView`)
- Sprache: Deutsch / Englisch
- Einheiten: Kilometer / Meilen
- Währung: EUR, USD, GBP, CHF
- Verbrauchsmodus (WLTP/Stadt/Land/Autobahn)
- Reichweitenanzeige (Aus/Kreis/Routenbasiert)
- Standard-Fahrzeug
- Navigations-App: Apple Maps / Google Maps
- Ladestation-Datenquelle und Filter
- **iCloud**: Hinweis zur Synchronisierung der eigenen Fahrzeuge + Opt-Out-Toggle „Anonyme Beiträge zum Fahrzeug-Katalog erlauben"
