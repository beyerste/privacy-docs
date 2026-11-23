# Privacy Policy for eDriver

Last updated: November 2026

This privacy policy explains which personal data is processed when you use the iOS, iPadOS and CarPlay app
**eDriver**, for what purpose this happens and which rights you have under the General Data Protection
Regulation (GDPR).

In case of any discrepancy, the German version of this privacy policy shall prevail.

---

## 1. Controller

Stefan Beyer

Email: evcalculator@icloud.com

No data protection officer has been appointed, as there is no legal obligation to do so.

---

## 2. Principles

- **No account:** eDriver can be used without registering or signing in.
- **No ads, no tracking:** The app contains no advertising and no third-party analytics, tracking or
  crash-reporting SDKs. No usage profiles are created.
- **No developer server:** The developer does not operate a server to which the app transmits personal data.
  Data is only sent to the services listed below, and only where technically necessary for the respective
  feature.
- **Your data stays with you:** Your vehicles, saved places and settings are stored on your device and – if
  enabled – in your private iCloud. The developer has no access to them.

---

## 3. Data Processing in the App

### 3.1 Location Data

With your permission, eDriver uses your device's location to

- show your position on the map,
- calculate routes from your current location,
- load charging stations near you or along the route,
- provide turn-by-turn guidance and voice instructions during active navigation – if you wish, also while
  the app is running in the background or being used via CarPlay.

Location data is processed on the device. For route calculation and charging station search, coordinates are
sent to the services listed in section 4. No movement profile is stored or transmitted to the developer. You
can change or revoke location access at any time under *Settings → Privacy & Security → Location Services →
eDriver*.

**Legal basis:** Art. 6(1)(b) GDPR (provision of the feature you requested) and Section 25(2) no. 2 of the
German Telecommunications Digital Services Data Protection Act (TDDDG); location is only accessed after you
have given consent via the iOS system dialog.

### 3.2 Data Stored Locally

The app stores the following data on your device:

- vehicles (model, battery capacity, consumption values, state of charge, plug types)
- saved places (e.g. "Home", "Work") and recent destinations
- map, routing and charge planning settings
- a bundled offline copy of the German Federal Network Agency's (Bundesnetzagentur) charging station
  registry

This data is deleted when you remove it in the app or uninstall the app.

### 3.3 Synchronization via iCloud

If you are signed in to iCloud with an Apple Account on your device, eDriver synchronizes vehicles, saved
places, recent destinations and the Home Assistant addresses between your devices via **your private iCloud
database** and the iCloud key-value store. The Home Assistant access token is stored in **iCloud Keychain**.

This data is processed by Apple and is encrypted; the developer can neither view nor access it. You can turn
off iCloud synchronization for eDriver under *Settings → [your name] → iCloud* and delete the stored data
there as well.

Provider: Apple Distribution International Ltd., Hollyhill Industrial Estate, Hollyhill, Cork, Ireland.
Privacy policy: <https://www.apple.com/legal/privacy/>

**Legal basis:** Art. 6(1)(b) GDPR.

### 3.4 Home Assistant (optional)

If you set up the Home Assistant integration, eDriver retrieves the state of charge and range of your vehicles
directly from **your own Home Assistant server** – on your local network or via the external address you
provide (e.g. Home Assistant Cloud / Nabu Casa). For this, iOS asks once for permission to access the local
network.

Communication takes place exclusively between your device and your server. The developer receives none of
this data. Processing on your server or by your remote access provider is subject to their terms.

**Legal basis:** Art. 6(1)(b) GDPR.

### 3.5 Notifications

With your permission, eDriver shows **local** notifications, e.g. when the planned charging target has been
reached at a charging stop. These notifications are generated on the device; no data is sent to servers for
this purpose. You can revoke permission at any time under *Settings → Notifications → eDriver*.

### 3.6 Voice Guidance

Voice instructions during navigation are generated directly on the device using the iOS speech output. No
audio is recorded or transmitted.

### 3.7 Feedback to the Developer

Under *Settings → Feedback* you can submit vehicle data, plug types or general feedback. A message is only
created when you explicitly trigger it, and you can see the full text before sending. In addition to your
input, the app version and – only if you choose to – the iOS version and device model are attached. No
locations or identifiers are transmitted.

