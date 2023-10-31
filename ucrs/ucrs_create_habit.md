# Use-Case-Realization Specification
# Erstellung eines Habits

## 1 Introduciton

### 1.1 Purpose

Dieses Dokument beschreibt den Ablauf der Sequenz zum erstellen eines Habits. Es beschreibt die benötigten Ressourcen und den jeweiligen Arbeitsaufwand.

### 1.2 Scope

Dieses UCRS beschreibt den Ablauf der Sequenz zum erstellen eines Habits. Dies geschieht auf der Habitübersicht.

### 1.3 Definitions, Acronyms, and Abbreviations

Keine

### 1.4 References

- UCRS Habitübersicht

### 1.5 Overview



## 2 Flow of Events -- Design

Die Hauptfunktion der Applikation ist das Erstellen & Verwalten von Habits (Angewohnheiten). Damit überhaupt ein Habit verwaltet und verfolgt werden kann, muss sie erst erstellt werden. Diese Sequenz dient somit zur Erstellung eines Habits. Es beginnt auf der Habitübersicht.

![Erstellen eines Habits](create_habit.png)

Die Sequenz benötigt insgesamt 4 Actor:

- Der Benutzer
- Zwei Participants
  - Das Frontend
  - Das Backend
- Die Datenbank

Die Sequenz beginnt mit dem öffnen des Dialogs zum erstellen eines Habits auf der Habitübersicht. Dies aktiviert das Frontend und zeigt dem Benutzer das angefragte Dialog zum erstellen eines Habits an.

Der Benutzer gibt nun seine Habitdaten im Dialog ein. Beim Absenden der Daten wird das Frontend aktiviert, und leitet die Habitdaten an das Backend weiter. Das Backend aktiviert die Datenbank, erstellt neue Einträge und schreibt die Habitdaten in die Datenbank. 

Nach erfolgreichem erstellen der Einträge gibt die Datenbank die Habitdaten an das Backend zurück. Das Backend leitet die Daten an das Frontend weiter und zeigt dem Benutzer die Habitansicht an, wo das neu erstellte Habit hinzugefügt worden ist.

## 3 Derived Requirements
