# Semester 2, Woche 4: Testplan

## Motivation

### Frontend

Da das Frontend der wesentliche Bestandteil für die Interaktion mit dem Benutzer ist (UI/UX), ist die problemlose Handhabung der Applikaiton von großer Bedeutung. Das Design und die Funktionsweise des Frontends kann entscheidend für Benutzer sein, welche Applikation sie für bestimmte Use-Cases benutzen möchten. Ein fehlerhaftes/verbuggtes Frontend kann somit Benutzer vom verwenden der Applikation abschrecken. Deswegen ist die fehlerfreie Handhabung des Frontends essentiell. 

### Backend



## Ziele der Tests

### Frontend

Die Tests im Frontend sollen sicherstellen, dass alle Funktionen der Applikation und dessen Bedienelemente fehlerfrei funktionieren. Zudem sollen die Website-Elemente richtig angezeigt werden. Zusätzlich sollte die Performance der Website sich in einem angemessenen Niveau befinden.

### Backend



## Arten der Tests

### Frontend

Durch die Verwendung des ```react.js``` Frameworks sind Tests für JavaScript/TypeScript notwendig. Glücklicherweise bietet das Framework anhand von Dokumentation und bereits integrierten Tools einfache Testmöglichkeiten an. Tests gibt es in zwei Kategorien:

- Rendern von Component Trees: Eine simple Testumgebung zum evaluieren des Outputs
- Starten einer kompletten App: Testen der App in einer realistischen Browser Umgebung (End-to-End Tests)

Die (vom Framework) empfohlenen Tools sind:

- Jest: Ein simples/einfaches JavaScript Testing Framework. Bietet vielseitige Konfigurationsmöglichkeiten und Testumgebungen (geeignet für alle Arten von Tests).
- React Testing Library: Vom Framework zur Verfügung gestellte Tools zum testen von ```react.js``` Komponenten. Sorgt für effizientes Refactoring und gibt Best Practice Vorschläge (geeignet für Unit-Tests & Integrationstests).

Durch solche Tests kann überprüft werden, ob...

- Komponenten der Website richtig angezeigt werden
- Werte, die der Benutzer eingibt, richtig eingelesen werden
- Komponenten die richtige Funktionalität besitzen und sie korrekt ausführen

Zusätzlich können API-Tests ausgeführt werden um zu überprüfen, ob die Kommunikation mit dem Backend/der Datenbank problemlos funktioniert.

Im Frontend gibt es keine automatisierten Tests, die ausgeführt werden können.

### Backend

github deployement/ci tests? https://docs.github.com/de/actions/automating-builds-and-tests/building-and-testing-nodejs

## Verwaltung/Vorgehensweise

### Frontend

Die Tests für das Frontend müssen seperat geschrieben und konfiguriert werden. Die Tests können einfach mit Version Control (``git``) zwischen den Entwicklern geteilt werden. Da die Umgebungen für die Tests in der Konfiguration definiert werden, muss für jeden Entwickler keine seperate Testumgebung aufgestellt werden.

Es wurden bis jetzt keine Tests für das Frontend geschrieben, da sich diese noch in der aktiven Entwicklung befindet. Es ist geplant, im Verlauf der Entwicklung Tests zu schreiben, um die Funktionsweise zu überprüfen. Kurz vor Ende der Entwicklung wird das Frontend vollständig mit den vorhin genannten Tools getestet.

### Backend