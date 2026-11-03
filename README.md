<p align="center">
  <img src="docs/logo.png" alt="ELdoroado" width="128">
</p>

<h1 align="center">ELdoroado</h1>

<p align="center">
  <b>Navigation und Ladeplanung für Elektroautos – offline, ohne Konto, ohne Werbung.</b><br>
  <i>electric do road</i>
</p>

---

ELdoroado ist eine Navi-App für Android, die speziell für Elektroautos gemacht ist. Sie berechnet Routen direkt auf dem Handy, plant Ladestopps passend zu deinem Fahrzeug und deinem Akku und sagt dich zuverlässig ans Ziel – auch dann, wenn gerade kein Netz da ist.

Die App ist ein Hobbyprojekt und Open Source. Sie kommt ohne Benutzerkonto, ohne Werbung und ohne Tracker aus. Was du fährst, bleibt auf deinem Handy.

> **Status:** Beta. ELdoroado wird im Alltag gefahren und laufend verbessert, ist aber bisher nur mit wenigen Fahrzeugen und Handys erprobt. Rückmeldungen sind ausdrücklich willkommen.

---

## Was ELdoroado kann

### Routen, offline auf dem Handy
- **Offline-Routing** mit der Routing-Engine Valhalla. Die Kartendaten werden einmal heruntergeladen (nur im WLAN), danach braucht die Routenberechnung kein Internet mehr.
- **Bis zu drei Routen** zur Auswahl, nebeneinander zum Durchwischen, sortiert nach der tatsächlichen Gesamtzeit inklusive Stau und Laden.
- **Realistische Fahrzeiten** dank Durchschnittsgeschwindigkeiten je Straßenart und Land.
- **Höchstgeschwindigkeit wählbar** – wer bewusst 110 oder 120 fährt, bekommt passende Zeiten und Verbrauchswerte.

### Ladeplanung, die erklärt, was sie tut
- **Eigene Ladeplanung auf dem Handy:** Die App vergleicht alle passenden Schnelllader entlang der Strecke und wählt die schnellste Kombination aus Fahren, Umwegen und Laden – der Akku fällt dabei nie unter deine Reserve.
- **Ladezeiten nach der echten Ladekurve** deines Fahrzeugs, die sich mit jedem Ladevorgang verfeinert.
- **Verbrauch mit Wetter, Wind und Höhenmetern:** Gegenwind wird für jeden Abschnitt zur tatsächlichen Fahrtrichtung gerechnet, Steigungen kosten Energie, bergab gibt es einen Teil per Rekuperation zurück.
- **Nachvollziehbar:** Zu jedem Ladestopp steht, warum er gewählt wurde – Ladeleistung, Umweg, Ladeziel und mit wie viel Akku du am nächsten Halt ankommst.
- **Unterwegs nachjustiert:** Mit OBD2-Adapter vergleicht die App deinen echten Akkustand mit der Planung und plant rechtzeitig einen früheren Ladestopp, wenn der Verbrauch höher ist als gedacht.

### Ladesäulen
- **Alle öffentlichen Ladepunkte in Deutschland offline** aus dem Ladesäulenregister der Bundesnetzagentur, wöchentlich aktualisiert – mit Leistung, Steckern, Öffnungszeiten und Bezahlmöglichkeiten.
- **Suche nach Anbieter und Ort**, zum Beispiel „EnBW Hagen“, auf der Karte, entlang der Route und am Ziel.

### Fahrzeuge
- **Rund 1.300 Elektroauto-Varianten** zur Auswahl: Hersteller, Modell, Akku-Variante – mit Akkugröße, Ladeleistung und Ladekurve.
- **Geprüfte Profile mit OBD2-Unterstützung** für Stellantis-Fahrzeuge (z. B. Citroën ë-C4, Peugeot e-208, Opel Corsa-e), getestet mit einem Vgate iCar Pro 2S (Bluetooth LE).
- **Ohne Adapter** stellst du den Akkustand vor der Fahrt einfach von Hand ein.

