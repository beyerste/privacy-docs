# Privacy Policy

**EV Calculator**
Last updated: 13. May 2026

---

### 1. Introduction

This privacy policy describes how the app "EV Calculator" (hereinafter "the app") handles your data. Protecting your privacy is important to us. The app was designed to collect and process as little data as possible.

### 2. Data Controller

Stefan Beyer
Email: evcalculator@icloud.com

### 3. Principle: Data Minimization

The app is designed to process as little data as possible. There is:

- No app-specific user account or registration
- No analytics or tracking services
- No advertising
- No sharing of data with third parties for advertising or analytics purposes

Your app data is stored primarily on the device. Optionally and transparently, **Apple iCloud** is used to sync between your own devices, and **anonymous contributions** are sent to a public vehicle catalog (see Sections 4 and 6).

### 4. What Data Is Stored and Where?

#### 4.1 Vehicle Data (Local + iCloud)
You can create vehicle profiles with technical data (name, manufacturer, model, battery capacity, consumption values, charging power, charge levels, electricity price). This data is:

- **Stored locally** in the app's database (SwiftData) on your device
- **Synced to your personal iCloud (Private Database)** if you are signed in with an Apple ID and have iCloud Drive enabled. Sync uses the standard Apple CloudKit mechanisms. Only you have access — we as the app provider cannot see this data.

If you disable iCloud or sign out, the data remains exclusively on the local device.

#### 4.2 Settings
Your app settings (language, units, currency, consumption mode, display mode, charger filters, iCloud sync toggle) are stored locally in your device's UserDefaults.

#### 4.3 API Keys
If you enter a custom API key for Open Charge Map, it is stored locally on your device. It is only used for direct requests to the respective service.

#### 4.4 Anonymous Device Hash
On first launch, the app generates a random UUID once and stores it locally. It is used solely to associate anonymous catalog contributions (see 6.4) with a device so that updates can be recognized. It has **no relation** to your Apple ID, name, location, or device hardware (no UDID, no IDFA, no IMEI).

### 5. Location Data

The app uses your location **only while actively in use** ("While Using"). Your location is needed for:

- Displaying your position on the map
- Calculating range from your current location
- Searching for charging stations nearby
- Route planning from your location to a destination

**Your location is not permanently stored** and is not shared with third parties for advertising or analytics purposes. The location is only kept in memory while the app is active.

### 6. Network Communication

The app communicates with external services only in the following cases:

#### 6.1 Charging Station Search
When you actively search for charging stations, the following data is transmitted to the selected provider:

- **GoingElectric** (api.goingelectric.de): Your approximate coordinates (latitude/longitude) and search parameters (radius, filters). Privacy Policy: https://www.goingelectric.de/datenschutz/
- **Open Charge Map** (api.openchargemap.io): Your approximate coordinates and search parameters. Privacy Policy: https://openchargemap.org/site/profile/privacy

This transmission occurs only upon your active request (e.g., when you open the map or plan a route).

#### 6.2 Route Calculation
When planning routes, start and destination coordinates are processed through Apple's MapKit service. Apple's privacy policy applies: https://www.apple.com/legal/privacy/

#### 6.3 Vehicle Catalog (Download)
The app downloads a publicly visible JSON file with a curated list of electric vehicles from **GitHub** (raw.githubusercontent.com, repository `beyerste/EMC-Vehicle-DB`). **No personal data is transmitted** in this process — it is a simple HTTPS download comparable to fetching a web page. GitHub may log technical data such as IP addresses according to its privacy policy: https://docs.github.com/site-policy/privacy-policies/github-privacy-statement

#### 6.4 Anonymous Contributions to the Vehicle Catalog (CloudKit Public Database)
To help grow the vehicle catalog, the app **by default** submits anonymous vehicle data to Apple's CloudKit Public Database (container `iCloud.de.beyerste.EVManualCalculation`).

**What is transmitted:** Manufacturer, model, display name, battery capacity, consumption values (WLTP/city/rural/highway), maximum and average charging power, catalog reference ID (if selected from catalog), device hash (random UUID), submission timestamp, app version, and selected language.

**What is NOT transmitted:** Apple ID, UDID, IDFA, name, email, location, electricity price, personal charge levels (minimum/target/arrival), route planning data, search queries, or any other usage data.

**Use:** The submitted data is used exclusively to expand the public vehicle catalog with quality-checked entries. It is not shared, not used for advertising, and not analyzed.

**Control:** You can disable this feature at any time in the app settings under "iCloud → Anonymous Contributions to Vehicle Catalog". After disabling, no further data will be transmitted. You can request deletion of previously submitted records (see Section 10).

#### 6.5 No Other Connections
The app does not establish any other network connections. There are no analytics servers, no ad networks, and no other third-party services.

### 7. Apple CarPlay

The CarPlay feature displays charging stations and vehicle data on the CarPlay screen. It uses the same data and services as the main app (see sections 5 and 6). No additional data is collected.

### 8. Data Sharing with Third Parties

The app does not share personal data with third parties, except in the cases described in section 6 (charging station search and route calculation), where technically necessary data (coordinates) is transmitted to the respective services.

### 9. Data Security

All locally stored data is subject to the security mechanisms of your iOS device (app sandbox, device encryption). Communication with external services is conducted exclusively via encrypted HTTPS connections.

### 10. Your Rights

You can at any time:

- Delete all vehicle data within the app (also affects iCloud sync)
- Disable anonymous catalog contributions in the app settings
- Disable iCloud sync for this app in iOS system settings
- Revoke location permission in iOS Settings
- Completely remove the app and all locally stored data from your device

**Deletion of anonymous catalog contributions:** If you would like already-submitted anonymous contributions to be removed from the CloudKit Public Database, contact us with your anonymous device hash (visible in Settings → Diagnostics, if enabled) or the manufacturer/model of the affected vehicles. We can then manually remove the records.

**iCloud data:** Data in your iCloud Private Database is tied to your own Apple ID. We as the app provider have no access to it. You can delete this app's iCloud data separately via iOS Settings.

### 11. Children

The app is not directed at children under 13 and does not knowingly collect data from children.

### 12. Changes

This privacy policy may be updated with app updates. Significant changes will be communicated in the app's release notes.

### 13. Contact

For privacy-related questions, contact us at:
evcalculator@icloud.com
