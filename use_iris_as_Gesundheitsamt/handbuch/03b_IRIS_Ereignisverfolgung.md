# Ereignis-Nachverfolgung (Gästelisten)

Im Bereich Ereignis-Nachverfolgung bietet IRIS connect die Möglichkeiten:

* Eine neue Ereignis-Nachverfolgung zu starten
* Offene Ereignis-Nachverfolgungen einzusehen
* Übertragene Daten aus einer Ereignis-Nachverfolgung zur Weiterbearbeitung in eine andere Fachanwendung mit entsprechender Schnittstelle oder per csv-Import zu übernehmen

![IRIS_event_start_request](images/IRIS_event_start_request.png "Starten einer Ereignis-Nachverfolgung (Screenshot enthält Beispiel- oder Testdaten)")
_Starten einer Ereignis-Nachverfolgung (Screenshot enthält Beispiel- oder Testdaten)_


### Starten einer neuen Ereignis-Nachverfolgung


Nach dem Starten einer neuen Ereignis-Nachverfolgung können Mitarbeitende im Gesundheitsamt eine einfach zu nutzende Suchfunktion zum Auffinden der Einrichtungen aufrufen.

Alle Einrichtungen, die digital über die angeschlossenen Lösungsanbieter Kontaktdaten erfassen, sind in einem digitalen Verzeichnis hinterlegt. Entsprechend genügen wenige Buchstaben, um eine Liste verfügbarer Orte anzeigen zu lassen. Beispiel: „Eiscafe Venezia“ könnte mehrmals gelistet sein.

![IRIS_event_looking_for_location](images/IRIS_event_looking_for_location.png "Suche nach einem Betrieb (Screenshot enthält Beispiel- oder Testdaten)")
_Suche nach einem Betrieb (Screenshot enthält Beispiel- oder Testdaten)_



* Durch Anzeige der Adresse des Betriebs/der Einrichtung kann in IRIS connect der passende Eintrag ausgewählt werden.
* Zur Abfrage müssen zusätzlich Datum und Zeitfenster der zu übermittelnden Gästeliste eingegeben werden, optional kann auch noch eine Textnachricht an den Betrieb übermittelt werden.

![IRIS_event_request_location](images/IRIS_event_request_location.png "image_tooltip")
_Anfrage bei einem Betrieb (Screenshot enthält Beispiel- oder Testdaten)_



* Durch Anklicken von „Absenden“ wird die Einrichtung zur Herausgabe der Daten aufgefordert (Dies passiert im Hintergrund durch eine Anfrage an den Lösungsanbieter, der die Daten verschlüsselt speichert. Der Lösungsanbieter leitet die Anfrage an die Einrichtung weiter – damit dieser eine Freigabe erteilen kann. Hier wird transparent die Information weitergereicht, dass die Anfrage von einem Gesundheitsamt gestartet wurde.)
* Die Einrichtung muss die Datenfreigabe erteilen und ermöglicht dadurch dem Lösungsanbieter die Verschlüsselung der Daten für das anfragende Gesundheitsamt anzupassen, so dass nur dieses die Daten auch wieder entschlüsseln kann.


### Prüfen offener Ereignis-Nachverfolgungen

* In einer übersichtlichen Liste werden gerade alle vom Gesundheitsamt angefragten Ereignis-Nachverfolgungen gelistet.
* Hier ändert sich der Status eines Eintrags, sobald eine angefragte  Einrichtung die Daten für das Gesundheitsamt freigegeben hat.
* Eine Filter- und Sortierfunktion erleichtert die Übersicht.

![IRIS_event_dashboard](images/IRIS_event_dashboard.png "Offene Ereignis-Nachverfolgungen (Screenshot enthält Beispiel- oder Testdaten)")
_Offene Ereignis-Nachverfolgungen (Screenshot enthält Beispiel- oder Testdaten)_


### Weiterbearbeitung bereitgestellter Daten

Die freigegebenen Daten einer Einrichtung können in IRIS connect zur Voransicht geöffnet werden.

* In der Voransicht haben Mitarbeitende des Gesundheitsamts die Möglichkeit, die enthaltenen Kontakte manuell an- oder abzuwählen. Dies ist deshalb erforderlich, weil es z.B. doppelte Einträge oder andere Unstimmigkeiten geben kann. So kann das Gesundheitsamt eine übersichtliche Vorauswahl treffen.

* Insbesondere ist eine Abwahl wichtig, da nicht alle zum selben Zeitpunkt anwesenden Personen automatisch relevante Kontakte z.B. ersten oder zweiten Grades sind. In der Regel sind Einrichtungen in Bereiche (z.B. Tische bei der Gastronomie) unterteilt. Hier liegt es im Ermessen des Fachpersonals zu entscheiden, welche Daten ins nachgelagerte System übernommen werden sollten. Es steht natürlich auch frei, alle Einträge der Liste zu übernehmen.

* Nach der Anwahl der zu übernehmenden Daten können diese an die nachgelagerte Fachanwendung mittels Schnittstelle oder per csv-ex/import übergeben werden.
* Hier stehen als Optionen derzeit Schnittstellen mit SORMAS und Octoware, sowie ein json/csv-Export zur Verfügung. Weitere Anbindungen an Systeme wie bspw. Äskulab21, ISGA, Mikado, o.a. bzw. Eigenentwicklungen sind mit geringem Aufwand möglich, sofern diese Anwendungen entsprechende (Import-)Funktionen haben oder entwickeln.
* In SORMAS werden automatisch die entsprechenden Aufgaben für die Kontaktnachverfolgung zur Weitergabe an entsprechende weitere Mitarbeitende erstellt. Dies erleichtert ggf. die Koordinierung innerhalb des Gesundheitsamts.

![IRIS_event_details](images/IRIS_event_details.png "Datenauswahl zur Übernahme in die Fachanwendung (Screenshot enthält Beispiel- oder Testdaten)")
_Datenauswahl zur Übernahme in die Fachanwendung (Screenshot enthält Beispiel- oder Testdaten)_