### Ansagen und Fahransicht
- **Ansagen nach Zeit statt nach festen Entfernungen**, mit Spurempfehlungen, Kreisverkehr samt Ausfahrtzählung und klaren Hinweisen an Autobahnkreuzen („rechts halten und auf die A 45 wechseln“).
- **Warnung vor Baustellen, Staus und Sperrungen** mit Vorankündigung.
- **Große, ruhige Fahransicht** mit Abbiegepfeil auf der Karte, Tempolimit, Ankunftszeit und Akku am Ziel.
- **Bild-im-Bild:** Beim Wechsel in eine andere App läuft die Navigation in einem kleinen Fenster weiter.
- **Querformat** mit Seitenleiste für die Halterung im Auto.
- **Nachtmodus** mit dezentem Lichtkegel vor dem Fahrzeugsymbol.
- Funktioniert mit jeder Sprachausgabe von Android, auch mit freien Stimmen wie Piper über SherpaTTS.

### Verkehr
- **Autobahnen:** Staus mit Verzögerung, Baustellen und Sperrungen von der Autobahn GmbH des Bundes – frei und ohne Anmeldung. Sperrungen werden automatisch umfahren, bei großen Staus schlägt die App eine schnellere Umfahrung vor.
- **Optional mit eigenem TomTom-Schlüssel:** Störungsmeldungen auch in der Stadt und im Ausland sowie die Verkehrslage auf der Karte.

### Für dich gemacht
- **Startbildschirm** mit Begrüßung, Wetter, Akku, Reichweite und einem Fahrvorschlag passend zu Ort und Uhrzeit („Zur Arbeit?“).
- **Lernt aus deinen Fahrten** – Verbrauch und Ladekurve werden mit der Zeit immer genauer.
- **Eco-Score** mit fünf nachvollziehbaren Teilwerten: Verbrauch, Gleichmäßigkeit, Tempo, Kurven und Vorausschau.
- **Ersteinrichtung** in sechs kurzen Schritten.

---

## Datenschutz

- **Kein Konto, keine Werbung, keine Tracker, keine Analyse-Dienste.**
- **Keine Google-Dienste nötig:** Der Standort kommt von Androids eigenem Standortdienst.
- Fahrten, gelernte Werte, Favoriten und Einstellungen bleiben **auf dem Handy**.
- Online-Abfragen gehen nur an die unten genannten Dienste, und nur so viel wie nötig. Routenberechnung, Ladeplanung und Ladesäulensuche in Deutschland laufen ohne Internet.

---

## Voraussetzungen

- Android 8.0 oder neuer, 64-Bit-Handy (praktisch alle aktuellen Geräte)
- Für das Offline-Routing etwa 6 GB freier Speicher
- Optional: OBD2-Adapter mit Bluetooth LE

---

## Bekannte Grenzen

- **Offline-Kartendaten** gibt es derzeit für Deutschland; weitere Länder sind in Vorbereitung.
- **Staus in der Stadt** gibt es nur mit eigenem TomTom-Schlüssel.
- **Keine Live-Belegung** von Ladesäulen.
- **Kein Android Auto.**
- Die Karte selbst wird online geladen; entlang einer geplanten Route kann sie für unterwegs gespeichert werden.

---

## Datenquellen und Software

ELdoroado steht auf den Schultern vieler offener Projekte. Herzlichen Dank an alle, die sie möglich machen.

### Karten- und Geodaten

