# 4 Typisches Ende-zu-Ende Anwendungsszenario


## 4.1 Beispiel: Wochenende der Familie Schmitz


**Am Samstag ist die Familie unterwegs!**


| Peter Schmitz bringt Sohn Louis nachmittags zum Fußballtraining und schaut zu.     Mit seinem Handy fotografiert er einen QR Code am Sportplatz und klickt „Check in“.  | ![checkin_soccer](images/checkin_soccer.png "CheckIn beim Fussball") |
| ![checkin_cinema](images/checkin_cinema.png "CheckIn im Kino") | Danach geht Peter mit seiner Frau Anouk ins Kino. Mit seinem Handy klickt Peter in der Ticket-App am Sitzplatz im Kino „Platz genommen“. |
| Abends geht die Familie Pizza-Essen in die Pizzeria Mio. Mit seinem Handy fotografiert Peter einen QR-Code am Tisch und klickt „Check-in“ | ![checkin_restaurant](images/checkin_restaurant.png "CheckIn im Restaurant") |


**Sonntag**

| Am Morgen besucht Peter Schmitz ein Testzentrum und wird Corona-Positiv getestet. | ![test_positive](images/test_positive.png "Positiv getestet") |
| ![testresult_to_PHO](images/testresult_to_PHO.png "Testergebnis wird an GA übermittelt") | Über das ans Testzentrum angeschlossene Labor wird das zuständige Gesundheitsamt durch die bestehenden Systeme informiert und im dortigen System als “Indexfall” erfasst. |

## 4.2 Ablauf: Peter Schmitz ist Corona-positiv 


#### Gesundheitsamt ruft Peter an


<table>
  <tr>
   <td>Ein/e GesundheitsaufseherIn im Gesundheitsamt kontaktiert Peter zunächst telefonisch. Peter wird offiziell unter häusliche Isolation (Quarantäne) gestellt.
<p>
Hier wird Peter medizinisch zu Symptomen befragt und es findet eine kurze Beratung statt, Peter wird aber auch um Angabe/Verifikation seiner E-Mail-Adresse gebeten, und er bekommt einen Token mitgeteilt.
   </td>
   <td>
    <p style="text-align: right">


<img src="images/call_PHO.png" width="" alt="call_PHO" title="call_PHO">
</p>

   </td>
  </tr>
</table>



#### Gesundheitsamt fordert Infos zu Kontakten der letzten Tage


<table>
  <tr>
   <td>Unter Peters registrierter Indexfall-Nummer startet die/der GesundheitsaufseherIn in der IRIS-Oberfläche die Indexfall-Verfolgung. 
<p>
Peter erhält eine E-Mail, die ihn bittet, Angaben zu Kontakten der letzten Tage zu machen. In der E-Mail befindet sich ein Link.
   </td>
   <td><p style="text-align: right">

<img src="images/IRIS_tracing_start.png" width="" alt="IRIS_tracing_start" title="IRIS_tracing_start">
</p>

   </td>
  </tr>
</table>



#### Peter übermittelt die Daten über ein Web-Formular am Computer


<table>
  <tr>
   <td>

<img src="images/IRIS_tracing_senddata.png" width="" alt="IRIS_tracing_senddata" title="IRIS_tracing_senddata">

   </td>
   <td>Da Peter keine Kontakttagebuch-App verwendet, kann er alle Informationenüber über ein sicheres Web-Formlar (“Digitales Wartezimmer”) eingeben und die Daten mit seinem Token fürs Gesundheitsamt freigeben. 
<p>
Würde Peter eine Kontakttage- buch-App (z.B. Coronika) nutzen, ginge das auch sehr einfach darüber und bald sogar auch über die Corona-Warn-App.
<p>

Über den Token wird auch sichergestellt, dass das Gesundheitsamt die Daten eindeutig zu Peters Fall zuordnen kann.
   </td>
  </tr>
</table>



#### Gesundheitsamt kann die Daten abrufen


<table>
  <tr>
   <td>Die/der GesundheitsaufseherIn wird nun innerhalb von IRIS informiert, dass Peters Daten vorliegen. Er sieht eine Übersicht aller Kontakte und Orte und kann selber entscheiden, welche davon Relevanz haben. 
<p>
Dies sind in unserem Fall: 
* Direktkontakte: Anouk und Louis 
* Kontaktorte (Einrichtungen):  Sportplatz, Kino, Pizzeria
   </td>
   <td><p style="text-align: right">


<img src="images/IRIS_tracing_checkIndexdata.png" width="" alt="IRIS_tracing_checkIndexdata" title="IRIS_tracing_checkIndexdata">
</p>

   </td>
  </tr>
</table>



#### Gesundheitsamt kann Peters Daten sichten & übernehmen


<table>
  <tr>
   <td>

