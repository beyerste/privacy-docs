# eDriver Support

Last updated: November 2026

This page helps you with the iOS, iPadOS and CarPlay app **eDriver** – answers to frequently asked questions
and ways to reach the developer.

---

## 1. Contact

- **Email:** evcalculator@icloud.com

- **Directly from the app:** *Settings → Feedback* – for missing vehicles, plug types or general feedback. You
  can see the full text before sending it by email or as a GitHub issue.

When reporting a problem, please include if possible:

- app version (*Settings*, at the bottom) and iOS version
- device (iPhone, iPad) and, if relevant, vehicle or CarPlay system
- what you did, what happened and what you expected
- for routing problems: start and destination (approximate is fine)

Requests are usually answered within a few days. eDriver is developed by a single person – thank you for your
patience. Requests in English or German are welcome.

---

## 2. Requirements

- iPhone or iPad with iOS / iPadOS 27 or later
- for CarPlay: a vehicle or head unit with Apple CarPlay
- internet connection for maps, route calculation and search
- optional: iCloud sign-in to synchronize between your devices
- optional: your own Home Assistant server for automatic state of charge

---

## 3. Frequently Asked Questions

### Getting Started

**How do I plan a route with charging stops?**
Add your car under *Vehicles* (from the catalog or manually) and set the current state of charge. Then search
for a destination and tap *Directions*. eDriver calculates the energy required and automatically plans charging stops
if the battery is not sufficient. The route plan shows the state of charge on arrival and departure as well as
the charging time for each stop.

**My vehicle is missing from the catalog.**
You can enter the data manually (battery capacity, consumption, charging power, plugs). Feel free to send us the
model via *Settings → Feedback → Vehicle* so it can be added to the catalog.

### Location & Navigation

**My location is not shown.**
Check under *Settings → Privacy & Security → Location Services → eDriver* whether access is allowed. For
guidance in the background and in CarPlay, choose *While Using the App* and keep *Precise Location* turned on.

**I don't hear any voice guidance.**
Check that voice guidance is turned on in the app, and adjust the volume while an instruction is being spoken
(not the ringer volume). In CarPlay, the volume is set on the vehicle.

**The route keeps being recalculated.**
eDriver recalculates when you deviate more than about 45 m from the route. With poor GPS reception (tunnels,
parking garages, dense city centers) this can happen more often. An inaccurate location can often be fixed by
restarting Location Services.

**Route calculation fails.**
Routes are provided by a public server of FOSSGIS e. V. If it is temporarily overloaded or unreachable, try again
after a few seconds. Please also check your internet connection.

### Charging Stations & Charge Planning

**No charging stations are shown on the map.**
- The charging station button on the map cycles through *none*, *filtered* and *all*. Choose *filtered* (green)
  or *all* (blue).
- Charging stations only appear from a certain zoom level – zoom in a little.
- Check the filters for minimum power, operator and plug type. They are ignored with *all*.

**Why isn't a particular charging station planned?**
Charge planning only considers stations with a compatible plug and within the maximum distance from the route
(default 2 km). On motorways, service areas on the opposite carriageway are deliberately excluded. You can replace
any charging stop in the route plan with another station along the route.

**The data for a charging station is wrong or outdated.**
Charging stations come from the charging station registry of the German Federal Network Agency
(Bundesnetzagentur), which is reported by the operators themselves. eDriver uses the data unchanged and updates it
regularly. Errors in the registry can only be corrected by the operator or the Federal Network Agency.

**Does eDriver work outside Germany?**
Navigation and maps work throughout Europe. The Federal Network Agency's registry covers Germany only. Outside
Germany, GoingElectric supplements charge planning where this data source is available.

**The calculated range is not accurate.**
Consumption depends heavily on speed, temperature, heating/air conditioning and load. Adjust your vehicle's
consumption values (city, rural roads, motorway) to match your experience. With Home Assistant, eDriver derives
the actual consumption from your car's state of charge and range.

### Home Assistant

**How do I set up Home Assistant?**
Under *Settings → Vehicle Data*, enter the local and/or external address of your server and a long-lived access
token (in Home Assistant under *Profile → Security → Long-lived access tokens*). Then enter, for each vehicle, the
entity ID for the state of charge in percent and optionally for the range.

**The state of charge is not retrieved.**
- Allow eDriver to access the local network (*Settings → Privacy & Security → Local Network*).
- Check the address (including `http://` or `https://` and port) and the token.
- On the road, an external address is required, e.g. via Home Assistant Cloud (Nabu Casa).
- The entity IDs must exactly match those in Home Assistant (e.g. `sensor.car_battery_level`).

### iCloud & Multiple Devices

**My vehicles and places don't appear on my other device.**
Both devices must be signed in to iCloud with the same Apple Account and allow iCloud for eDriver
(*Settings → [your name] → iCloud*). Synchronization can take a few minutes; open the app on both devices and wait
a moment.

### CarPlay

**eDriver doesn't appear in CarPlay.**
Check under *Settings → General → CarPlay → [your vehicle] → Customize* whether eDriver is shown. If necessary,
disconnect the iPhone from the vehicle briefly and reconnect it.

**iPhone and CarPlay show different routes.**
This shouldn't happen – iPhone and CarPlay share the same navigation state. If it does, end navigation and start
it again, and please report it via *Settings → Feedback*.

---

## 4. Privacy

eDriver works without an account, advertising or tracking. For details, see the
[privacy policy](/eDriver/privacy/en).

---

## 5. Acknowledgements

Maps © OpenStreetMap contributors, tiles by OpenFreeMap. Routing via Valhalla (FOSSGIS e. V.), search via
Photon (komoot). Charging stations from the charging station registry of the German Federal Network Agency
(CC BY 4.0) and from GoingElectric. Closures from Die Autobahn GmbH des Bundes.