| Was | Quelle | Lizenz |
|---|---|---|
| Straßen, Orte, Tempolimits, Spuren | © [OpenStreetMap](https://www.openstreetmap.org/copyright)-Mitwirkende | ODbL 1.0 |
| Kartendarstellung | [OpenFreeMap](https://openfreemap.org) (Stile Bright, Positron, Dark, Fiord) | Daten: ODbL · Stile: siehe Projekt |
| Durchschnittsgeschwindigkeiten | [OpenStreetMapSpeeds](https://github.com/OpenStreetMapSpeeds/schema) | siehe Projekt |
| Höhenmodell | SRTM (NASA/USGS) über die [AWS Terrain Tiles](https://registry.opendata.aws/terrain-tiles/) | gemeinfrei |
| Ortssuche | [Photon](https://photon.komoot.io) von Komoot, auf Basis von OpenStreetMap | ODbL (Daten) |
| Tempolimits (Rückfall) | [Overpass API](https://overpass-api.de), OpenStreetMap | ODbL |

### Laden, Fahrzeuge, Wetter, Verkehr

| Was | Quelle | Lizenz |
|---|---|---|
| Ladesäulen Deutschland | [Ladesäulenregister der Bundesnetzagentur](https://www.bundesnetzagentur.de/ladesaeulenkarte), aufbereitet von [ratopi/ladesaeule](https://github.com/ratopi/ladesaeule) | CC BY 4.0 |
| Ladesäulen Ausland (optional) | [Open Charge Map](https://openchargemap.org) | überwiegend CC BY 4.0 |
| Fahrzeugdaten | [Open EV Data](https://github.com/KilowattApp/open-ev-data) | MIT |
| Wetter, Wind, Höhen (Rückfall) | [Open-Meteo](https://open-meteo.com) | CC BY 4.0 |
| Verkehr auf Autobahnen | [Autobahn GmbH des Bundes](https://verkehr.autobahn.de) | Daten der Autobahn GmbH |
| Verkehr Stadt/Ausland (optional) | [TomTom Traffic API](https://developer.tomtom.com) mit eigenem Schlüssel | proprietär, nach TomTom-Bedingungen |

### Software

| Was | Projekt | Lizenz |
|---|---|---|
| Routing-Engine | [Valhalla](https://github.com/valhalla/valhalla) | MIT |
| Valhalla für Android | [valhalla-mobile](https://github.com/Rallista/valhalla-mobile) | MIT |
| Kartendarstellung | [MapLibre Native](https://github.com/maplibre/maplibre-native) | BSD-2-Clause |
| Oberfläche | Jetpack Compose, Kotlin | Apache 2.0 |
| Netzwerk, JSON | OkHttp, kotlinx.serialization, Moshi | Apache 2.0 |
| Schrift | [Noto Sans](https://fonts.google.com/noto) | SIL OFL 1.1 |
| 3D-Fahrsymbole | [Kenney „Car Kit“](https://kenney.nl), [Quaternius „Spaceship Pack“](https://quaternius.com) | CC0 |

Die Kartendaten für das Offline-Routing werden aus OpenStreetMap mit Valhalla aufbereitet und über einen eigenen Server bereitgestellt. Dabei gelten die Lizenzbedingungen von OpenStreetMap (ODbL).

---

## Sicherheit

ELdoroado ist eine Navigationshilfe. Maßgeblich sind immer die Verkehrsregeln, die Beschilderung und die Situation vor Ort. Bediene das Handy nicht während der Fahrt. Reichweiten- und Ladeplanung sind Schätzungen – plane gerade bei Kälte, auf unbekannten Strecken und bei knappem Akku ausreichend Reserve ein. Die Nutzung erfolgt auf eigene Verantwortung und ohne Gewähr.

---

## Mitmachen

Besonders hilfreich sind Erfahrungen mit **anderen Fahrzeugen, OBD2-Adaptern und Handys** sowie Hinweise zu Ansagen an konkreten Kreuzungen. Fehler und Ideen gern als [Issue](../../issues) – am besten mit Screenshot, Ort und der genauen Ansage.

---

## Lizenz

Copyright © 2026 die ELdoroado-Mitwirkenden

ELdoroado ist freie Software: Du darfst sie unter den Bedingungen der **GNU General Public License Version 3** (GPL-3.0) weitergeben und verändern, wie sie in der Datei [LICENSE](LICENSE) steht. Veränderte Fassungen, die weitergegeben werden, müssen ebenfalls unter der GPL-3.0 und mit Quellcode erscheinen.

ELdoroado wird in der Hoffnung bereitgestellt, dass es nützlich ist, aber **ohne jede Gewährleistung** – auch ohne die stillschweigende Gewährleistung der Marktreife oder der Eignung für einen bestimmten Zweck. Einzelheiten stehen in der GPL-3.0.

Für die verwendeten Daten und Bibliotheken gelten die oben genannten Lizenzen ihrer jeweiligen Urheber. Die eingebundenen Bibliotheken stehen unter MIT, BSD oder Apache 2.0 und sind mit der GPL-3.0 vereinbar; Schrift (OFL) und 3D-Modelle (CC0) dürfen mitgeliefert werden, die Fahrzeugdaten liegen als MIT-lizenzierter Grundstock bei, alle übrigen Daten werden zur Laufzeit geladen.

ELdoroado ist ein unabhängiges Projekt und steht in keiner Verbindung zu Fahrzeugherstellern, Ladesäulenbetreibern oder den genannten Diensten.
