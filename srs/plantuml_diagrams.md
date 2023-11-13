## Use-Case Diagram
```plantuml
left to right direction
:User: as user
:Account-Management: as mgmt
:Backend: as backend

rectangle Application {
	(registrieren) as reg
	(anmelden) as login
	(Habit erstellen) as create
	(Tätigkeit eintragen) as log
	(Habit bearbeiten) as edit
	(Habit entfernen) as remove
	(Habitübersicht anzeigen) as overview
	(Habit anzeigen) as show
}

reg ..> login : <<include>>
overview ..> show : <<include>>

user --- reg
reg -- mgmt

user -- login
login -- mgmt

user -- create
create -- backend

user -- log
log -- backend

user -- edit
edit -- backend

user -- remove
remove -- backend

user --- overview
overview -- backend

user -- show
show -- backend
```
## Sequenzdiagramme
### Registrieren
```plantuml
@startuml
actor       Benutzer  as us
participant Frontend  as fe
participant Backend   as be
database    Datenbank as db

us -> fe : fragt Registrationsseite an
activate fe
fe -> us : zeigt Registrationsseite an
deactivate fe
us -> fe : gibt Registrationsdaten ein
activate fe
fe -> be : sendet Registrationsdaten
activate be
be -> db : fragt Benutzerdaten\nmit Benutzername an
activate db

alt Benutzerdaten existieren bereits
  db -> be : Benutzerdaten
  be -> fe : Registration nicht bestätigen
  fe -> us : zeigt Fehler an\n[Benutzer mit Namen existiert bereits]
else Benutzerdaten existieren noch nicht
  db -> be : keine Benutzerdaten
  deactivate db
  be -> db : schreibe Benutzerdaten
  activate db
  db -> be : Benutzerdaten
  deactivate db
  be -> fe : Registration bestätigen
  deactivate be
  fe -> us : zeige Erfolgsnachricht an
  fe -> us : zeige Habitübersicht an
  deactivate fe
end

@enduml
```

### Anmelden
```plantuml
@startuml
actor       Benutzer  as us
participant Frontend  as fe
participant Backend   as be
database    Datenbank as db

us -> fe : fragt Loginseite an
activate fe
fe -> us : zeigt Loginseite an
deactivate fe
us -> fe : gibt Logindaten ein
activate fe
fe -> be : sendet Logindaten
activate be
be -> db : holt Logindaten vom Benutzer
activate db
db -> be : Logindaten vom Benutzer
deactivate db
be -> be : check Logindaten

alt Logindaten stimmen
  be -> be : Erstellt Sitzung
  be -> fe : Login bestätigt und Sitzung senden
  fe -> us : zeigt Habitübersicht
else Logindaten stimmen nicht
  be -> fe : Login nicht bestätigt
  deactivate be
  fe -> us : zeigt Fehlermeldung
  deactivate fe
end
@enduml
```

### Abmelden
```plantuml
@startuml
actor       Benutzer  as us
participant Frontend  as fe
participant Backend   as be
database    Datenbank as db

us -> fe : Logout wird getätigt
activate fe
fe -> be : Logoutanfrage
activate be
be -> be : Sitzung wird entfernt
be -> fe : Logout bestätigt
deactivate be
fe -> us : Loginseite wird angezeigt
deactivate fe
@enduml
```

### Habit erstellen
```plantuml
@startuml
actor       Benutzer  as us
participant Frontend  as fe
participant Backend   as be
database    Datenbank as db

us -> fe : öffnet Habiterstellungsdialog
activate fe
fe -> us : zeigt Habiterstellungsdialog an
deactivate fe
us -> fe : gibt Habitdaten ein
activate fe
fe -> be : sendet Habitdaten
activate be
be -> db : schreibt Habitdaten
activate db
db -> be : Habitdaten
deactivate db
be -> fe : Habitdaten
deactivate be
fe -> us : zeigt Habitansicht an
deactivate fe
@enduml
```

### Habit bearbeiten

```plantuml
@startuml
actor       Benutzer  as us
participant Frontend  as fe
participant Backend   as be
database    Datenbank as db

us -> fe : öffnet Habitansicht
activate fe
fe -> us : zeigt Habitansicht
deactivate fe
us -> fe : bearbeitet Habit
activate fe
fe -> be : sendet Habitdaten
activate be
be -> db : überschreibt Habitdaten
activate db
db -> be : Habitdaten
deactivate db
be -> fe : Habitdaten
deactivate be
fe -> us : Habitansicht mit neuen Daten anzeigen
deactivate fe
@enduml
```

