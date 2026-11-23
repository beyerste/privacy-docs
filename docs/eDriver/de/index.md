# Datenschutzerklärung für eDriver

Stand: November 2026

Diese Datenschutzerklärung informiert dich darüber, welche personenbezogenen Daten bei der Nutzung der
iOS-, iPadOS- und CarPlay-App **eDriver** verarbeitet werden, zu welchem Zweck das geschieht und welche
Rechte du nach der Datenschutz-Grundverordnung (DSGVO) hast.

---

## 1. Verantwortlicher

Stefan Beyer

E-Mail: evcalculator@icloud.com

Ein Datenschutzbeauftragter ist nicht bestellt, da hierzu keine gesetzliche Pflicht besteht.

---

## 2. Grundsätze

- **Kein Benutzerkonto:** eDriver lässt sich ohne Registrierung oder Anmeldung nutzen.
- **Keine Werbung, kein Tracking:** Die App enthält keine Werbung und keine Analyse-, Tracking- oder
  Crash-Reporting-SDKs von Drittanbietern. Es werden keine Nutzungsprofile erstellt.
- **Kein eigener Server:** Der Entwickler betreibt keinen eigenen Server, an den die App personenbezogene
  Daten überträgt. Daten werden nur an die unten genannten Dienste gesendet, soweit dies für die jeweilige
  Funktion technisch nötig ist.
- **Daten bleiben bei dir:** Deine Fahrzeuge, gespeicherten Orte und Einstellungen liegen auf deinem Gerät
  und – sofern aktiviert – in deiner privaten iCloud. Der Entwickler hat darauf keinen Zugriff.

---

## 3. Datenverarbeitung in der App

### 3.1 Standortdaten

Mit deiner Erlaubnis verwendet eDriver den Standort deines Geräts, um

- deine Position auf der Karte anzuzeigen,
- Routen ab deinem aktuellen Standort zu berechnen,
- Ladestationen in deiner Umgebung bzw. entlang der Route zu laden,
- während einer aktiven Navigation die Zielführung und Sprachansagen bereitzustellen – auf Wunsch auch,
  wenn die App im Hintergrund läuft oder über CarPlay genutzt wird.

Die Standortdaten werden auf dem Gerät verarbeitet. Zur Routenberechnung und zur Ladestationssuche werden
Koordinaten an die in Abschnitt 4 genannten Dienste gesendet. Ein Bewegungsprofil wird weder gespeichert noch
an den Entwickler übermittelt. Du kannst die Standortfreigabe jederzeit unter *Einstellungen → Datenschutz &
Sicherheit → Ortungsdienste → eDriver* ändern oder widerrufen.

**Rechtsgrundlage:** Art. 6 Abs. 1 lit. b DSGVO (Bereitstellung der von dir angeforderten Funktion) sowie
§ 25 Abs. 2 Nr. 2 TDDDG; der Zugriff auf den Standort erfolgt nur nach deiner Einwilligung über den
Systemdialog von iOS.

### 3.2 Lokal gespeicherte Daten

Folgende Daten speichert die App auf deinem Gerät:

- Fahrzeuge (Modell, Akkukapazität, Verbrauchswerte, Akkustand, Steckertypen)
- gespeicherte Orte (z. B. „Zuhause“, „Arbeit“) und zuletzt angefahrene Ziele
- Einstellungen zu Karte, Routing und Ladeplanung
- eine mitgelieferte Offline-Kopie des Ladesäulenregisters der Bundesnetzagentur

Diese Daten werden gelöscht, wenn du sie in der App entfernst oder die App deinstallierst.

### 3.3 Synchronisation über iCloud

Wenn du auf deinem Gerät mit einem Apple Account bei iCloud angemeldet bist, synchronisiert eDriver
Fahrzeuge, gespeicherte Orte, zuletzt angefahrene Ziele und die Home-Assistant-Adressen über **deine private
iCloud-Datenbank** bzw. den iCloud-Schlüssel-Wert-Speicher zwischen deinen Geräten. Der Home-Assistant-
Zugriffstoken wird im **iCloud-Schlüsselbund** gespeichert.

Diese Daten werden von Apple verarbeitet und sind verschlüsselt; der Entwickler kann sie weder einsehen noch
darauf zugreifen. Du kannst die iCloud-Synchronisation für eDriver unter *Einstellungen → [dein Name] →
iCloud* deaktivieren und die gespeicherten Daten dort auch löschen.

