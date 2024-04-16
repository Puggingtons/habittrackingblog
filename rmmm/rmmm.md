
# Risk Mitigation, Monitoring and Management

Categories:
- **U**: user
- **R**: requirement
- **Comp**: project complexity
- **P&C**: planning and control
- **T**: team
- **Org**: organizational environment
- **Tech**: technical

| Risk ID | Category | Risk Description                                      | Probability | Impact    | Risk Score | Mitigation Strategy                                                       | Indicator                                                                                                               | Contingency Plan                         | Responsible                              | Status | Last modified date |
| ------- | -------- | ----------------------------------------------------- | ----------- | --------- | ---------- | ------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------- | ---------------------------------------- | ---------------------------------------- | ------ | ------------------ |
| RISK010 | P&C      | unerfahrene Teamleitung                               | hoch        | hoch      | 6          | Teamleiterweiterbildung und Managementunterstützung                       | nicht eingehaltene Deadlines, ungleiche Aufgabenverteilung                                                              | Teamleitung durch Erfahrenen ersetzen    | Management                               | offen  | 2024.04.16         |
| RISK020 | Comp     | Zu viele Anforderungen in zu wenig Zeit               | mittel      | hoch      | 5          | Anforderungen anpassen und/oder Zeitraum verlängern                       | voraussichtliche Nichtfertigstellung bis zur Deadline                                                                   | Anforderungen reduzieren                 | Product Owner / Management / Teamleitung | offen  | 2024.04.16         |
| RISK030 | T        | Ausfall von Teammitgliedern                           | hoch        | mittel    | 5          | Pufferzeit allokieren, in der Teamkollegen die Aufgaben übernehmen können | Anzahl der Teammitglieder ist weniger als sonst                                                                         | Aufgaben streichen / Deadline verlängern | Teamleitung / Management                 | offen  | 2024.04.16         |
| RISK040 | Tech     | Verlust der Daten in der Datenbank                    | niedrig     | sehr hoch | 7          | regelmäßige Backups der Datenbank                                         | Datenbank liefert keine/fehlerhafte Daten                                                                               | Datenbankbackup einspielen               | Team                                     | offen  | 2024.04.16         |
| RISK050 | Tech     | eine Drittpartei erhält Zugang zu Daten eines Nutzers | niedrig     | sehr hoch | 6          | regelmäßige Erneuerung der Auth Daten (login token)                       | einzelne Benutzer beschweren sich über fehlerhafte Daten / Zugriff auf Benutzerdaten von einem neuen, unbekannten Gerät | Benutzer auf allen Geräten abmelden      | Team                                     | offen  | 2024.04.16         |
