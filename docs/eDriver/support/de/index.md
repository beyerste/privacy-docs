# Support für eDriver

Stand: November 2026

Hier findest du Hilfe zur iOS-, iPadOS- und CarPlay-App **eDriver** – Antworten auf häufige Fragen und die
Möglichkeiten, den Entwickler zu erreichen.

---

## 1. Kontakt

- **E-Mail:** evcalculator@icloud.com
- **Direkt aus der App:** *Einstellungen → Rückmeldung* – für fehlende Fahrzeuge, Steckertypen oder allgemeines
  Feedback. Du siehst den vollständigen Text, bevor du ihn per Mail oder als GitHub-Issue sendest.

Bitte gib bei Fehlern möglichst an:

- App-Version (*Einstellungen*, unten) und iOS-Version
- Gerät (iPhone, iPad) und ggf. Fahrzeug bzw. CarPlay-System
- was du gemacht hast, was passiert ist und was du erwartet hättest
- bei Routing-Problemen Start und Ziel (ungefähr genügt)

Anfragen werden in der Regel innerhalb weniger Tage beantwortet. eDriver wird von einer einzelnen Person
entwickelt – danke für deine Geduld.

---

## 2. Voraussetzungen

- iPhone oder iPad mit iOS / iPadOS 27 oder neuer
- für CarPlay: ein Fahrzeug oder Radio mit Apple CarPlay
- Internetverbindung für Karten, Routenberechnung und Suche
- optional: iCloud-Anmeldung für die Synchronisation zwischen deinen Geräten
- optional: ein eigener Home-Assistant-Server für den automatischen Akkustand

---

## 3. Häufige Fragen

### Erste Schritte

**Wie plane ich eine Route mit Ladestopps?**
Lege unter *Fahrzeuge* dein Auto an (aus dem Katalog oder manuell) und stelle den aktuellen Akkustand ein. Such
dann ein Ziel und tippe auf *Route*. eDriver berechnet den Energiebedarf und plant Ladestopps automatisch ein,
wenn der Akku nicht reicht. Im Routenplan siehst du Ankunfts- und Abfahrts-Akkustand sowie die Ladedauer je Stopp.

**Mein Fahrzeug fehlt im Katalog.**
Du kannst die Daten manuell eingeben (Akkukapazität, Verbrauch, Ladeleistung, Stecker). Schick uns das Modell
gern über *Einstellungen → Rückmeldung → Fahrzeug*, damit es in den Katalog aufgenommen wird.

### Standort & Navigation

**Mein Standort wird nicht angezeigt.**
Prüfe unter *Einstellungen → Datenschutz & Sicherheit → Ortungsdienste → eDriver*, ob der Zugriff erlaubt ist.
Für die Zielführung im Hintergrund und in CarPlay wähle *Beim Verwenden der App* und lass *Genauer Standort*
eingeschaltet.

**Ich höre keine Sprachansagen.**
Prüfe, ob die Sprachansagen in der App eingeschaltet sind, und die Lautstärke während einer Ansage (nicht die
Ruftonlautstärke). In CarPlay wird die Lautstärke am Fahrzeug eingestellt.

**Die Route wird ständig neu berechnet.**
eDriver berechnet neu, wenn du mehr als ca. 45 m von der Route abweichst. Bei schlechtem GPS-Empfang (Tunnel,
Parkhaus, Häuserschluchten) kann das häufiger passieren. Ein ungenauer Standort lässt sich oft durch einen
Neustart der Ortungsdienste beheben.

**Die Routenberechnung schlägt fehl.**
Die Routen kommen von einem öffentlichen Server der FOSSGIS e. V. Ist er kurzzeitig überlastet oder nicht
erreichbar, versuch es nach einigen Sekunden erneut. Prüfe auch deine Internetverbindung.

### Ladestationen & Ladeplanung

**Auf der Karte werden keine Ladestationen angezeigt.**
- Der Ladestationsknopf auf der Karte wechselt reihum zwischen *keine*, *gefiltert* und *alle*. Wähle
  *gefiltert* (grün) oder *alle* (blau).
- Ladestationen erscheinen erst ab einer bestimmten Zoomstufe – zoom etwas näher heran.
- Prüfe die Filter für Mindestleistung, Betreiber und Steckertyp. Mit *alle* werden sie ignoriert.

