# Architecture Significant Requirements

## 3 Schritt Ansatz

### 1. Schritt: Klärung der Anforderungen an das Qualitätsmerkmal

#### 6-Part Form

| Q-Attribute   | Quelle          | Stimulus                               | Artefakt | Umgebung           | Reaktion                                            | Messung                               |
| ------------- | --------------- | -------------------------------------- | -------- | ------------------ | --------------------------------------------------- | ------------------------------------- |
| Security      | externer Akteur | möchte Datenbank einsehen              | System   | Produktivsystem    | Anfragedaten werden geloggt und Betreiber alarmiert | innerhalb von 5 Sekunden alarmiert    |
| Security      | Benutzer        | möchte Daten anderer Benutzer einsehen | System   | Produktivsystem    | Anfragedaten werden geloggt und Betreiber alarmiert | innerhalb von 5 Sekunden alarmiert    |
| Performance   | Benutzer        | initiiert Änderung                     | System   | Produktivsystem    | Änderung wird verarbeitet                           | Latenz von durchschnittlich 1 Sekunde |
| Modifiability | Entwickler      | möchte Änderung am UI Design vornehmen | Design   | Entwicklungssystem | Änderungen vorgenommen und getestet                 | in 3 Stunden                          |
| Usability     | Benutzer        | lädt zum ersten Mal die Webanwendung   | System   | Produktivsystem    | Benutzer benutzt Anwendung                          | nach 2-minütiger Experimentation      |

### 2. Schritt: Diskutieren Sie, welche potenziellen Taktiken für Ihr Projekt geeignet sind

#### Security
- Vertraulichkeit
  - Benutzer können nicht auf Daten anderer zugreifen
  - Nur authentifizierte und authorisierte Benutzer können auf Daten zugreifen
  - Passwörter werden nicht im Klartext gespeichert
- Integrität
  - nur authentifizierte und authorisierte Benutzer können ihre Daten bearbeiten
  - Daten können nur durch die Webanwendung bearbeitet werden
- Verfügbarkeit
  - Die Anwendung zu 99% der Zeit erreichbar

##### Tactics
- Detect Attacks
  - Verify Message Integrity
    - Nur Anfragen mit den definierten Eingabewerten werden verarbeitet
- Resist Attacks
  - Authenticate Actors
    - nur authentifizierte Benutzer können Daten bearbeiten
  - Authorize Actors
    - nur authorisierte Benutzer können Daten bearbeiten
  - Limit Exposure
    - Ein Benutzer wird automatisch nach 24 Stunden Inaktivität ausgeloggt
  - Encrypt Data
    - Passwörter von Benutzern werden verschlüsselt in der Datenbank gespeichert
- Recover from Attacks
  - Restore
    - Ein Datenbankbackup wird eingespielt

#### Performance
- Latenzzeit
  - soll bei maximal 2 Sekunden liegen
- Fristen bei der Verarbeitung
  - keine
- Durchsatz des Systems
  - es sollen immer mindestens 100 Transaktionen verarbeitet werden können
- Jitter der Antwort
  - es ist zulässig, dass die Antwort im akzeptierten Latenzzeitbereich jittert.
- Anzahl der nicht verarbeiteten Ereignisse
  - soll 0 betragen

##### Tactics
- Control Resource Demand
  - Reduce overhead
    - Minimierung der Anfragen pro Seitenzugriff
- Manage Resources
  - Increase resources
    - Bei hoher Belastung des Systems werden die Ressources temporär erhöht
  - Introduce concurrency
    - Anfragen werden parallel verarbeitet

#### Modifiability
Was kann sich ändern?
- Design eines Buttons (oder anderen Elements)
- Farbschema
- Schriftart

Wie hoch ist die Wahrscheinlichkeit der Veränderung?
- sehr hoch, da das Design noch nicht entgültig feststeht und sich im Laufe der Entwicklung weiter entwickelt

Wann wird die Änderung vorgenommen und wer macht sie?
- Ein UI-Entwickler während der Entwicklungsphase (sowie nach dem Produktivgang)

Wie hoch sind die Kosten der Änderung?
- eher gering

##### Tactics
- Refactor
  - Elemente mit ähnlichen Eigenschaften (Buttons, Icons, ...) in eigene Klassen zusammenfassen
- Abstract Common Services
  - Farbschema durch Bibliothek anwenden


#### Usability
- Systemfunktionen lernen
  - die Bedienung der Anwendung soll intuitiv sein
  - alle Bedienelemente sollen erklärt sein
- Ein System effizient nutzen
  - Die Navigation soll einfach und mit wenigen Klicks erfolgen
- Minimierung der Auswirkungen von Fehlern
  - Eingaben werden direkt im Frontend geprüft
  - Falsche Daten werden im Backend abgefangen und im Frontend mit einer Fehlermeldung berichtet
- Das System an die Bedürfnisse des Benutzer anpassen
  - Der Benutzer soll zwischen Light- und Dark-Modus wechseln können
- Steigerung von Vertrauen und Zufriedenheit
  - Positive Mitteilungen bei erfolgreichen Bearbeitungen der Daten

##### Tactics
- Support User Initiative
  - Cancel
    - jede Bearbeitung kann abgebrochen werden, um zum ursprünglichen Zustand zurückzukehren

### 3. Schritt: Entscheiden und dokumentieren Sie Architekturentscheidungen und Entwurfsmuster

#### Security
Um die Security zu erhöhen,
- werden Passwörter verschlüsselt gespeichert.
- werden Eingabewerte an Endpunkte auf Korrektheit überprüft.
- sind Endpunkte für Benutzerdaten nur für authentifizierten und authorisierten Benutzern erreichbar.

#### Performance
Um die Performance zu erhöhen, werden Anfragen parallel verarbeitet.

#### Modifiability
Um die Modifiablility im Frontend zu verbessern, benutzen wir die Einteilung der Elemente basierend auf dem 'Atomic Design'.

#### Usability
Um die Usability zu erhöhen,
- wird ein Benachrichtigungssystem benutzt, um den Benutzer zu informieren.
- haben alle Bedienelemente einen Hovertext mit einer kurzen Beschreibung.
- gibt es eine Hilfeseite.