You have two options:

- **By email** via your Mail app to evcalculator@icloud.com. The developer receives your email address and
  the content of the message. The email is used only to handle your request and is deleted once it is no
  longer needed, unless statutory retention obligations apply.
- **As an issue on GitHub** (<https://github.com/beyerste/privacy-docs>). This requires a GitHub account.
  Issues are **publicly visible**. The provider is GitHub, Inc., 88 Colin P. Kelly Jr. Street,
  San Francisco, CA 94107, USA. Data may be transferred to the USA in the process; GitHub is certified under
  the EU-U.S. Data Privacy Framework. Privacy statement:
  <https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement>

**Legal basis:** Art. 6(1)(b) and (f) GDPR (legitimate interest in handling requests and improving the app).

---

## 4. Transfer to Third-Party Services

For some features, the app sends requests directly to external services. For technical reasons, your **IP
address** is transmitted to the respective server along with the content listed below. The developer does not
receive this data. The privacy policies of the respective providers apply.

| Service | Purpose | Data transmitted |
| --- | --- | --- |
| Valhalla routing server of FOSSGIS e. V. (valhalla1.openstreetmap.de), Germany | Route calculation | Start, destination and waypoint coordinates, routing options |
| Photon by komoot (photon.komoot.io), Germany | Place and address search | Search term, approximate map position |
| OpenFreeMap (tiles.openfreemap.org) | Map display | Requested map tiles |
| Apple CloudKit, public database | Charging stations from the Federal Network Agency in the visible map area or along the route | Map area or route area, without user identifier |
| GoingElectric.de | Charging stations (only if selected as data source or as a supplement outside Germany) | Map area or route area |
| Die Autobahn GmbH des Bundes (verkehr.autobahn.de), Germany | Current motorway closures | Affected motorways, no location data |

Privacy policies of the providers:

- FOSSGIS e. V.: <https://www.fossgis.de/datenschutzerklaerung/>
- komoot: <https://www.komoot.com/privacy>
- OpenFreeMap: <https://openfreemap.org>
- Apple: <https://www.apple.com/legal/privacy/>
- GoingElectric: <https://www.goingelectric.de/datenschutz/>
- Die Autobahn GmbH des Bundes: <https://www.autobahn.de/datenschutz>

**Legal basis:** Art. 6(1)(b) GDPR (provision of the requested feature).

---

## 5. App Store

eDriver is distributed via Apple's App Store. When you download, purchase or update the app, Apple processes
data under its own responsibility (e.g. Apple Account, device data). The developer has no influence on this.
If you have agreed to it in the iOS settings, Apple provides the developer with anonymized crash reports and
usage statistics that do not allow conclusions to be drawn about your identity. For details, see Apple's
privacy policy: <https://www.apple.com/legal/privacy/>

---

## 6. Retention Period

- Local data remains stored until you delete it in the app or uninstall the app.
- iCloud data remains stored in your iCloud until you delete it there.
- Feedback emails are deleted once your request has been resolved and no statutory retention obligations
  apply.
- GitHub issues remain publicly visible until they are deleted. If you would like this, please contact the
  developer.
- How long third-party providers store server log data (e.g. IP addresses) depends on their privacy
  policies.

---

## 7. Your Rights

Under the GDPR, you have the following rights, insofar as the developer processes personal data about you:

- access (Art. 15 GDPR)
- rectification (Art. 16 GDPR)
- erasure (Art. 17 GDPR)
- restriction of processing (Art. 18 GDPR)
- data portability (Art. 20 GDPR)
- **objection** to processing based on legitimate interests (Art. 21 GDPR)
- withdrawal of consent with effect for the future (Art. 7(3) GDPR), e.g. for access to location, local
  network or notifications in the iOS settings

To exercise these rights, please contact the email address given in section 1.

You also have the right to lodge a complaint with a data protection supervisory authority (Art. 77 GDPR), in
particular in the Member State of your habitual residence, place of work or place of the alleged
infringement.

---

## 8. Children

eDriver is not directed at children under the age of 16. The developer does not knowingly collect personal
data from children.

---

## 9. Changes to This Privacy Policy

This privacy policy may be updated if the app or legal requirements change. The current version, available at
the address provided in the App Store, applies.