### Habit löschen
```plantuml
@startuml
actor       Benutzer  as us
participant Frontend  as fe
participant Backend   as be
database    Datenbank as db

us -> fe : öffnet Habitansicht
activate fe
fe -> us : zeigt Habitansicht
deactivate fe
us -> fe : löscht Habit
activate fe
fe -> be : sendet Löschanfrage
activate be
be -> db : löscht Habitdaten
activate db
db -> be : Erfolg
deactivate db
be -> fe : Erfolg
deactivate be
fe -> us : Habitübersicht ohne\ngelöschtes Habit anzeigen
deactivate fe
@enduml
```

### Habitübersicht anzeigen
```plantuml
@startuml
actor       Benutzer  as us
participant Frontend  as fe
participant Backend   as be
database    Datenbank as db

us -> fe : öffnet Habitübersicht
activate fe
fe -> be : fragt Habits von Benutzer an
activate be
be -> db : fragt Habits von Benutzer an
activate db
db -> be : Habitsdaten
deactivate db
be -> fe : Habitsdaten
deactivate be
fe -> us : Habitübersicht anzeigen
deactivate fe
@enduml
```

## Aktivitätsdiagramme

### Registrieren (von Paul)
```plantuml
@startuml

start

:Open Website;

repeat :Open Registration View;

if ( ) then ( )
	stop
else ( )
	:Enter Registration Data;
endif

:Submit Registration Data;

repeat while (registration successful) is (no) not (yes)
  
:View Habitoverview;

stop

@enduml
```

### Anmelden (von Paul)
```plantuml
@startuml

start

:Open Website;

repeat :Open Login View;

if ( ) then ( )
	stop
else ( )
	:Enter Login Data;
endif

:Submit Login Data;

repeat while (login successful) is (no) not (yes)
  
:View Habitoverview;

stop

@enduml
```

### Abmelden (von Paul)
```plantuml
@startuml

start

:Open Website;

:Perfom Logout Action;

:View Landingpage;

stop

@enduml
```
## UML-Aktivitätsdiagramme
### Registrieren
@startuml
start

repeat :Benutzer gibt Daten ein;
:sende Daten zur Datenbank;
:check Daten;
backward:Warnung "Daten unvollständig";
repeat while (Daten falsch?)
->no;
If (Neuer Nutzer) then (yes)
:Benutzerdaten anlegen;
:Registration bestätigen;
:Seite Anzeigen;
else (no)
:Warnung "Benutzer existiert bereits";
:Registrierenseite anzeigen;
@enduml

### Anmelden
@startuml
start

repeat :Benutzer gibt Logindaten ein;
:sende Logindaten zur Datenbank;
:check Logindaten;
backward:Warnung "Benutzerdaten Falsch";
repeat while (Daten falsch?)
->no;
:Login bestätigen;
:Seite Anzeigen;
stop
@enduml

### Abmelden
@startuml
start

:Logout wird getätigt;
:Sitzung wird entfernt;
:Loginseite wird angezeigt;
stop
@enduml

## Klassendiagramme
```plantuml
@startuml
package backend {

	package node_modules {
		package @nest {
			class JwtService
		}
	
		package @prisma {
			class PrismaClient
		}
	}
	
	package AppModule {
	
	}

	package PrismaModule {
		class PrismaService
		PrismaService --|> PrismaClient
	}
	
	package UsersModule {
		class UsersService {
			findOne()
			create()
		}
	}
	
	package AuthModule {
		class AuthService {
			signIn()
			signOut()
			register()
		}
		AuthService ..> UsersService : <<use>>
		AuthService ..> JwtService : <<use>>

		class AuthController {
			signIn()
			signOut()
			register()
			getProfile()
		}
		AuthController ..> AuthService : <<use>>
	}

	AppModule ..> PrismaModule : <<use>>
	AppModule ..> UsersModule : <<use>>
	AppModule ..> AuthModule : <<use>>

	UsersModule ..> PrismaModule : <<use>>

	AuthModule ..> UsersModule : <<use>>
}
@enduml
```

 ```plantuml
@startuml
package frontend {
	package node_modules {
		package @react-router-dom {
			class "Routes" as rr_routes
			class "Route" as rr_route
		}
	}

	package Components {
		class Habit
		package Dialogues {
			class CreateHabit
			class EditHabit
			class DeleteHabit
		}
		Habit *-- CreateHabit
		Habit *-- EditHabit
		Habit *-- DeleteHabit
	}
	
	package Routes {
		class Login {
			sendLogin()
		}
		
		class Registration {
			sendRegistration()
		}
		
		class HabitOverview {
		}
		
		class Habitview {
		}

		HabitOverview "*" *-- Habit
		Habitview "1" *-- Habit
	}

	package Router {
		class AppRoutes
		AppRoutes ..> rr_routes : <<use>>
		AppRoutes ..> rr_route : <<use>>
		AppRoutes *-- Login
		AppRoutes *-- Registration
		AppRoutes *-- HabitOverview
		AppRoutes *-- Habitview
	}
}
@enduml
```
