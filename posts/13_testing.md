# Semester 2, Woche 5: Testing Testing Testing

Hallo zusammen,
in dieser Woche konnten wir die Implementierung unserer Tests fortsetzen. Kayra implementiert die Tests für das Frontend und Paul für das Backend. Benutzt wird dafür jeweils Jest.

Am Testplan gibt es bisher keine Änderungen.

## Testing im Frontend
Nachdem es im Frontendtestingsetup einige Probleme mit Jest und Typescript gab, konnte Kayra erfolgreich die Testingumgebung für das Frontend einrichten. Tests folgen in den kommenden Wochen.

## Testing im Backend
Beim Testen im Backend sind ein paar Probleme mit dem Testing Framework und dem Modulsystem von Nest.js entstanden.
Um die Datenbankanbindung, die wir mit Prisma implementiert haben, zu mocken, sind wir [diesem Vorschlag](https://stackoverflow.com/a/73697154) gefolgt. Ebenso mussten wir in der `tsconfig.json` den `strictNullCheck` aktivieren, um eine Fehlermeldung von zyklischen Abhängigkeiten zu beheben. (siehe [hier](https://www.prisma.io/docs/orm/prisma-client/testing/unit-testing#mocking-the-prisma-client))
Mit dieser Lösung ist es jetzt jedoch möglich, den `PrismaService` zu mocken und so die anderen Services unabhängig von diesem zu testen.
Den `UserService` haben wir jetzt komplett getestet. Die anderen folgen in den kommenden Wochen :)

## Fortschritt im Projekt

Kai arbeitet fleißig am Frontend weiter und implementiert Komponenten.
Zum einen die `HabitOverview`, in der die Habits eines Users dargestellt werden. Zum anderen eine Eingabemaske, in der der User ein neues Habit erstellen kann.

Grüßle und schon mal ein schönes Pfingstfest
euer Habittrackingteam <3

---

<script src="https://utteranc.es/client.js" repo="Puggingtons/habittrackingblog" issue-term="pathname" theme="github-light" crossorigin="anonymous" async> </script>