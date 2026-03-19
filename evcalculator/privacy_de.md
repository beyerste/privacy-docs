# Datenschutzrichtlinie

**EV Calculator**
Stand: 19. März 2026

---
### 1. Einleitung

Diese Datenschutzrichtlinie beschreibt, wie die App „EV Calculator" (nachfolgend „die App") mit Ihren Daten umgeht. Der Schutz Ihrer Privatsphäre ist uns wichtig. Die App wurde so entwickelt, dass sie so wenig Daten wie möglich erhebt und verarbeitet.

### 2. Verantwortlicher

Stefan Beyer
E-Mail: stefanjbeyer@icloud.com

### 3. Grundsatz: Lokale Datenverarbeitung

Die App speichert alle Ihre Daten **ausschließlich lokal auf Ihrem Gerät**. Es gibt:

- Kein Benutzerkonto und keine Registrierung
- Keine Cloud-Synchronisation
- Keine Analyse- oder Tracking-Dienste
- Keine Werbung
- Keine Weitergabe von Daten an Dritte zu Werbe- oder Analysezwecken

### 4. Welche Daten werden gespeichert?

#### 4.1 Fahrzeugdaten
Sie können Fahrzeugprofile mit technischen Daten anlegen (Name, Batteriekapazität, Verbrauchswerte, Ladeleistung, Strompreis). Diese Daten werden ausschließlich lokal in der App-Datenbank (SwiftData) auf Ihrem Gerät gespeichert.

#### 4.2 Einstellungen
Ihre App-Einstellungen (Sprache, Einheiten, Währung, Verbrauchsmodus, Anzeigemodus, Ladestationsfilter) werden lokal in den UserDefaults Ihres Geräts gespeichert.

#### 4.3 API-Schlüssel
Falls Sie einen eigenen API-Schlüssel für Open Charge Map eingeben, wird dieser lokal auf Ihrem Gerät gespeichert. Er wird nur für direkte Anfragen an den jeweiligen Dienst verwendet.

### 5. Standortdaten

Die App nutzt Ihren Standort **nur während der aktiven Nutzung** („Beim Verwenden"). Der Standort wird benötigt für:

- Anzeige Ihrer Position auf der Karte
- Berechnung der Reichweite ab Ihrem aktuellen Standort
- Suche nach Ladestationen in Ihrer Nähe
- Routenplanung von Ihrem Standort zu einem Ziel

**Ihr Standort wird nicht dauerhaft gespeichert** und nicht an Dritte zu Werbe- oder Analysezwecken weitergegeben. Der Standort wird nur im Arbeitsspeicher gehalten, solange die App aktiv ist.

### 6. Netzwerkkommunikation

Die App kommuniziert ausschließlich in folgenden Fällen mit externen Diensten:

#### 6.1 Ladestationssuche
Wenn Sie aktiv nach Ladestationen suchen, werden folgende Daten an den gewählten Anbieter übermittelt:

- **GoingElectric** (api.goingelectric.de): Ihre ungefähren Koordinaten (Breitengrad/Längengrad) und Suchparameter (Radius, Filter). Datenschutzrichtlinie: https://www.goingelectric.de/datenschutz/
- **Open Charge Map** (api.openchargemap.io): Ihre ungefähren Koordinaten und Suchparameter. Datenschutzrichtlinie: https://openchargemap.org/site/profile/privacy

Diese Übertragung erfolgt nur auf Ihre aktive Anfrage hin (z. B. wenn Sie die Karte öffnen oder eine Route planen).

#### 6.2 Routenberechnung
Bei der Routenplanung werden Start- und Zielkoordinaten über Apples MapKit-Dienst verarbeitet. Es gelten die Datenschutzbestimmungen von Apple: https://www.apple.com/legal/privacy/

#### 6.3 Keine sonstigen Verbindungen
Die App stellt keine weiteren Netzwerkverbindungen her. Es gibt keine Analyse-Server, keine Werbenetzwerke und keine sonstigen Drittanbieter-Dienste.

### 7. Apple CarPlay

Die CarPlay-Funktion zeigt Ladestationen und Fahrzeugdaten auf dem CarPlay-Display an. Es werden dabei dieselben Daten und Dienste wie in der Hauptapp verwendet (siehe Abschnitte 5 und 6). Es werden keine zusätzlichen Daten erhoben.

### 8. Datenweitergabe an Dritte

Die App gibt keine personenbezogenen Daten an Dritte weiter, außer in den unter Abschnitt 6 beschriebenen Fällen (Ladestationssuche und Routenberechnung), bei denen technisch notwendige Daten (Koordinaten) an die jeweiligen Dienste übermittelt werden.

### 9. Datensicherheit

Alle lokal gespeicherten Daten unterliegen den Sicherheitsmechanismen Ihres iOS-Geräts (App-Sandbox, Geräteverschlüsselung). Die Kommunikation mit externen Diensten erfolgt ausschließlich über verschlüsselte HTTPS-Verbindungen.

### 10. Ihre Rechte

Sie können jederzeit:

- Alle Fahrzeugdaten in der App löschen
- Die Standortberechtigung in den iOS-Einstellungen widerrufen
- Die App und damit alle gespeicherten Daten vollständig von Ihrem Gerät entfernen

Da keine Daten auf unseren Servern gespeichert werden, entfallen Auskunfts-, Berichtigungs- und Löschungsanfragen — Sie haben die volle Kontrolle über Ihre Daten auf Ihrem Gerät.

### 11. Kinder

Die App richtet sich nicht an Kinder unter 13 Jahren und erhebt wissentlich keine Daten von Kindern.

### 12. Änderungen

Diese Datenschutzrichtlinie kann bei Updates der App angepasst werden. Wesentliche Änderungen werden in den Release-Informationen der App kommuniziert.

### 13. Kontakt

Bei Fragen zum Datenschutz erreichen Sie uns unter:
stefanjbeyer@icloud.com
