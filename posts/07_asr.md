# Architecture Significant Requirements (ASR)

## ASR
Das Dokument mit den ASR ist hier zu finden:

[ASR](../asr/asr)

Zusammenfassend sind wir zu folgenden Architekturentscheidungen gekommen:

> **Security**  
> Um die Security zu erhöhen,
> - werden Passwörter verschlüsselt gespeichert.
> - werden Eingabewerte an Endpunkte auf Korrektheit überprüft.
> - sind Endpunkte für Benutzerdaten nur für authentifizierten und authorisierten Benutzern erreichbar.

> **Performance**  
> Um die Performance zu erhöhen, werden Anfragen parallel verarbeitet.

> **Modifiability**  
> Um die Modifiablility im Frontend zu verbessern, benutzen wir die Einteilung der Elemente basierend auf dem 'Atomic Design'.

> **Usability**  
> Um die Usability zu erhöhen,
> - wird ein Benachrichtigungssystem benutzt, um den Benutzer zu informieren.
> - haben alle Bedienelemente einen Hovertext mit einer kurzen Beschreibung.
> - gibt es eine Hilfeseite.

## Utility-Tree

Das Dokument des Utility-Trees ist hier zu finden:

[Utility-Tree](../asr/utility_tree)

---

<script src="https://utteranc.es/client.js" repo="Puggingtons/habittrackingblog" issue-term="pathname" theme="github-light" crossorigin="anonymous" async> </script> 