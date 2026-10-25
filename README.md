# ⚡ ELdoroado

**Deutsch** · [English](#english)

Eine private Android-Navigations-App für Elektroautos, entwickelt mit dem **Citroën ë-C4 (2022)** und nutzbar für die **E-Autos von Stellantis** (Citroën, Peugeot, Opel, DS, Jeep, Fiat, Alfa Romeo, Lancia) sowie Leapmotor und eigene Fahrzeugwerte: Routenplanung mit automatischen Ladestopps, Live-Verkehr, OBD2-Akkudaten und einer Oberfläche im Stil von Apple Maps.

> Inspiriert von A Better Routeplanner (ABRP), TomTom und Apple Maps, aber selbst gebaut, ohne Werbung, ohne Konto und ohne Tracking.

---

## Inhalt

- [Funktionen](#funktionen)
- [Voraussetzungen](#voraussetzungen)
- [APK bauen und installieren](#apk-bauen-und-installieren)
- [Erste Einrichtung](#erste-einrichtung)
- [Datenquellen](#datenquellen)
- [Technik und Projektaufbau](#technik-und-projektaufbau)
- [Grenzen](#grenzen)
- [Datenschutz](#datenschutz)
- [Hinweise](#hinweise)

---

## Funktionen

### 🗺️ Karte und Navigation
- Kartenstile **Liberty**, **Positron** und **TomTom**, bei Nacht automatisch **Fiord** oder **Schwarz**
- Bis zu **3 Routenoptionen** (Empfohlen, Alternative, Mautfrei) mit Ankunftszeit, Ladezeit und Akku am Ziel
- Blaue Routenlinie, **nach Verkehr eingefärbt**, gefahrene Strecke grau
- Fahrsymbol wählbar: 3D-Pfeil im TomTom-Stil, Auto (mit Farbwahl) oder Punkt
- **Vorausberechnete Position**: Das Symbol läuft flüssig mit, ohne Verzögerung, und fährt im **Tunnel** bis zu 45 Sekunden ohne GPS weiter
- Abbiege-Banner mit Pfeilen, „Dann …“-Hinweis und **Spurassistent** direkt im Banner
- **Sprachansagen** auf Deutsch, inklusive Spurempfehlung („Benutzen Sie die beiden rechten Spuren“)
- **Tempolimit**-Anzeige, Tempo wird rot bei Überschreitung
- **Stauende-, Baustellen- und Sperrungswarnung** mit Ansage
- Neuberechnung bei Abweichung, Hinweis auf **schnellere Routen** während der Fahrt
- **Offline-Karte** entlang der Route (optional automatisch, nur im WLAN)

### 🔋 Laden und Akku
- **Langstrecken-Planung mit automatischen Ladestopps** (TomTom Long Distance EV Routing) inklusive Ladekurve des ë-C4
- Wetter (Temperatur, Gegenwind, Regen), Höhenprofil, Heizung und Klima fließen in den Verbrauch ein
- Ladestopps mit Leistung, Ladezeit, Ankunfts- und Abfahrts-Akkustand und **Live-Belegung**
- **„Anderen wählen“**: Alternativen rund um einen Ladestopp, auf Karte und Liste, mit eigener Suche
- **Ladestations-Fenster**: Lage (z. B. Raststätte), Ladepunkte je Stecker und Leistung, Öffnungszeiten, **Toiletten, Essen und Einkauf in der Nähe**
- Ladestationen direkt **auf der Karte** und in der **Suche** („Tesla Kamen“, „EnBW Aachen“)
- Bevorzugte und gemiedene **Ladeanbieter**, eigene **Ladekarten**
- **Laden und Parken am Ziel**, Ziel während der Fahrt ändern

### 🚗 Fahrzeuge
- Fahrzeugauswahl: Stellantis e-CMP **1. Generation** (50/46 kWh, z. B. ë-C4, e-208, e-2008, Corsa-e, Mokka-e, DS 3) und **2. Generation** (54/51 kWh, z. B. ë-C4 ab 2023, Avenger, 600e, Junior, Ypsilon), Hochdachkombis, **Leapmotor** (ohne OBD) und **eigene Werte**
- Je Fahrzeug passende Kapazität, Ladeleistung, Ladekurve und Verbrauch

### 🔌 OBD2 (Stellantis e-CMP)
- Bluetooth-LE-Adapter, getestet mit **Vgate iCar Pro 2S**
- Live: Akkustand (SoC), SOH, Energie im Akku, Zellspannungen, Temperaturen, Tempo
- **Plan gegen Ist**: Weicht der Akku vom Plan ab, wird automatisch neu geplant
- Diagnose-Bildschirm mit Rohdaten, Konsole und Protokoll

### 🧠 Lernen
- Fahrten werden automatisch aufgezeichnet, sobald OBD verbunden ist
- Der **Verbrauch wird je Tempo- und Temperaturbereich gelernt** und für die Planung verwendet
- Die **Ladekurve** wird beim Schnellladen gelernt
- Fahrtenliste mit kWh/100 km, Export als Tabelle

### 🔍 Suche und Orte
- Suche mit **Spracheingabe**, Favoriten (Zuhause, Arbeit, eigene), zuletzt gesuchte Ziele
- **Ortsfenster** wie bei Google Maps: Öffnungszeiten, „Jetzt geöffnet“, Telefon, Webseite
- **Orte (POI) auf der Karte** nach Kategorien, antippbar, auch offline
- Zwischenstopps mit Pause, sortierbar

### ✨ Planung mit Wünschen und KI-Assistent
- Wünsche: **nur bestimmte Ladeanbieter** (z. B. Tesla, EnBW) oder Anbieter **meiden**, **Pause zu einer Uhrzeit** an einem Ort (z. B. Burger King, IKEA)
- **KI-Assistent offline auf dem Handy** (llama.cpp): versteht Sätze wie „nach Varazze, nur Tesla, mittags Pause bei IKEA“ und antwortet in normalen Sätzen
- Modelle zum Herunterladen: Qwen3.5 2B (empfohlen), Gemma 4 E2B, Qwen3.5 0.8B

### ⚙️ Sonstiges
- Einstellungen in übersichtlichen Rubriken, Sicherung und Wiederherstellung
- Fehlerprotokoll zum Teilen
- Android-Auto-Unterstützung ist im Code enthalten (siehe [Grenzen](#grenzen))

---

## Voraussetzungen

| Was | Wofür | Pflicht? |
|---|---|---|
| Android 8.0 oder neuer | App | ✅ |
| **TomTom API-Key** (kostenlos, [developer.tomtom.com](https://developer.tomtom.com)) | Verkehr, Ladeplanung, Spuren, Tempolimits, Ladesäulen, TomTom-Karte | empfohlen |
| Freigeschaltete TomTom-Produkte | Routing, Long Distance EV Routing, Search, EV Charging Availability, Traffic, Map Display | empfohlen |
| OBD2-Adapter (Bluetooth LE) | Live-Akkudaten | optional |
| GitHub-Konto | APK automatisch bauen lassen | ✅ |

Ohne TomTom-Key läuft die App mit freiem Routing (OSRM) und einer einfachen Akku-Schätzung, aber ohne Verkehr und automatische Ladestopps.

---

## APK bauen und installieren

Die APK wird über **GitHub Actions** gebaut. Android Studio ist nicht nötig.

1. Projekt in ein (privates) GitHub-Repository hochladen.
2. Die Datei `.github/workflows/build.yml` muss im Repository liegen.
3. Bei jedem Push baut GitHub die App. Die fertige `ELdoroado.apk` liegt danach unter **Releases → „ELdoroado – neuester Build“**.
4. APK auf dem Handy herunterladen und installieren (Installation aus dieser Quelle einmalig erlauben).

### Optional: eigener Release-Schlüssel

Damit alle Updates mit demselben Schlüssel signiert sind (z. B. für die Registrierung in der Android Developer Console), unter **Settings → Secrets and variables → Actions** anlegen:

| Secret | Inhalt |
|---|---|
| `KEYSTORE_BASE64` | Keystore-Datei, Base64-kodiert |
| `KEYSTORE_PASSWORD` | Passwort des Keystores (Alias `evroute`) |

Ohne diese Secrets wird mit dem Debug-Schlüssel signiert. Im Build-Protokoll steht, welcher Schlüssel verwendet wurde. In der App steht er unter **Einstellungen → Info**.

---

## Erste Einrichtung

1. **Einstellungen → TomTom**: API-Key eintragen (wird nur auf dem Handy gespeichert)
2. **Einstellungen → OBD2-Adapter**: Adapter suchen und auswählen (Car Scanner und ABRP vorher schließen)
3. **Einstellungen → Fahrzeug**: nutzbare Kapazität, Fahrweise, Referenzverbrauch prüfen
4. **Einstellungen → Ladeplanung**: Mindest-Akku, bevorzugte Anbieter und Ladekarten
5. Zuhause und Arbeit über die Favoriten in der Suche festlegen

---

## Datenquellen

| Quelle | Verwendung | Lizenz bzw. Bedingungen |
|---|---|---|
| [OpenStreetMap](https://www.openstreetmap.org/copyright) | Kartendaten, Orte, Suche | © OpenStreetMap-Mitwirkende, ODbL |
| [OpenFreeMap](https://openfreemap.org) | Kartenstile und Kacheln | frei nutzbar |
| [TomTom](https://developer.tomtom.com) | Routing, Verkehr, EV-Routing, Ladestationen, Belegung, Karte | eigener API-Key, TomTom-Nutzungsbedingungen |
| [Photon](https://photon.komoot.io) (Komoot) | Adresssuche | OSM-Daten |
| [Nominatim](https://nominatim.org) | Ortsdetails (Öffnungszeiten, Webseite) | OSM-Nutzungsrichtlinie |
| [Open-Meteo](https://open-meteo.com) | Wetter und Höhe | CC BY 4.0 |
| [OSRM](https://project-osrm.org) | Routing ohne TomTom-Key | Demo-Server |
| Overpass API | Rückfall für „In der Nähe“ | OSM-Daten |

OBD-Abfragen für die Stellantis-E-Plattform nach öffentlich dokumentierten Listen aus der OVMS- und GoingElectric-Community.

---

## Technik und Projektaufbau

- **Kotlin**, **Jetpack Compose**, **MapLibre Native**, OkHttp, kotlinx.serialization, Google Play Services Location, Android Car App Library

```
app/src/main/java/de/evroute/
├── App.kt            Start, Activity, ViewModel
├── Core.kt           Modelle, Geometrie, Einstellungen
├── Data.kt           Routing (TomTom/OSRM), Suche, Wetter, Verbrauchsmodell
├── Nav.kt            Navigation, Ansagen, Hintergrunddienst
├── MapScreen.kt      Karte, Routenlinie, Fahrzeugsymbol
├── Ui.kt             Hauptbildschirm, Einstellungen
├── Extras.kt / Extras2.kt   Routenfenster, Ladeliste, Spuren, Sicherung
├── Obd.kt / ObdUi.kt OBD2-Verbindung und Diagnose
├── Learn.kt          Fahrten aufzeichnen, Verbrauch lernen
├── Places.kt / Pois.kt / TilePois.kt   Ortsfenster, Orte auf der Karte
├── MapChargers.kt / Nearby.kt          Ladestationen, Umgebung
├── Robust.kt         Fehlerprotokoll, Offline-Karte
└── Car.kt            Android Auto
```

---

## Grenzen

- **Android Auto**: Der Code ist vorhanden, aber Google lässt Navigations-Apps mit der Car App Library nur aus dem Play Store zu. „Unbekannte Quellen“ reicht dafür nicht.
- **Play Protect** scannt selbst gebaute APKs bei der Installation. Das ist harmlos.
- **Ladepreise** sind nicht enthalten (keine freien Daten verfügbar).
- **Routing offline** ist nicht möglich, nur die Karte.
- OBD-Werte für Spannung, Strom und Temperaturen sind zum Teil geschätzt und kalibrierbar.

---

## Datenschutz

- Kein Konto, keine Werbung, keine Analyse-Dienste.
- Einstellungen, Favoriten, Fahrten und Gelerntes bleiben **auf dem Handy**.
- Anfragen gehen direkt an die oben genannten Dienste (z. B. Position und Ziel an TomTom für die Route).

---

## Hinweise

- Privates Hobbyprojekt, **nicht verbunden** mit TomTom, Stellantis, Citroën, Google oder ABRP. Alle Marken gehören ihren Inhabern.
- **Während der Fahrt nicht bedienen.** Die App ersetzt nicht die Aufmerksamkeit im Straßenverkehr.
- Akku- und Reichweitenprognosen sind Schätzungen. Für Fehlplanungen wird keine Haftung übernommen.

---
---

<a name="english"></a>
# ⚡ ELdoroado (English)

[Deutsch](#-eldoroado) · **English**

A private Android navigation app for electric vehicles, developed with the **Citroën ë-C4 (2022)** and usable for **Stellantis EVs** (Citroën, Peugeot, Opel, DS, Jeep, Fiat, Alfa Romeo, Lancia), Leapmotor and custom vehicle values: route planning with automatic charging stops, live traffic, OBD2 battery data and an Apple Maps–inspired interface.

> Inspired by A Better Routeplanner (ABRP), TomTom and Apple Maps, but self-built, with no ads, no account and no tracking.

## Features

### 🗺️ Map and navigation
- Map styles **Liberty**, **Positron** and **TomTom**, with **Fiord** or **Black** at night
- Up to **3 route options** (recommended, alternative, toll-free) with arrival time, charging time and battery at destination
- Blue route line **colored by traffic**, driven part greyed out
- Selectable vehicle icon: TomTom-style 3D arrow, car (with color choice) or dot
- **Predicted position**: the icon moves smoothly without lag and keeps going for up to 45 seconds in **tunnels** without GPS
- Turn banner with arrows, "then …" hint and **lane guidance** inside the banner
- German **voice guidance**, including lane advice
- **Speed limit** display, speed turns red when exceeded
- **End-of-jam, roadworks and closure warnings** with voice alerts
- Rerouting when off route, **faster route** suggestions while driving
- **Offline map** along the route (optionally automatic, Wi-Fi only)

### 🔋 Charging and battery
- **Long-distance planning with automatic charging stops** (TomTom Long Distance EV Routing) including the ë-C4 charging curve
- Weather (temperature, headwind, rain), elevation, heating and A/C are factored into consumption
- Charging stops with power, charging time, arrival and departure state of charge and **live availability**
- **"Choose another"**: alternatives around a charging stop, on map and list, with its own search
- **Charging station panel**: location (e.g. motorway services), connectors per type and power, opening hours, **toilets, food and shops nearby**
- Charging stations **on the map** and in **search** ("Tesla Kamen", "EnBW Aachen")
- Preferred and avoided **charging operators**, your own **charging cards**
- **Charging and parking at the destination**, change destination while driving

### 🚗 Fahrzeuge
- Fahrzeugauswahl: Stellantis e-CMP **1. Generation** (50/46 kWh, z. B. ë-C4, e-208, e-2008, Corsa-e, Mokka-e, DS 3) und **2. Generation** (54/51 kWh, z. B. ë-C4 ab 2023, Avenger, 600e, Junior, Ypsilon), Hochdachkombis, **Leapmotor** (ohne OBD) und **eigene Werte**
- Je Fahrzeug passende Kapazität, Ladeleistung, Ladekurve und Verbrauch

### 🔌 OBD2 (Stellantis e-CMP)
- Bluetooth LE adapter, tested with **Vgate iCar Pro 2S**
- Live: state of charge (SoC), SOH, energy in battery, cell voltages, temperatures, speed
- **Plan vs. actual**: automatic replanning when the battery deviates from the plan
- Diagnostics screen with raw data, console and log

### 🧠 Learning
- Trips are recorded automatically while OBD is connected
- **Consumption is learned per speed and temperature range** and used for planning
- The **charging curve** is learned during fast charging
- Trip list with kWh/100 km, export as a table

### 🔍 Search and places
- Search with **voice input**, favorites (home, work, custom), recent destinations
- **Place panel** like Google Maps: opening hours, "open now", phone, website
- **Points of interest on the map** by category, tappable, offline-capable
- Waypoints with breaks, reorderable

## Requirements

| What | Purpose | Required? |
|---|---|---|
| Android 8.0 or newer | App | ✅ |
| **TomTom API key** (free, [developer.tomtom.com](https://developer.tomtom.com)) | Traffic, charging planning, lanes, speed limits, chargers, TomTom map | recommended |
| Enabled TomTom products | Routing, Long Distance EV Routing, Search, EV Charging Availability, Traffic, Map Display | recommended |
| OBD2 adapter (Bluetooth LE) | Live battery data | optional |
| GitHub account | Automatic APK builds | ✅ |

Without a TomTom key the app falls back to free routing (OSRM) with a simple battery estimate, but without traffic and automatic charging stops.

## Building and installing

The APK is built by **GitHub Actions**, no Android Studio needed.

1. Upload the project to a (private) GitHub repository.
2. `.github/workflows/build.yml` must be present in the repository.
3. Every push triggers a build. The resulting `ELdoroado.apk` is published under **Releases → "ELdoroado – neuester Build"**.
4. Download and install the APK on your phone (allow installs from this source once).

**Optional release key:** add the repository secrets `KEYSTORE_BASE64` (Base64-encoded keystore) and `KEYSTORE_PASSWORD` (alias `evroute`). Without them the debug key is used. The signing fingerprint is shown in the build log and in the app under **Settings → Info**.

## First setup

1. **Settings → TomTom**: enter your API key (stored on the device only)
2. **Settings → OBD2 adapter**: scan and select your adapter (close Car Scanner and ABRP first)
3. **Settings → Vehicle**: check usable capacity, driving style, reference consumption
4. **Settings → Charging**: minimum battery, preferred operators and charging cards
5. Set home and work via the favorites in the search panel

## Data sources

OpenStreetMap (© OpenStreetMap contributors, ODbL), OpenFreeMap, TomTom (own API key, TomTom terms apply), Photon by Komoot, Nominatim, Open-Meteo (CC BY 4.0), OSRM demo server and the Overpass API. OBD requests for the Stellantis e-CMP platform are based on publicly documented lists from the OVMS and GoingElectric communities.

## Tech

Kotlin, Jetpack Compose, MapLibre Native, OkHttp, kotlinx.serialization, Google Play Services Location, Android Car App Library. See the project structure in the German section above.

## Limitations

- **Android Auto**: the code is included, but Google only allows Car App Library navigation apps installed from the Play Store. "Unknown sources" is not enough.
- **Play Protect** scans self-built APKs on installation. This is harmless.
- **Charging prices** are not available (no free data source).
- **Offline routing** is not possible, only the offline map.
- Some OBD values (voltage, current, temperatures) are estimated and can be calibrated.

## Privacy

No account, no ads, no analytics. Settings, favorites, trips and learned data stay **on the device**. Requests go directly to the services listed above (e.g. position and destination to TomTom for routing).

## Disclaimer

- Private hobby project, **not affiliated** with TomTom, Stellantis, Citroën, Google or ABRP. All trademarks belong to their respective owners.
- **Do not operate the app while driving.** It does not replace attention on the road.
- Battery and range predictions are estimates. No liability is accepted for planning errors.
