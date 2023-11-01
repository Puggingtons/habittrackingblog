# Use-Case-Realization Specification

# Habitübersicht

## 1 Introduciton

### 1.1 Purpose

Dieses Dokument beschreibt den Ablauf der Sequenz zum Anzeigen der Habitübersicht und die benötigten Ressourcen.

### 1.2 Scope

Die Sequenz muss folgende Eigenschaften/Funktionen erfüllen:

- Der Benutzer muss die Habitübersicht öffnen können
- Es sollten alle (aktiven) Habits übersichtlich aufgelistet sein
- Es sollten nur die Habits sichtbar sein, die dem jeweiligen Benutzer zugeordnet worden sind

### 1.3 Definitions, Acronyms, and Abbreviations

Keine

### 1.4 References

| Title | Publisher |
| ----- | --------- |
| [Blog](https://puggingtons.github.io/habittrackingblog/) | Habittracker Team |
| [GitHub](https://github.com/Puggingtons/habittracking) | Habittracker Team |
| [UCRS Erstellen eines Habits](ucrs_create_habit.md) | Habittracker Team|

### 1.5 Overview

Im folgenden wird der Ablauf der Sequenz beschrieben sowie die Voraussetzungen für das erfolgreiche Ausführen.

## 2 Flow of Events -- Design

Die Habitübersicht sollte die Hauptseite der Applikation sein, sobald sich der Benutzer angemeldet hat. Der Benutzer muss die Möglichkeit haben, alle eingetragenen Habits einzusehen, neue zu erstellen (siehe [UCRS Erstellen eines Habits](ucrs_create_habit.md)) und ggf. zu bearbeiten. Dafür wird die Habitübersicht verwendet.

![Aufrufen der Übersichtsseite](show_habitoverview.png)

Die Sequenz benötigt 4 Actor:

- Der Benutzer
- Zwei Participants
  - Das Frontend
  - Das Backend
- Die Datenbank

Die Sequenz beginnt mit der Öffnung der Übersicht durch den Benutzer (hauptsächlich nach der Anmeldung auf der Applikation). Das Frontend wird aktiviert und fragt dem Backend nach den Habits vom Benutzer an.

Das Backend leitet die Abfrage an die Datenbank weiter, wo die jeweiligen Habits abgespeichert worden sind. Die Datenbank gibt die Habitdaten der weiligen Einträge an das Backend zurück.

Das Backend leitet die Habitdaten anschließend an das Frontend weiter, wo es mithilfe einer UI dem Benutzer auf einer Übersicht angezeigt wird.



## 3 Derived Requirements

Für den Ablauf der Sequenz wird benötigt:

- Eine (zum Teil fertige) Rohseite für die Habitübersicht
- Eine Schnittstellte zwischen Frontend & Backend
- Eine Datenbank

Zudem müssen die folgenden Bedingungen erfüllt werden:

- Es sollten nur die Habits angezeigt werden, die dem angemeldeten Benutzer zugeordnet werden können
- Es dürfen nicht die Habits anderer Benutzer angezeigt werden