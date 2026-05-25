# Datenschutzrichtlinie

**EV Calculator**
Stand: 13. Mai 2026

### 1. Einleitung

Diese Datenschutzrichtlinie beschreibt, wie die App „EV Calculator" (nachfolgend „die App") mit Ihren Daten umgeht. Der Schutz Ihrer Privatsphäre ist uns wichtig. Die App wurde so entwickelt, dass sie so wenig Daten wie möglich erhebt und verarbeitet.

### 2. Verantwortlicher

Stefan Beyer
E-Mail: evcalculator@icloud.com

### 3. Grundsatz: Datenminimierung

Die App ist so gestaltet, dass möglichst wenige Daten verarbeitet werden. Es gibt:

- Kein eigenes Benutzerkonto und keine Registrierung
- Keine Analyse- oder Tracking-Dienste
- Keine Werbung
- Keine Weitergabe von Daten an Dritte zu Werbe- oder Analysezwecken

Ihre App-Daten werden primär lokal gespeichert. Optional und transparent kommt **Apple iCloud** für die Synchronisierung zwischen Ihren eigenen Geräten zum Einsatz sowie **anonyme Beiträge** zu einem öffentlichen Fahrzeug-Katalog (siehe Abschnitt 4 und 6).

### 4. Welche Daten werden gespeichert und wo?

#### 4.1 Fahrzeugdaten (lokal + iCloud)
Sie können Fahrzeugprofile mit technischen Daten anlegen (Name, Hersteller, Modell, Batteriekapazität, Verbrauchswerte, Ladeleistung, Ladestände, Strompreis). Diese Daten werden:

- **Lokal** auf Ihrem Gerät in der App-Datenbank (SwiftData) gespeichert
- **In Ihre persönliche iCloud (Private Database)** synchronisiert, sofern Sie mit einer Apple ID angemeldet sind und iCloud Drive aktiviert haben. Die Synchronisierung erfolgt über die Standard-Mechanismen von Apple CloudKit. Nur Sie selbst haben Zugriff auf diese Daten — auch wir als App-Anbieter sehen sie nicht.

Falls Sie iCloud deaktivieren oder sich abmelden, verbleiben die Daten ausschließlich lokal auf dem Gerät.

#### 4.2 Einstellungen
Ihre App-Einstellungen (Sprache, Einheiten, Währung, Verbrauchsmodus, Anzeigemodus, Ladestationsfilter, iCloud-Sync-Toggle) werden lokal in den UserDefaults Ihres Geräts gespeichert.

#### 4.3 API-Schlüssel
Falls Sie einen eigenen API-Schlüssel für Open Charge Map eingeben, wird dieser lokal auf Ihrem Gerät gespeichert. Er wird nur für direkte Anfragen an den jeweiligen Dienst verwendet.

#### 4.4 Anonymer Geräte-Hash
Beim ersten Start der App wird einmalig eine zufällige UUID generiert und lokal gespeichert. Diese dient ausschließlich dazu, anonyme Katalog-Beiträge (siehe 6.3) dem Gerät zuzuordnen, damit Aktualisierungen erkannt werden können. Sie enthält **keinerlei Bezug** zu Ihrer Apple ID, Ihrem Namen, Ihrem Standort oder Ihrer Geräte-Hardware (kein UDID, keine IDFA, keine IMEI).

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

#### 6.3 Fahrzeug-Katalog (Download)
Die App lädt von **GitHub** (raw.githubusercontent.com, Repository `beyerste/EMC-Vehicle-DB`) eine öffentlich einsehbare JSON-Datei mit einer kuratierten Liste von Elektrofahrzeugen. Dabei werden **keine personenbezogenen Daten übertragen** — es handelt sich um einen einfachen HTTPS-Download wie beim Abruf einer Webseite. GitHub kann gemäß seiner Datenschutzrichtlinie technische Daten wie IP-Adressen protokollieren: https://docs.github.com/site-policy/privacy-policies/github-privacy-statement

#### 6.4 Anonyme Beiträge zum Fahrzeug-Katalog (CloudKit Public Database)
Damit der Fahrzeug-Katalog wachsen kann, übermittelt die App **standardmäßig** anonyme Fahrzeugdaten in Apples CloudKit Public Database (Container `iCloud.de.beyerste.EVManualCalculation`).

