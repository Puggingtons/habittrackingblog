# Semester 2: Woche 8: Review

Hallo zusammen 👋
in dieser Woche konnten wir unsere CICD umsetzen und ein technisches Review durchführen.
Wir arbeiten auch weiterhin fleißig am Abschluss der Implementierung 🫡

## CICD

Der CICD Workflow auf Github ist jetzt, wie in der letzten Woche vorgestellt, umgesetzt.
Bei einem Mergerequest in den `main`-Branch wird zunächst eine Sonarcubeanalyse gestartet.

Beim Merge in den `main`-Branch wird dann der von uns definierte Workflow ausgeführt. Dabei werden zuerst die Tests im Frontend und im Backend ausgeführt. Wenn diese erfolgreich waren, wird der `build & deploy` Schritt durchgeführt, in dem das Dockerimage gebaut wird und auf den Server deployed wird.

## Review

#todo :)

Wir sind weiterhin dabei, die Anwendung weiter zu implementieren und können es kaum erwarten, euch nächste Woche das Ergebnis zu zeigen.

Euer Habittracking Team

---

<script src="https://utteranc.es/client.js" repo="Puggingtons/habittrackingblog" issue-term="pathname" theme="github-light" crossorigin="anonymous" async> </script>