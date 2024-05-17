# Semester 2, Woche 6: Metriken

Servus miteinander,

in dieser Woche beschäftigten wir uns mit den Metriken unseres Software Projektes. Während Paul sich Metriken für das Backend herausgesucht hat, hat Kayra versucht relevante und wichtige Metriken für das Frontend zu finden.

## Metriken im Frontend

Im Frontend gibt es leider nicht viele Optionen zum sammeln von Metriken, vorallem im react.js Framework. Die einzig relevanten Metriken (die auch für den Endbenutzer von Bedeutung sind) sind die über die Performance. Im Frontend kann gemessen werden...

- Wie schnell sich eine Seite rendert
- Wie lange ein Query vom/zum Backend dauert
- Wie lange die einzelnen Funktionen der Seite brauchen, bis sie abgeschlossen werden
- Wie viel (Arbeits-)Speicher die Seite benötigt

Tools zum messen dieser Metriken sind in den heutigen gängigsten Browsern schon eingebaut, aufrufbar über die sog. DevTools. Dort können unter anderem die Netzwerkaktivität, der Speicherverbrauch und die Performance (laden der Website) eingesehen werden.

Somit ist keine weitere Software nötig um solche Metriken aufzuzeichnen. Jedoch gibt es Browserextensions, die die DevTools erweitern/ergänzen können. Dies sind unter anderem [Google Lighthouse](https://developer.chrome.com/docs/lighthouse/overview?hl=de) und speziell für react.js die [React Developer Tools](https://react.dev/learn/react-developer-tools). Lighthouse kann jedoch nicht verwendet werden, da es nur die Performance von Online Seiten messen kann (kein `localhost`). Die React Developer Tools erweitern die DevTools im Browser um eine Anzeige zum listen aller Components der Seite und bietet einen Profiler zum messen der Rendergeschwindigkeit.

Es wurde somit beschlossen die DevTools des Browsers zusammen mit den React Developer Tools zu verwenden, um die Performance der Seite messen zu können. Eine Automatisierung dieses Prozesses ist Stand jetzt noch nicht möglich. Die Performance Messung erfolgt über den Brave Browser (basierend auf Chromium).

### Renderdauer

Die Renderdauer kann einfach durch den Profiler der DevTools gemessen werden. Sie zeigt an, wie lange eine einzelne Seite benötigt um gerendert zu werden und wie lange die einzelnen Komponenten der Seite benötigen.

![Performance der Login Page](/posts/media/PerformanceMetrikLogin.png)

Die Ergebnisse können nach einem Durchlauf in eine `json` Datei exportiert werden, um später die Daten zu veranschaulichen.

Nach mehrmaligem Messen erhielten wir folgende Metriken für die Login Page:

- Laden der Scripte: ~410ms
- Rendern der Seite: ~10ms
- System, Painting, Loading und Idling: ~40ms
- **Gesammtzeit: ~460ms**

Die Renderdauer besitzt somit aus unserer Sicht eine absolut akzeptable Dauer von einer halben Sekunde zum vollständigen Laden der Login Page. Es ist jedoch anzumerken, dass auf die Seite lokal zugegriffen wird. Heißt: Es können eventuelle Verzögerungen hinzukommen, falls die Seite Online gestellt wird (die durch das Netzwerk beeinflusst werden können).

### Benötigter Speicher

Über die DevTools können Snapshots von dem verbrauchten Speicher für die Seite aufgenommen werden. Das Snapshot beinhaltet die benötigte Menge an Speicher plus wie viel Speicher die Components der Seite benötigen (unter anderem complied Code, gespeicherte Arrays, CSS Styling etc...). Auch diese Ergebnisse können in eine `json` Datei exportiert werden.

![Speicher-Aufschlüsselung der Login Page](/posts/media/SpeicherLoginPage.png)

Es wurde festgestellt, dass die Login Page im **Durchschnitt ~22MB** an Speicher benötigt, um komplett angezeigt zu werden. Dies ist in unseren Augen ein akzeptabler Speicherverbrauch.
