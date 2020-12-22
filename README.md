# ThingSpeak
## 1. Beschreibung
ThingSpeak ist eine Open-Source Analyse-Plattform des Internet-of-Things-Anwendung (IoT). Mit einer API kann man live Datenströme in der Cloud visualisieren und analysieren. Die Daten von den jeweiligen Geräten können an ThingSpeak gesendet werden und es werden sofortige Visualisierungen und Analysen durchgeführt. Mit ThingSpeak können Ingenieure und Wissenschaftler IoT-Systeme prototypisieren und erstellen, ohne Server einrichten oder Web-Software entwickeln zu müssen.

## 2. Installation
1. ThinkSpeak Account erstellen
2. ThinkSpeak Projekt erstellen
3. ThinkSpeak Source Festlegen
4. git klonen
5. main.cpp anpassen (url, API-Key)
6. kompilieren
7. Deploy kompiliertes File auf das IOT-kit-v3
8. IOT-Kit-v3 neu starten
9. Installation fertig
10. ThingSpeak Daten auslesen

## 3. Dokumentation
### 3.1 Daten übermitteln
Die Daten werden über HTTPS an ThingSpeak übermittelt. Dadurch ist die Datenintegrität und Sicherheit gegeben. Die Daten werden via URL verschickt. 

Die URL ist durch SSL verschlüsselt. Somit kann niemand ausser, ThinkSpeak die Daten lesen, da diese als SSL-Trust hinterlegt wurden.

```
https://api.thingspeak.com/update?[API-KEy]field1=[data],field2=[data]
```

### 3.2 Grafische Darstellung
ThingSpeak verwendet für die grafische Darstellung zwei Werte. Einerseits sind es die gesendeten Daten und um dies in einem Lieniendiagramm darzustellen, nimmt es noch die Zeit, wann die Daten angekommen sind.

### 3.3 Verarbeitung der Daten
Mathlap ist die Firma, welche ThingSpeak anbietet. Mit diesem Tool könnte man die Daten noch weiter verarbeiten. Zum Beispiel könnte man den Mittelwert ausrechnen etc.

### 3.4 Alerts
Thingspeak kann als Alert zum Beispiel Twitter benutzen, oder ein Mail verschicken. Um Twitter aber zu benutzen, müsste man einen Twitter API-Key benutzen. Wir hatten aber alle keinen Twitter Account, deshalb haben wir uns auf unser Haubtproekt fokusiert, also unser Cloud-Dienst.

## 4. Testprotokoll
### 4.1 Kompillieren 
| Testfall: 001     | Kompillieren                                                                                                         |
| ----------------- | -------------------------------------------------------------------------------------------------------------------- |
| Ziel:             | Das kompillierte File kann auf Thingspeak hochgeladen werden. Auf der seriellen Verbindung kommt es zu keinem Error. |
| Beschreibung:     | Die Source von ./source kompillieren und auf das IOTkitV3 aufspielen. Danach das Board neu starten.                  |
| Soll-Wert:        | Es kommen keine Errors auf der seriellen Verbinung                                                                   |
| Ist-Wert:         | keine Errors                                                                                                         |
| Analyse:          | funktioniert richtig.                                                                                                |
| Weitere Schritte: | -                                                                                                                    |

### 4.2 Display Anzeige
| Testfall: 002     | Display Anzeige                                                        |
| ----------------- | ---------------------------------------------------------------------- |
| Ziel:             | Auf dem Display wird die Temperatur und Luftfäuchtigkeit angezeigt.    |
| Beschreibung:     | Board an strom anschliessen und anschliessend in einen Sensor "huchen" |
| Soll-Wert:        | Die Luftfäuchtigkeit steigt                                            |
| Ist-Wert:         | Daten werden auf dem Display angezeigt                                 |
| Analyse:          | Alles Richtig                                                          |
| Weitere Schritte: | -                                                                      |

### 4.3 Kommunikation ThingSpeak
| Testfall: 003     | Kommunikation ThingSpeak                                                                       |
| ----------------- | ---------------------------------------------------------------------------------------------- |
| Ziel:             | Die Kommunikation erfolg verschlüsselt und die Daten werden grafisch auf ThingSpeak angezeigt. |
| Beschreibung:     | Serielle Verbindung öffnen und schauen, ob die Daten über https verschickt werden.             |
| Soll-Wert:        | Auf der seriellen Verbindung wird https ausgegeben.                                            |
| Ist-Wert:         | https://update.thinkspeak.com                                                                  |
| Analyse:          | Daten werden verschlüsselt übermittelt                                                         |
| Weitere Schritte: | -                                                                                              |