Anbieter: Apple Distribution International Ltd., Hollyhill Industrial Estate, Hollyhill, Cork, Irland.
Datenschutzhinweise: <https://www.apple.com/de/legal/privacy/>

**Rechtsgrundlage:** Art. 6 Abs. 1 lit. b DSGVO.

### 3.4 Home Assistant (optional)

Wenn du die Home-Assistant-Anbindung einrichtest, ruft eDriver Akkustand und Reichweite deiner Fahrzeuge
direkt von **deinem eigenen Home-Assistant-Server** ab – im lokalen Netzwerk oder über die von dir angegebene
externe Adresse (z. B. Home Assistant Cloud / Nabu Casa). Hierfür fragt iOS einmalig die Berechtigung für das
lokale Netzwerk ab.

Die Kommunikation findet ausschließlich zwischen deinem Gerät und deinem Server statt. Der Entwickler erhält
keine dieser Daten. Für die Verarbeitung auf deinem Server bzw. bei deinem Fernzugriffsanbieter gelten deren
Bestimmungen.

**Rechtsgrundlage:** Art. 6 Abs. 1 lit. b DSGVO.

### 3.5 Mitteilungen

Mit deiner Erlaubnis zeigt eDriver **lokale** Mitteilungen an, z. B. wenn am Ladestopp das geplante Ladeziel
erreicht ist. Diese Mitteilungen werden auf dem Gerät erzeugt; dafür werden keine Daten an Server übertragen.
Die Erlaubnis kannst du jederzeit unter *Einstellungen → Mitteilungen → eDriver* widerrufen.

### 3.6 Sprachansagen

Sprachansagen während der Navigation werden mit der Sprachausgabe von iOS direkt auf dem Gerät erzeugt.
Es werden keine Audiodaten aufgenommen oder übertragen.

### 3.7 Rückmeldungen an den Entwickler

Über *Einstellungen → Rückmeldung* kannst du Fahrzeugdaten, Steckertypen oder allgemeines Feedback senden.
Eine Nachricht wird nur erstellt, wenn du das ausdrücklich auslöst, und du siehst den vollständigen Text vor
dem Senden. Neben deinen Eingaben werden die App-Version und – nur wenn du das auswählst – die iOS-Version
und das Gerätemodell angehängt. Standorte oder Kennungen werden nicht übermittelt.

Du hast zwei Möglichkeiten:

- **Per E-Mail** über deine Mail-App an evcalculator@icloud.com. Dabei erhält der Entwickler deine
  E-Mail-Adresse und den Inhalt der Nachricht. Die E-Mail wird nur zur Bearbeitung deines Anliegens verwendet
  und gelöscht, sobald sie nicht mehr benötigt wird, sofern keine gesetzlichen Aufbewahrungspflichten
  bestehen.
