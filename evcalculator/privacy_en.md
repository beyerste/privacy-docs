# Privacy Policy

**EV Calculator**
Last updated: 19. März 2026

---
### 1. Introduction

This privacy policy describes how the app "EV Calculator" (hereinafter "the app") handles your data. Protecting your privacy is important to us. The app was designed to collect and process as little data as possible.

### 2. Data Controller

Stefan Beyer
Email: stefanjbeyer@icloud.com

### 3. Principle: Local Data Processing

The app stores all your data **exclusively on your device**. There is:

- No user account or registration
- No cloud synchronization
- No analytics or tracking services
- No advertising
- No sharing of data with third parties for advertising or analytics purposes

### 4. What Data Is Stored?

#### 4.1 Vehicle Data
You can create vehicle profiles with technical data (name, battery capacity, consumption values, charging power, electricity price). This data is stored exclusively in the local app database (SwiftData) on your device.

#### 4.2 Settings
Your app settings (language, units, currency, consumption mode, display mode, charger filters) are stored locally in your device's UserDefaults.

#### 4.3 API Keys
If you enter a custom API key for Open Charge Map, it is stored locally on your device. It is only used for direct requests to the respective service.

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

#### 6.3 No Other Connections
The app does not establish any other network connections. There are no analytics servers, no ad networks, and no other third-party services.

### 7. Apple CarPlay

The CarPlay feature displays charging stations and vehicle data on the CarPlay screen. It uses the same data and services as the main app (see sections 5 and 6). No additional data is collected.

### 8. Data Sharing with Third Parties

The app does not share personal data with third parties, except in the cases described in section 6 (charging station search and route calculation), where technically necessary data (coordinates) is transmitted to the respective services.

### 9. Data Security

All locally stored data is subject to the security mechanisms of your iOS device (app sandbox, device encryption). Communication with external services is conducted exclusively via encrypted HTTPS connections.

### 10. Your Rights

You can at any time:

- Delete all vehicle data within the app
- Revoke location permission in iOS Settings
- Completely remove the app and all stored data from your device

Since no data is stored on our servers, requests for access, correction, or deletion do not apply — you have full control over your data on your device.

### 11. Children

The app is not directed at children under 13 and does not knowingly collect data from children.

### 12. Changes

This privacy policy may be updated with app updates. Significant changes will be communicated in the app's release notes.

### 13. Contact

For privacy-related questions, contact us at:
stefanjbeyer@icloud.com
