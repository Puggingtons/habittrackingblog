# Semester 2: Woche 7: CICD

Hallo zusammen 🍁

Diese Woche konnten wir aufgrund der Klausur leider keinen Fortschritt am Projekt berichten. Wir geloben Besserung 🙏

## CICD

Die Versionskontrollplattform unseres Projetkes ist GitHub. Die CI/CD Pipeline werden wir also auch über GitHub implementieren. Die genaue Implementation wird in der nächsten Woche stattfinden. Einige Eckpunkte möchten wir euch jedoch jetzt auch schon mitteilen.
Ziel der CI/CD Pipeline ist es, ein Dockerimage zu bauen und diesen auf einen möglicherweise auf einen Server zu deployen.
Dazu wird von der GitHub CI/CD zunächst dieser Container gebaut. Dafür haben wir bereits ein Dockerfile, welches dann dafür benutzt wird.
Für die Testausführung haben wir noch keinen konkreten Plan. Dieser folgt dann ebenfalls in der nächsten Woche.
Der Deploy wird ein Upload auf einen Server und das Starten der Anwendung auf dem Server mit einer speziellen `compose.yaml`, die dann ein eigenes Serverumfeld beschreibt. Aktuell haben wir nur eins für die Entwicklungsumgebung.

Wir freuen uns, euch nächste Woche die Ergebnisse mitzuteiilen und sind auf eure Lösungen gespannt.

Euer Habittracking Team

---

<script src="https://utteranc.es/client.js" repo="Puggingtons/habittrackingblog" issue-term="pathname" theme="github-light" crossorigin="anonymous" async> </script>