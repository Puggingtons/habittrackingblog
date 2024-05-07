# Semester 2, Woche 4: Testplan

## Motivation

### Frontend

Da das Frontend der wesentliche Bestandteil für die Interaktion mit dem Benutzer ist (UI/UX), ist die problemlose Handhabung der Applikaiton von großer Bedeutung. Das Design und die Funktionsweise des Frontends kann entscheidend für Benutzer sein, welche Applikation sie für bestimmte Use-Cases benutzen möchten. Ein fehlerhaftes/verbuggtes Frontend kann somit Benutzer vom verwenden der Applikation abschrecken. Deswegen ist die fehlerfreie Handhabung des Frontends essentiell. 

### Backend

Das Backend ist für die korrekte Persistierung und Auslieferung der Daten der Anwendung zuständig.
Um diese Funktionalitäten zu gewährleisten und auf Korrektheit zu prüfen, sind Tests sinnvoll.
Durch diese Tests kann auch vermieden werden, durch Änderungen an der Datenbank die API-Definition ungewollt zu verändern.

## Ziele der Tests

### Frontend

Die Tests im Frontend sollen sicherstellen, dass alle Funktionen der Applikation und dessen Bedienelemente fehlerfrei funktionieren. Zudem sollen die Website-Elemente richtig angezeigt werden. Zusätzlich sollte die Performance der Website sich in einem angemessenen Niveau befinden.

### Backend

Die Tests im Backend sollen sicherstellen, dass die einzelnen Komponenten, wie Controller, Services oder Guards, individuell korrekt funktionieren.
Weiterhin soll durch die Tests sichergestellt werden, dass diese auch miteinander ein korrektes Verhalten aufweisen.

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

Die Dokumentation des von uns im Backend verwendeten Frameworks `nest.js` hat beinhaltet das Vorgehen des Testens einer `nest.js` Anwendung. Diese Dokumentation ist [hier](https://docs.nestjs.com/fundamentals/testing) zu finden.
`nest.js` ist mit `jest` sehr gut testbar, da das Framework dies von sich aus unterstützt.

Die oben genannten Komponenten können so mit Unit-Tests getestet werden.
Um die Abhängigkeiten zu anderen Komponenten aus dem getesteten Code zu isolieren, liefert `nest.js` die `@nestjs/testing` package. Diese ermöglicht es, Module zu mocken.

<!-- github deployement/ci tests? https://docs.github.com/de/actions/automating-builds-and-tests/building-and-testing-nodejs -->

## Verwaltung/Vorgehensweise

### Frontend

Die Tests für das Frontend müssen seperat geschrieben und konfiguriert werden. Die Tests können einfach mit Version Control (``git``) zwischen den Entwicklern geteilt werden. Da die Umgebungen für die Tests in der Konfiguration definiert werden, muss für jeden Entwickler keine seperate Testumgebung aufgestellt werden.

Es wurden bis jetzt keine Tests für das Frontend geschrieben, da sich diese noch in der aktiven Entwicklung befindet. Es ist geplant, im Verlauf der Entwicklung Tests zu schreiben, um die Funktionsweise zu überprüfen. Kurz vor Ende der Entwicklung wird das Frontend vollständig mit den vorhin genannten Tools getestet.

### Backend

Die Tests werdern unabhängig vom Frontend implementiert. Jede Komponente erhält eine eigene Test-Datei. Diese Test-Datei beginnt wie die Quelldatei der Komponente und hat die Endung `.spec.ts` (z.B. `habits.controller.spec.ts`).

---

<script src="https://utteranc.es/client.js" repo="Puggingtons/habittrackingblog" issue-term="pathname" theme="github-light" crossorigin="anonymous" async> </script>