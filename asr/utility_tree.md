# Utility Tree

(***L***ow, ***M***edium, ***H***igh)
| Quality attribute | Refinement                          | Quality attribute scenarios                                                                                                                        | Business value | Techical Risk |
| ----------------- | ----------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- | -------------- | ------------- |
| Security          | Passwortsicherheit                  | Wenn ein neuer Benutzer ein Passwort bei der Erstellung eines Accounts eingibt, wird dieses verschlüsselt gespeichert.                             | H              | L             |
|                   | Benutzerdatensicherheit             | Ein Benutzer kann nicht auf die Daten anderer Benutzer zugreifen.                                                                                  | H              | M             |
| Performance       | Transaktionsantwortzeit             | Wenn ein Benutzer ein Habit aktualisiert und das System unter höchster Last läuft, wird die Transaktion in unter 1 Sekunde erfolgreich bearbeitet. | H              | M             |
|                   | Datendurchsatz                      | Wenn das System unter höchster Last läuft, werden 100 normalisierte Transaktionen erfolgreich bearbeitet.                                          | H              | H             |
| Maintainablity    | Upgrade einer Drittparteikomponente | Wenn eine neue Majorversion des Datenbanksystems veröffentlicht wird, benötigt das Update auf diese maximal 2 Personenwochen.                      | H              | M             |