**Warum wird eine bestimmte Ladestation nicht eingeplant?**
Die Ladeplanung berücksichtigt nur Stationen mit passendem Stecker und innerhalb des maximalen Abstands zur
Route (Standard 2 km). Raststätten auf der Gegenfahrbahn werden auf Autobahnen bewusst nicht eingeplant. Du kannst
jeden Ladestopp im Routenplan durch eine andere Station entlang der Route ersetzen.

**Die Daten zu einer Ladestation sind falsch oder veraltet.**
Die Ladestationen stammen aus dem Ladesäulenregister der Bundesnetzagentur, das die Betreiber selbst melden.
eDriver übernimmt die Daten unverändert und aktualisiert sie regelmäßig. Fehler im Register lassen sich nur beim
Betreiber oder bei der Bundesnetzagentur korrigieren.

**Funktioniert eDriver im Ausland?**
Navigation und Karte funktionieren europaweit. Das Ladesäulenregister der Bundesnetzagentur umfasst nur
Deutschland. Außerhalb Deutschlands ergänzt GoingElectric die Ladeplanung, sofern diese Datenquelle verfügbar ist.

**Die berechnete Reichweite stimmt nicht.**
Der Verbrauch hängt stark von Geschwindigkeit, Temperatur, Heizung/Klima und Zuladung ab. Passe die
Verbrauchswerte deines Fahrzeugs (Stadt, Landstraße, Autobahn) an deine Erfahrung an. Mit Home Assistant leitet
eDriver den tatsächlichen Verbrauch aus Akkustand und Reichweite deines Autos ab.

### Home Assistant

**Wie richte ich Home Assistant ein?**
Unter *Einstellungen → Fahrzeugdaten* trägst du die lokale und/oder externe Adresse deines Servers und ein
langlebiges Zugriffstoken ein (in Home Assistant unter *Profil → Sicherheit → Langlebige Zugriffstoken*). Danach
gibst du je Fahrzeug die Entity-ID für den Akkustand in Prozent und optional für die Reichweite an.

**Der Akkustand wird nicht abgerufen.**
- Erlaube eDriver den Zugriff auf das lokale Netzwerk (*Einstellungen → Datenschutz & Sicherheit → Lokales
  Netzwerk*).
- Prüfe Adresse (inkl. `http://` bzw. `https://` und Port) und Token.
- Unterwegs ist eine externe Adresse nötig, z. B. über Home Assistant Cloud (Nabu Casa).
- Die Entity-IDs müssen exakt mit denen in Home Assistant übereinstimmen (z. B. `sensor.auto_battery_level`).

### iCloud & mehrere Geräte

**Meine Fahrzeuge und Orte erscheinen nicht auf dem anderen Gerät.**
Beide Geräte müssen mit demselben Apple Account bei iCloud angemeldet sein und iCloud für eDriver erlauben
(*Einstellungen → [dein Name] → iCloud*). Die Synchronisation kann einige Minuten dauern; öffne die App auf beiden
Geräten und warte kurz.

### CarPlay

**eDriver erscheint nicht in CarPlay.**
Prüfe unter *Einstellungen → Allgemein → CarPlay → [dein Fahrzeug] → Anpassen*, ob eDriver eingeblendet ist.
Trenne das iPhone ggf. kurz vom Fahrzeug und verbinde es erneut.

**iPhone und CarPlay zeigen unterschiedliche Routen.**
Das sollte nicht passieren – iPhone und CarPlay teilen sich denselben Navigationszustand. Falls doch, beende die
Navigation und starte sie erneut, und melde uns den Fall bitte über *Einstellungen → Rückmeldung*.

---

## 4. Datenschutz

eDriver kommt ohne Benutzerkonto, Werbung und Tracking aus. Details findest du in der
[Datenschutzerklärung](</eDriver/privacy/de/>).

---

## 5. Danksagung

Karten © OpenStreetMap-Mitwirkende, Kacheln von OpenFreeMap. Routing über Valhalla (FOSSGIS e. V.), Suche über
Photon (komoot). Ladestationen aus dem Ladesäulenregister der Bundesnetzagentur (CC BY 4.0) sowie von
GoingElectric. Sperrungen von der Autobahn GmbH des Bundes.
