# Risikomanagement

Hallo Zusammen 😇

Das neue Semester hat begonnen und das Projekt kommt wieder so langsam ins Rollen.
In dieser Woche haben wir eine Risk Mitigation, Monitoring and Management (RMMM) Tabelle erstellt.
Diese ist [hier](../rmmm/rmmm) zu finden.

Im Folgenden wird das größte, von uns bisher festgehaltene, technische Risiko vorgestellt.

## Datenbank weg 😱😱😱

Das in der [RMMM](../rmmm/rmmm)-Tabelle festgehaltene Risiko mit der ID ``RISK040`` beschreibt das Risiko, die Daten in der Datenbank zu verlieren.

Um einen kompletten Datenverlust zu verhindern, werden regelmäßig Backups der Datenbank erstellt.
Dazu wird ein sql-Dump generiert und auf einem anderen Server gespeichert.

Im Falle eines Datenverlusts kann so der Stand des letzten Backups wieder in die Datenbank eingespielt werden.

## Fortschritt in der Implementierung

Nach der Halbzeitpräsentation ist noch nicht Fortschritt zu verzeichnen.

Kai und Kayra arbeiten weiter am Frontend. Als nächstes werden hier die Habitkomponente und die Eingabemaske eines neuen Habit implementiert.

Im Backend arbeite ich weiterhin an der Implementierung der Api-Endpunkte.

---

Wir wünschen euch allen viel Erfolg bei euren Projekten im neuen Semester 🤗

---

<script src="https://utteranc.es/client.js" repo="Puggingtons/habittrackingblog" issue-term="pathname" theme="github-light" crossorigin="anonymous" async> </script>