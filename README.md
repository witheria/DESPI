# DACH eSports Package Installer
Der *DACH eSports Package Installer* ist ein kleines Programm, um Streaming-Packages, die von OBS (*Open Broadcaster Software*) exportiert werden, automatisiert und vollständig zu verschieben, ohne dabei die Dateipfade der Dateien einzeln ändern zu müssen. 

#### Das Programm benutzt die folgenden Module um seiner Aufgabe nachzugehen:

 - [PyQt5 Gui, Widgets, Core](https://pypi.org/project/PyQt5/)
 - [pathlib](https://docs.python.org/3/library/pathlib.html)
 - [inspect](https://docs.python.org/3/library/inspect.html)

DESPI wurde in **Python** implementiert und mit [pyinstaller](https://www.pyinstaller.org/) zu einer unter Windows ausführbaren .exe gepackt. 
Weitere Module können dem Code entnommen werden.

## Benutzung
Der Gebrauch ist denkbar einfach:
 1. Nach Ausführen des Installers öffnet der Button "Installiere das Paket" ein Ordner- Auswahlfenster, mit dessen Hilfe der Zielordner in das Programm eingegeben wird (wo das Paket am Ende hin soll). 
 2. Ist das geschehen, öffnet sich ein Datei-Auswahlfenster, in die JSON-Datei des Packages gesucht und eingegeben wird (wo das Paket ist). 
 3. Das Paket wurde fertig in dem angegebenem Ordner installiert. 
 
 Das Programm:
  - kopiert *alles* im Ordner der JSON-Datei an die neue Location
  - ändert Pfade von allen Elementen die in diesem Paket liegen (*müssen in einem eindeutigen Unterordner liegen!*) in der JSON
  **!WICHTIG! 
     Damit von einem Objekt der Pfad geändert wird, muss es eindeutig dem Paket zuweisbar sein! Das wird z.B. durch einen Unterordner erreicht.
     Beispiel:
     Alle Dateien des Pakets liegen im Unterordner /paket/..., die JSON auch, dann werden alle Pfade von Elementen die diesen Ordner im Namen haben geändert
     !WICHTIG!**
     

  - trägt die neue Szenensammlung in die OBS-Szenenliste ein (Programm muss als Administrator ausgeführt werden!)
  - öffnet OBS mit der neuen Szenensammlung (funktioniert auch nur als Administrator)
 
**WICHTIG!** Befindet sich der Zielordner auf einer anderen Partition als der, auf der DESPI ausgeführt wird, *muss* das Programm als Administrator ausgeführt werden. 

Das Programm erstellt bei Benutzung im Ordner eine versteckte config-Datei, die die Daten der letzten Installation enthält. Diese Daten werden gebraucht um ein Paket mit dem Tool wieder zu entfernen. *Diese Funktion ist für ein versehentliches Installieren von Paketen gedacht und sollte nicht verwendet werden, wenn man sich nicht sicher ist, wo man zuletzt installiert hat.*

**WARNUNG!** Die Löschen-Funktion kann Daten und Ordner vollständig und ohne Rückmeldung permanent löschen. Sie sollte deshalb nur unmittelbar nach einer Installation oder mit der config-Datei verwendet werden.

Mit "Schließen" kann das Programm frühzeitig geschlossen werden. 

*Das Programm wird mithilfe einer Command-Prompt gestartet werden, um mögliche Fehler aufzufangen.*

    © Toni Schmidbauer 2020 / Released under GPL 2.0
    
    Bugs, Probleme, Kritiken: schmidbauer.biz@gmail.com
    
Contribute to future projects [Donate](https://www.paypal.com/donate?hosted_button_id=825RPFTRDCW7A) (to PayPal)