- **Als Issue auf GitHub** (<https://github.com/beyerste/privacy-docs>). Dafür ist ein GitHub-Konto nötig.
  Issues sind **öffentlich einsehbar**. Anbieter ist GitHub, Inc., 88 Colin P. Kelly Jr. Street,
  San Francisco, CA 94107, USA. Dabei können Daten in die USA übermittelt werden; GitHub ist unter dem
  EU-U.S. Data Privacy Framework zertifiziert. Datenschutzhinweise:
  <https://docs.github.com/de/site-policy/privacy-policies/github-general-privacy-statement>

**Rechtsgrundlage:** Art. 6 Abs. 1 lit. b und lit. f DSGVO (berechtigtes Interesse an der Bearbeitung von
Anfragen und der Verbesserung der App).

---

## 4. Übermittlung an Drittanbieter

Für einige Funktionen sendet die App Anfragen direkt an externe Dienste. Dabei wird technisch bedingt deine
**IP-Adresse** an den jeweiligen Server übertragen, zusammen mit den unten genannten Inhalten. Der Entwickler
erhält diese Daten nicht. Es gelten die Datenschutzbestimmungen der jeweiligen Anbieter.

| Dienst | Zweck | Übermittelte Daten |
| --- | --- | --- |
| Valhalla-Routing-Server der FOSSGIS e. V. (valhalla1.openstreetmap.de), Deutschland | Routenberechnung | Start-, Ziel- und Zwischenkoordinaten, Routing-Optionen |
| Photon von komoot (photon.komoot.io), Deutschland | Orts- und Adresssuche | Suchbegriff, ungefähre Kartenposition |
| OpenFreeMap (tiles.openfreemap.org) | Kartendarstellung | angeforderte Kartenausschnitte |
| Apple CloudKit, öffentliche Datenbank | Ladestationen der Bundesnetzagentur im Kartenausschnitt bzw. entlang der Route | Kartenausschnitt bzw. Routenbereich, ohne Benutzerkennung |
| GoingElectric.de | Ladestationen (nur wenn als Datenquelle gewählt oder ergänzend außerhalb Deutschlands) | Kartenausschnitt bzw. Routenbereich |
| Die Autobahn GmbH des Bundes (verkehr.autobahn.de), Deutschland | aktuelle Sperrungen auf Autobahnen | betroffene Autobahnen, keine Standortdaten |

Datenschutzhinweise der Anbieter:

- FOSSGIS e. V.: <https://www.fossgis.de/datenschutzerklaerung/>
- komoot: <https://www.komoot.com/de-de/privacy>
- OpenFreeMap: <https://openfreemap.org>
- Apple: <https://www.apple.com/de/legal/privacy/>
- GoingElectric: <https://www.goingelectric.de/datenschutz/>
- Die Autobahn GmbH des Bundes: <https://www.autobahn.de/datenschutz>

**Rechtsgrundlage:** Art. 6 Abs. 1 lit. b DSGVO (Bereitstellung der angeforderten Funktion).

---

## 5. App Store

eDriver wird über den App Store von Apple vertrieben. Beim Herunterladen, bei Käufen und Updates verarbeitet
Apple Daten in eigener Verantwortung (z. B. Apple Account, Gerätedaten). Darauf hat der Entwickler keinen
Einfluss. Wenn du in den iOS-Einstellungen zugestimmt hast, stellt Apple dem Entwickler anonymisierte
Absturzberichte und Nutzungsstatistiken zur Verfügung, die keinen Rückschluss auf deine Person zulassen.
Näheres findest du in der Datenschutzrichtlinie von Apple: <https://www.apple.com/de/legal/privacy/>

---

## 6. Speicherdauer

- Lokale Daten bleiben gespeichert, bis du sie in der App löschst oder die App deinstallierst.
- iCloud-Daten bleiben in deiner iCloud gespeichert, bis du sie dort löschst.
- Feedback-E-Mails werden gelöscht, sobald dein Anliegen erledigt ist und keine gesetzlichen
  Aufbewahrungspflichten entgegenstehen.
- GitHub-Issues bleiben öffentlich sichtbar, bis sie gelöscht werden. Wenn du das möchtest, wende dich an den
  Entwickler.
- Wie lange Drittanbieter Server-Logdaten (z. B. IP-Adressen) speichern, richtet sich nach deren
  Datenschutzbestimmungen.

---

## 7. Deine Rechte

Nach der DSGVO hast du folgende Rechte, soweit der Entwickler personenbezogene Daten von dir verarbeitet:

- Auskunft (Art. 15 DSGVO)
- Berichtigung (Art. 16 DSGVO)
- Löschung (Art. 17 DSGVO)
- Einschränkung der Verarbeitung (Art. 18 DSGVO)
- Datenübertragbarkeit (Art. 20 DSGVO)
- **Widerspruch** gegen Verarbeitungen auf Grundlage berechtigter Interessen (Art. 21 DSGVO)
- Widerruf erteilter Einwilligungen mit Wirkung für die Zukunft (Art. 7 Abs. 3 DSGVO), z. B. für den Zugriff
  auf Standort, lokales Netzwerk oder Mitteilungen in den iOS-Einstellungen

Wende dich dazu an die in Abschnitt 1 genannte E-Mail-Adresse.

Außerdem hast du das Recht, dich bei einer Datenschutz-Aufsichtsbehörde zu beschweren (Art. 77 DSGVO),
insbesondere in dem Mitgliedstaat deines Wohnorts, deines Arbeitsplatzes oder des mutmaßlichen Verstoßes.

---

## 8. Kinder

eDriver richtet sich nicht an Kinder unter 16 Jahren. Der Entwickler erhebt wissentlich keine
personenbezogenen Daten von Kindern.

---

## 9. Änderungen dieser Datenschutzerklärung

Wenn sich die App oder die rechtlichen Anforderungen ändern, kann diese Datenschutzerklärung angepasst werden.
Es gilt die jeweils aktuelle Fassung, die unter der im App Store angegebenen Adresse abrufbar ist.