**Übermittelt werden:** Hersteller, Modell, Anzeigename, Akkukapazität, Verbrauchswerte (WLTP/Stadt/Land/Autobahn), maximale und durchschnittliche Ladeleistung, Katalog-Referenz-ID (falls aus dem Katalog gewählt), Geräte-Hash (zufällige UUID), Submission-Zeitpunkt, App-Version und gewählte Sprache.

**Nicht übermittelt werden:** Apple ID, UDID, IDFA, Name, E-Mail, Standort, Strompreis, persönliche Ladestände (Mindest-/Ziel-/Ankunftsladestand), Routenplanungen, Suchanfragen oder sonstige Nutzungsdaten.

**Verwendung:** Die übermittelten Daten werden ausschließlich dazu verwendet, den öffentlichen Fahrzeug-Katalog mit qualitätsgeprüften Einträgen zu erweitern. Sie werden nicht weitergegeben, nicht für Werbung genutzt und nicht ausgewertet.

**Steuerung:** Sie können diese Funktion in den App-Einstellungen unter „iCloud → Anonyme Beiträge zum Fahrzeug-Katalog" jederzeit deaktivieren. Nach Deaktivierung werden keine weiteren Daten übermittelt. Bereits übermittelte Datensätze können Sie auf Anfrage löschen lassen (siehe Abschnitt 13).

#### 6.5 Keine sonstigen Verbindungen
Die App stellt keine weiteren Netzwerkverbindungen her. Es gibt keine Analyse-Server, keine Werbenetzwerke und keine sonstigen Drittanbieter-Dienste.

### 7. Apple CarPlay

Die CarPlay-Funktion zeigt Ladestationen und Fahrzeugdaten auf dem CarPlay-Display an. Es werden dabei dieselben Daten und Dienste wie in der Hauptapp verwendet (siehe Abschnitte 5 und 6). Es werden keine zusätzlichen Daten erhoben.

### 8. Datenweitergabe an Dritte

Die App gibt keine personenbezogenen Daten an Dritte weiter, außer in den unter Abschnitt 6 beschriebenen Fällen (Ladestationssuche und Routenberechnung), bei denen technisch notwendige Daten (Koordinaten) an die jeweiligen Dienste übermittelt werden.

### 9. Datensicherheit

Alle lokal gespeicherten Daten unterliegen den Sicherheitsmechanismen Ihres iOS-Geräts (App-Sandbox, Geräteverschlüsselung). Die Kommunikation mit externen Diensten erfolgt ausschließlich über verschlüsselte HTTPS-Verbindungen.

### 10. Ihre Rechte

Sie können jederzeit:

- Alle Fahrzeugdaten in der App löschen (wirkt auch in der iCloud-Sync)
- Anonyme Katalog-Beiträge in den App-Einstellungen deaktivieren
- Die iCloud-Synchronisierung in den iOS-Systemeinstellungen für die App deaktivieren
- Die Standortberechtigung in den iOS-Einstellungen widerrufen
- Die App und damit alle lokal gespeicherten Daten vollständig von Ihrem Gerät entfernen

**Löschung anonymer Katalog-Beiträge:** Wenn Sie möchten, dass bereits übermittelte anonyme Beiträge aus der CloudKit Public Database entfernt werden, kontaktieren Sie uns mit Ihrem anonymen Geräte-Hash (zu finden in den Einstellungen → Diagnose, sofern aktiviert) oder schicken Sie uns Hersteller/Modell der betroffenen Fahrzeuge. Wir können die Records dann manuell entfernen.

**iCloud-Daten:** Daten in Ihrer iCloud Private Database unterliegen Ihrer eigenen Apple-ID. Wir als App-Anbieter haben keinen Zugriff darauf. Über die iOS-Einstellungen können Sie iCloud-Daten dieser App separat löschen.

### 11. Kinder

Die App richtet sich nicht an Kinder unter 13 Jahren und erhebt wissentlich keine Daten von Kindern.

### 12. Änderungen

Diese Datenschutzrichtlinie kann bei Updates der App angepasst werden. Wesentliche Änderungen werden in den Release-Informationen der App kommuniziert.

### 13. Kontakt

Bei Fragen zum Datenschutz erreichen Sie uns unter:
evcalculator@icloud.com