<img src="images/IRIS_tracing_importdata.png" width="" alt="IRIS_tracing_importdata" title="IRIS_tracing_importdata">

   </td>
   <td>Die/der GesundheitsaufseherIn überführt die ausgewählten Daten in das nachgelagerte Software-System. 
<p>
Weitere Prozesse werden aus diesem angestoßen: Gespräch mit Anouk, ggfs. Absonderungsbescheide für Anouk & Louis und die Aufforderung zum Test.
   </td>
  </tr>
</table>



#### Gesundheitsamt überprüft die Orte, an denen sich Peter aufgehalten hat


<table>
  <tr>
   <td>
    Die/der GesundheitsaufseherIn kann nun erneut IRIS nutzen, um Informationen darüber abzufragen, wer sich zu der betreffenden Zeit ebenfalls an den besuchten Orten aufgehalten hat. 
<p>

Obwohl an allen Aufenthaltsorten entsprechende Hygienekonzepte umgesetzt sind, interessiert in Peters Fall besonders die Pizzeria, da Peter selbst angegeben hatte, dass es dort an der Theke etwas enger zuging.
   </td>
   <td><p style="text-align: right">

<img src="images/IRIS_tracing_event.png" width="" alt="IRIS_tracing_event" title="IRIS_tracing_event">
</p>

   </td>
  </tr>
</table>



#### Gesundheitsamt fordert Infos von der Pizzeria an


<table>
  <tr>
   <td>


<img src="images/IRIS_event_request.png" width="" alt="IRIS_event_request" title="IRIS_event_request">

   </td>
   <td>Hierzu startet die/der Gesundheits- aufseherIn in IRIS eine neue “Ereignis-Nachverfolgung”. Eine intuitiv zu bedienende Suchmaske ermöglicht das schnelle Finden über den Namen - denn IRIS funktioniert wie eine Internet-Suche: 
<p>
Alle angebundenen Lösungen stellen ein Register der deutschlandweit digital angebundenen Begegnungsorte zur Verfügung. Bei Eingabe von “Pizzeria Mio” erscheinen 12 Einträge, die/der GesundheitsaufseherIn kann anhand des Ortes die richtige auswählen.
   </td>
  </tr>
</table>



<table>
  <tr>
   <td>Nun grenzt die/der GesundheitsaufseherIn noch die richtige Uhrzeit ein und startet die Abfrage. Im Hintergrund kontaktiert IRIS nun den den Lösungsanbieter, mit dem die Pizzeria Mio ihre Gästedaten erfasst.
<p>
Die digitale Lösung wiederum kontaktiert automatisch die Pizzeria Mio, dass eine Anfrage vom Gesundheitsamt vorliegt. Pizzeria Mio erteilt gemäß Mitwirkungspflicht eine Freigabe für die Daten – und diese werden mit dem Schlüssel des anfragenden GA verschlüsselt und durch eine von IRIS vermittelte Verbindung übertragen. So sieht auch der Betrieb die Daten nicht, nur das anfragende Gesundheitsamt kann die Daten entschlüsseln.
   </td>
   <td>

<img src="images/IRIS_event_handling.png" width="" alt="IRIS_event_handling" title="IRIS_event_handling">

   </td>
  </tr>
</table>



#### Gesundheitsamt kann die Daten der Pizzeria abrufen


<table>
  <tr>
   <td>

<img src="images/IRIS_event_datafromlocation.png" width="" alt="IRIS_event_datafromlocation" title="IRIS_event_datafromlocation">

   </td>
   <td>Die/der GesundheitsaufseherIn wird nun wieder innerhalb von IRIS informiert, dass die Daten aus der Pizzeria vorliegen. 
<p>
Durch Anklicken werden diese für die/den GesundheitsaufseherIn entschlüsselt – und er/sie kann alle Besucher sehen, die zur gleichen Zeit wie Peter in der Pizzeria waren.
   </td>
  </tr>
</table>



#### Gesundheitsamt kann Daten aus der Pizzeria sichten & übernehmen


<table>
  <tr>
   <td>Erneut kann die/der GesundheitsaufseherIn nun selber entscheiden, welche der Daten ins nachgelagerte System übertragen werden sollen. Es wird sichtbar, dass Peter mit Anouk und Louis im Barbereich gesessen hat. 
<p>
Ebenfalls im Barbereich waren zur selben Zeit zwei weitere Gäste und der Bar-Mitarbeitende. Diese wählt die/der GesundheitsaufseherIn aus, um sie ins nachgelagerte System zu überführen.
   </td>
   <td> 

<img src="images/IRIS_event_datafromlocation_chekced.png" width="" alt="IRIS_event_datafromlocation_chekced" title="IRIS_event_datafromlocation_chekced">

   </td>
  </tr>
</table>



