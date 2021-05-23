
<p style="color: red; font-weight: bold">>>>>>  gd2md-html alert:  ERRORs: 0; WARNINGs: 1; ALERTS: 24.</p>
<ul style="color: red; font-weight: bold"><li>See top comment block for details on ERRORs and WARNINGs. <li>In the converted Markdown or HTML, search for inline alerts that start with >>>>>  gd2md-html alert:  for specific instances that need correction.</ul>

<p style="color: red; font-weight: bold">Links to alert messages:</p><a href="#gdcalert1">alert1</a>
<a href="#gdcalert2">alert2</a>
<a href="#gdcalert3">alert3</a>
<a href="#gdcalert4">alert4</a>
<a href="#gdcalert5">alert5</a>
<a href="#gdcalert6">alert6</a>
<a href="#gdcalert7">alert7</a>
<a href="#gdcalert8">alert8</a>
<a href="#gdcalert9">alert9</a>
<a href="#gdcalert10">alert10</a>
<a href="#gdcalert11">alert11</a>
<a href="#gdcalert12">alert12</a>
<a href="#gdcalert13">alert13</a>
<a href="#gdcalert14">alert14</a>
<a href="#gdcalert15">alert15</a>
<a href="#gdcalert16">alert16</a>
<a href="#gdcalert17">alert17</a>
<a href="#gdcalert18">alert18</a>
<a href="#gdcalert19">alert19</a>
<a href="#gdcalert20">alert20</a>
<a href="#gdcalert21">alert21</a>
<a href="#gdcalert22">alert22</a>
<a href="#gdcalert23">alert23</a>
<a href="#gdcalert24">alert24</a>

<p style="color: red; font-weight: bold">>>>>> PLEASE check and correct alert issues and delete this message and the inline alerts.<hr></p>



# Einführung, Überblick & Funktionen

<p style="text-align: right">
In Kooperation mit und gefördert durch</p>



    <p style="text-align: right">
– vertraulich –</p>


<p style="text-align: right">
Stand 17.05.2021</p>



    <p style="text-align: right">
Björn Steiger Stiftung – Stiftung bürgerlichen Rechts</p>



    <p style="text-align: right">
</p>



#### Inhaltsverzeichnis


[TOC]



# 1 Einführung


## 1.1 Was ist IRIS?

IRIS ist eine digitale Schnittstelle zum Einsatz in Gesundheitsämtern. Sie ermöglicht digital erfasste Daten von Bürgern und Veranstaltungsorten im Rahmen eines aktuellen Pandemiegeschehens im Bedarfsfall anzufragen und zur Weiter- verarbeitung an die in den Gesundheitsämtern verwendeten Anwendungen zu übergeben.

Der Fokus von IRIS liegt auf einem offenen pluralistischen Charakter: Eine Vielzahl innovativer Lösungen und Anbieter haben sich seit März 2020 mit einer breiten Lösungspalette zur digitalen Kontaktdatenerfassung etabliert. Viele weitere sind gerade im Entstehen, und zukünftiges Pandemiegeschehen kann wiederum neue Lösungen erfordern.

IRIS fungiert hier als Gateway für all diese Lösungen, um die Daten sicher und standardisiert an die Fachanwendungen im Gesundheitsamt zu übergeben. Mit dem Ziel, die Mitarbeitenden im Gesundheitsamt an den Stellen zu entlasten, die digital, datenschutzrechtlich und CoronaSchVO-konform möglich sind.


## 1.2 Welches Geschäftsmodell steht hinter IRIS? 

Das IRIS Projekt wurde im Oktober 2020 in Kooperation zwischen dem Innovationsverbund Öffentliche Gesundheit und der  Björn Steiger Stiftung gemein- nützig initiiert und finanziert, es besteht keine Gewinnerzielungsabsicht.

Der Quellcode von IRIS ist offen einsehbar (Open Source), die Schnittstellen zur Integration weiterer Lösungen sind hinreichend dokumentiert und der Betrieb durch  öffentliche Dienstleister vorgesehen.

IRIS kann von Gesundheitsämtern selbständig betrieben werden, bei Bereitstellung auf Landesebene durch die Björn Steiger Stiftung wird ein einmaliger Betrag je Gesundheitsamt zur Teilfinanzierung der Entwicklungskosten in Rechnung gestellt, ebenso wie eine jährliche Pauschale zur Deckung der Weiterentwicklungskosten. IRIS kann ebenfalls über sog. „IRIS Trusted Partner“ angeboten werden, diese können eine Bereitstellung z.B. in Kombination mit weiteren Diensten anbieten.


## 1.3 Warum gibt es IRIS?

Der Innovationsverbund Öffentliche Gesundheit (InÖG: [www.inög.de](http://www.inög.de)) ist eine gemeinnützige Initiative, die - ausgelöst durch den deutlich werdenden Bedarf in der Corona Krise - gegründet wurde um Innovation für den Öffentlichen Gesundheitsdienst verstehbar und implementierbar zu machen. Mit einem breiten Netzwerk und einem vielseitigen Portfolio innovativer Initiativen, entstehen Quervernetzungen um Synergiepotenzial zu heben und den größtmöglichen Mehrwert für den Öffentlich Gesundheitsdienst zu stiften. Dabei sind neben ideellen Verbindungen auch physische Verbindungen notwendig um Interoperabilität herzustellen und Manövrierfähigkeit herzustellen.

Parallel zu den Entwicklungen durch den InÖG und die Björn Steiger Stiftung, ebenfalls im Oktober 2020, haben sich erste Anbieter digitaler Kontakterfassungs- lösungen zur Initiative „Wir für Digitalisierung“ zusammengeschlossen, um gemeinsam Standards für den Datentransfer in die Gesundheitsämter zu definieren. Die Bemühungen der Initiative sind in dem IRIS Projekt aufgegangen, zum Zeitpunkt April 2021 stehen über 50 Lösungsbetreiber hinter dem Projekt und unterstützen den Ansatz einer offenen Schnittstelle.

IRIS wurde initiiert, um Gesundheitsämter im Rahmen des Pandemiegeschehens durch Einsatz digitaler Lösungen zu entlasten. 

Zum einen gibt es auf Seiten der Bürger*innen und Einrichtungsbetreibenden viele digitale Lösungen, die Pandemie-relevante Daten aus verschiedensten Anwendungsszenarien vorhalten. Zum anderen existieren auch auf Seiten der Gesundheitsämter gute digitale Fachanwendungen, um schnell agieren zu können. 

Was fehlte war eine digitale Verbindung zwischen beiden Endpunkten. So mussten bisher Listen auf Papier verschickt, gefaxt, oder als offene Datei per E-Mail verschickt und in den Gesundheitsämtern manuell den jeweiligen Fällen zugeordnet werden.


# 


# 2 Kurzübersicht: Wie funktioniert IRIS?


    IRIS besteht aus:



*   Zentralen Komponenten, die eine dezentrale Verbindung zwischen der Applikation und dem Gesundheitsamt vermitteln. Hier sind alle teilnehmenden digitalen Lösungen „registriert“. Über die dezentralen Verbindungen werden alle Anfragen aus den Gesundheitsämtern an die angeschlossenen Lösungen übertragen und entsprechend auch deren Daten entgegengenommen. 
*   Einer Benutzerschnittstelle in den Gesundheitsämtern (Client), über die Mitarbeitende die erfassten Daten der Bürger*innen und Einrichtungen anfragen, abrufen und filtern können. Hier wird eine Sicherheitsbarriere zwischen dem Internet und dem Netz des Gesundheitsamts aufgebaut.

     \


<p id="gdcalert1" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image1.jpg). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert2">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image1.jpg "image_tooltip")
 \
_Die Grafik zeigt die Anwendungsvielfalt anhand unterschiedlicher Einrichtungen und unterschiedlicher Optionen eines Corona-Infizierten, digital bei der Kontaktverfolgung zu unterstützen._



# 3 Wie entlastet IRIS die Gesundheitsämter?

Generell unterstützt IRIS das Gesundheitsamt bei der Anfrage und Beschaffung digital erfasster Daten.

Wenn dem Gesundheitsamt ein Indexfall gemeldet wird, sind folgende Daten relevant:



*   Die Daten des/der Infizierten: Über ein Telefonat nimmt das Gesundheitsamt Kontakt auf, den gesundheitlichen Status und die Versorgungssituation des/der Infizierten zu klären und um zu ermitteln wo der-/diejenige überall gewesen ist, mit wem er/sie dort gewesen ist, wen er/sie vielleicht dort unbewusst getroffen hat (unbekannte Dritte). \
 \
Durch die Indexfall-Nachverfolgung kann viel Zeit gespart werden: Digitale Kontakttagebücher wie aus der CWA  aber auch Webformulare, in die die Indexpersonen Daten für das Gesundheitsamt eintragen können, werden über IRIS ans Gesundheitsamt zurückgespielt. 
*   Die Daten der besuchten Orte: Durch die Angaben der/des Infizierten können diese gezielt abgefragt werden. Die Daten werden gemäß der Mitwirkungspflichten der Einrichtungsbetreibenden bereitgestellt. \
 \
IRIS findet über die Ereignisabfrage sofort heraus, ob die besuchten Orte digital Daten erfasst haben, kann sie anfragen und für das Gesundheitsamt passend bereitstellen.


###### 

<p id="gdcalert2" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image2.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert3">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image2.png "image_tooltip")
 \
Startseite von IRIS im Gesundheitsamt (Screenshot enthält Beispiel- oder Testdaten)




## 3.1 Funktionsüberblick Indexfall-Nachverfolgung


    Im Bereich Indexfall-Nachverfolgung bietet IRIS die Möglichkeiten:



*   Eine neue Indexfall-Abfrage zu starten
*   Offene Indexfall-Anfragen einzusehen
*   Übertragene Daten aus einer Indexfall-Anfrage zur Weiterbearbeitung zu übernehmen


### 3.1.1 Starten einer neuen Indexfall-Abfrage

Nach dem Starten einer neuen Indexfall-Abfrage wird eine spezifische TAN-Nummer für den/die Infizierten generiert und kann per E-Mail an diese/n versendet werden, oder sie wird beim Erstgespräch telefonisch übermittelt.

In der E-Mail werden der/dem Infizierten verschiedene Optionen zur Übermittlung der eigenen Kontakthistorie genannt:



*   Via Kontakttagebuch-App (z.Zt. bereits Coronika angeschlossen): Hier kann der/die Infizierte durch Eingabe eines Tokens die Daten für das Gesundheitsamt freigeben und versenden. Voraussetzung ist natürlich, dass der/die Infizierte die eine Tagebuch-App installiert hat und verwendet.
*   Via Online-Webformular: Über die Webseite [https://digitales-wartezimmer.org](https://digitales-wartezimmer.org) können Infizierte selbständig Daten erfassen, wann sie wo mit wem gewesen sind. Die Übermittlung erfolgt mittels eines Tokens direkt an das zugeordnete Gesundheitsamt. 
*   Als weitere Alternative wird eine Anbindung an das Kontakttagebuch und die Meldefunktionen der Corona Warn App gemeinsam mit den Entwicklern der CWA konzipiert. Hier gibt der Schlüssel des positiven Testergebnisses die Möglichkeit, Daten ins Gesundheitsamt zu senden. Es wird also eine Möglichkeit der freiwilligen Partizipation gegeben.

**_» Das IRIS Portal geht neue Wege, indem es die Bevölkerung befähigt, an der öffentlichen Gesundheit positiv mitzuwirken «_**


### 3.1.2 Prüfen offener Indexfall-Abfragen



*   In einer übersichtlichen Liste werden alle aktuell vom Gesundheitsamt angefragten Indexfälle gelistet.
*   Hier ändert sich der Status eines Eintrags, sobald der Indexfall via Webformular oder App Daten für das Gesundheitsamt bereitgestellt hat.
*   Eine Filter- und Sortierfunktion erleichtert die Übersicht.


###### 

<p id="gdcalert3" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image3.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert4">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image3.png "image_tooltip")
Offene Indexfall-Abfragen (Screenshot enthält Beispiel- oder Testdaten)


### 3.1.3 Weiterbearbeitung bereitgestellter Daten


    Daten eines Indexfalls, die dieser via Webformular oder App bereitgestellt hat, können in IRIS zur Voransicht geöffnet werden.



*   In der Voransicht hat der Mitarbeitende des Gesundheitsamts die Möglichkeit, einzelne Ereignisse, Begegnungen und Kontakte manuell an- oder abzuwählen. Dies ist deshalb erforderlich, weil es doppelte Einträge oder bspw. auch evtl. Fantasieorte geben kann, die der Indexfall angegeben hat.
*   Nach der Anwahl der zu übernehmenden Daten können diese an eine Fachanwendung übergeben werden.
*   Hier stehen als Optionen derzeit eine direkte Schnittstelle zu SORMAS und ein JSON/CSV-Export zur Verfügung. In Planung sind mögliche Anbindungen an weitere Systeme wie bspw. Octoware, Äskulab21, ISGA, Mikado, o.a. bzw. Eigenentwicklungen, sofern diese Anwendungen entsprechende Funktionen haben oder entwickeln.
*   In SORMAS werden automatisch die entsprechenden Aufgaben für die Kontaktnachverfolung zur Weitergabe an entsprechende weitere Mitarbeitende erstellt. Dies erleichtert ggf. die Koordinierung innerhalb des Gesundheitsamts.




## 3.2 Funktionsüberblick Ereignis-Nachverfolgung


    Im Bereich Ereignis-Nachverfolgung bietet IRIS die Möglichkeiten:



*   Eine neue Ereignis-Nachverfolgung zu starten
*   Offene Ereignis-Nachverfolgungen einzusehen
*   Übertragene Daten aus einer Ereignis-Nachverfolgung zur Weiterbearbeitung zu übernehmen


###### 

<p id="gdcalert4" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image4.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert5">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image4.png "image_tooltip")
 Starten einer Ereignis-Nachverfolgung (Screenshot enthält Beispiel- oder Testdaten)


### 3.2.1 Starten einer neuen Ereignis-Nachverfolgung


    Nach dem Starten einer neuen Ereignis-Nachverfolgung kann der Mitarbeitende des Gesundheitsamts eine einfach zu nutzende Suchfunktion zum Auffinden der Einrichtungen aufrufen.



*   Alle Einrichtungen, die digital über die angeschlossenen Lösungsanbieter Kontaktdaten erfassen, sind in einem digitalen Verzeichnis hinterlegt. Entsprechend genügen wenige Buchstaben, um eine Liste verfügbarer Orte anzeigen zu lassen. Beispiel: „Eiscafe Venezia“ könnte sicherlich über 50 Mal gelistet sein. 


###### 

<p id="gdcalert5" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image5.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert6">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image5.png "image_tooltip")
  \
Suche nach einem Betrieb (Screenshot enthält Beispiel- oder Testdaten)



*   Durch Anzeige der Adresse des Betriebs/der Einrichtung kann in IRIS der passende Eintrag ausgewählt werden. 
*   Zur Abfrage müssen nun noch Datum und  Zeitfenster der zu übermittelnden Gästeliste eingegeben werden, optional kann auch noch eine Textnachricht an den Betrieb übermittelt werden. 


###### 

<p id="gdcalert6" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image6.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert7">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image6.png "image_tooltip")
  \
Suche nach einem Betrieb (Screenshot enthält Beispiel- oder Testdaten)



*   Durch Anklicken von „Absenden“ wird die Einrichtung zur Herausgabe der Daten aufgefordert. (Dies passiert im Hintergrund durch eine Anfrage an den Lösungsanbieter, der die Daten verschlüsselt speichert. Der Lösungsanbieter leitet die Anfrage an den Einrichtung weiter – damit dieser eine Freigabe erteilen kann. Hier wird transparent die Information weitergereicht, dass die Anfrage von einem Gesundheitsamt gestartet wurde.)
*   Die Einrichtung muss die Datenfreigabe erteilen, diese Freigabe ermöglicht dem Lösungsanbieter die Verschlüsselung der Daten für das anfragende Gesundheitsamt anzupassen, so dass nur dieses die Daten auch wieder entschlüsseln kann. 


### 3.2.2 Prüfen offener Ereignis-Nachverfolgungen



*   In einer übersichtlichen Liste werden gerade alle vom Gesundheitsamt angefragten Ereignis-Nachverfolgungen gelistet. 
*   Hier ändert sich der Status eines Eintrags, sobald eine angefragte  Einrichtung die Daten für das Gesundheitsamt freigegeben hat.
*   Eine Filter- und Sortierfunktion erleichtert die Übersicht.


###### 

<p id="gdcalert7" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image7.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert8">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image7.png "image_tooltip")
 Offene Ereignis-Nachverfolgungen (Screenshot enthält Beispiel- oder Testdaten)


### 3.2.3 Weiterbearbeitung bereitgestellter Daten


    Die freigegebenen Daten einer Einrichtung können in IRIS zur Voransicht geöffnet werden.



*   In der Voransicht hat der Mitarbeitende des Gesundheitsamts die Möglichkeit, die enthaltenen Kontakte manuell an- oder abzuwählen. Dies ist deshalb erforderlich, weil es z.B. doppelte Einträge oder andere Unstimmigkeiten geben kann. So kann das Gesundheitsamt eine übersichtliche Vorauswahl treffen.
*   Insbesondere ist eine Abwahl wichtig, da nicht alle zum selben Zeitpunkt anwesenden Personen automatisch Kontakte ersten oder zweiten Grades sind. In der Regel sind Einrichtungen in Bereiche (z.B. Tische bei der Gastronomie) unterteilt. Hier liegt es im Ermessen des Gesundheitsamtsmitarbeitenden zu entscheiden, welche Daten ins nachgelagerte System übernommen werden sollten. Es steht natürlich auch frei, alle Einträge der Liste zu übernehmen.
*   Nach der Anwahl der zu übernehmenden Daten können diese an die nachgelagerte Fachanwendung übergeben werden.
*   Hier stehen als Optionen derzeit eine Schnittstelle mit SORMAS und ein JSON/CSV-Export zur Verfügung. In Planung sind mögliche Anbindungen an weitere Systeme wie bspw. Octoware,  Äskulab21, ISGA, Mikado, o.a. bzw. Eigenentwicklungen, sofern diese Anwendungen entsprechende Funktionen haben oder entwickeln.
*   In SORMAS werden automatisch die entsprechenden Aufgaben für die Kontaktnachverfolgung zur Weitergabe an entsprechende weitere Mitarbeitende erstellt.Dies erleichtert ggf. die Koordinierung innerhalb des Gesundheitsamts.


###### 

<p id="gdcalert8" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image8.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert9">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image8.png "image_tooltip")
 Datenauswahl zur Übernahme in die Fachanwendung  \
(Screenshot enthält Beispiel- oder Testdaten)


# 


# 4 Typisches Ende-zu-Ende Anwendungsszenario


## 4.1 Beispiel: Wochenende der Familie Schmitz


#### Am Samstag ist die Familie unterwegs!


<table>
  <tr>
   <td>Peter Schmitz bringt Sohn Louis nachmittags zum Fußballtraining und schaut zu. 
<p>
Mit seinem Handy fotografiert er einen QR Code am Sportplatz und klickt „Check in“.
   </td>
   <td colspan="3" >
    <p style="text-align: right">


<p id="gdcalert9" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image9.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert10">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


<img src="images/image9.png" width="" alt="alt_text" title="image_tooltip">
</p>

   </td>
  </tr>
  <tr>
   <td colspan="3" >
        

<p id="gdcalert10" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image10.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert11">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


<img src="images/image10.png" width="" alt="alt_text" title="image_tooltip">

   </td>
   <td>Danach geht Peter mit seiner Frau Anouk ins Kino. 
<p>
Mit seinem Handy klickt Peter in der Ticket-App am Sitzplatz im Kino „Platz genommen“.
   </td>
  </tr>
  <tr>
   <td colspan="2" >Abends geht die Familie Pizza-Essen in die Pizzeria Mio. 
<p>
Mit seinem Handy fotografiert Peter einen QR-Code am Tisch und klickt „Check-in“.
   </td>
   <td colspan="2" ><p style="text-align: right">


<p id="gdcalert11" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image11.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert12">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


<img src="images/image11.png" width="" alt="alt_text" title="image_tooltip">
</p>

   </td>
  </tr>
</table>



#### Sonntag


<table>
  <tr>
   <td>Am Morgen besucht Peter Schmitz ein Testzentrum und wird Corona-Positiv getestet.
   </td>
   <td colspan="2" >
    <p style="text-align: right">


<p id="gdcalert12" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image12.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert13">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


<img src="images/image12.png" width="" alt="alt_text" title="image_tooltip">
</p>

   </td>
  </tr>
  <tr>
   <td colspan="2" >
    

<p id="gdcalert13" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image13.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert14">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


<img src="images/image13.png" width="" alt="alt_text" title="image_tooltip">

   </td>
   <td>Über das ans Testzentrum angeschlossene Labor wird das zuständige Gesundheitsamt durch die bestehenden Systeme informiert und im dortigen System als “Indexfall” erfasst.
   </td>
  </tr>
</table>



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


<p id="gdcalert14" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image14.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert15">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


<img src="images/image14.png" width="" alt="alt_text" title="image_tooltip">
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


<p id="gdcalert15" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image15.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert16">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


<img src="images/image15.png" width="" alt="alt_text" title="image_tooltip">
</p>

   </td>
  </tr>
</table>



#### Peter übermittelt die Daten über ein Web-Formular am Computer


<table>
  <tr>
   <td>


<p id="gdcalert16" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image16.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert17">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


<img src="images/image16.png" width="" alt="alt_text" title="image_tooltip">

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
Dies sind in unserem Fall: \
- Direktkontakte: Anouk und Louis \
- Kontaktorte (Einrichtungen):  \
   Sportplatz, Kino, Pizzeria
   </td>
   <td><p style="text-align: right">


<p id="gdcalert17" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image17.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert18">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


<img src="images/image17.png" width="" alt="alt_text" title="image_tooltip">
</p>

   </td>
  </tr>
</table>



#### Gesundheitsamt kann Peters Daten sichten & übernehmen


<table>
  <tr>
   <td>

<p id="gdcalert18" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image18.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert19">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


<img src="images/image18.png" width="" alt="alt_text" title="image_tooltip">

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


<p id="gdcalert19" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image19.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert20">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


<img src="images/image19.png" width="" alt="alt_text" title="image_tooltip">
</p>

   </td>
  </tr>
</table>



#### Gesundheitsamt fordert Infos von der Pizzeria an


<table>
  <tr>
   <td>

<p id="gdcalert20" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image20.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert21">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


<img src="images/image20.png" width="" alt="alt_text" title="image_tooltip">

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

<p id="gdcalert21" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image21.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert22">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


<img src="images/image21.png" width="" alt="alt_text" title="image_tooltip">

   </td>
  </tr>
</table>



#### Gesundheitsamt kann die Daten der Pizzeria abrufen


<table>
  <tr>
   <td>

<p id="gdcalert22" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image22.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert23">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


<img src="images/image22.png" width="" alt="alt_text" title="image_tooltip">

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

<p id="gdcalert23" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image23.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert24">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


<img src="images/image23.png" width="" alt="alt_text" title="image_tooltip">

   </td>
  </tr>
</table>



# 5 Wie wird IRIS betrieben?


## 5.1 Technische Betreibergrafik


###### 

<p id="gdcalert24" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image24.jpg). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert25">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image24.jpg "image_tooltip")



######  \
C2-Container-Diagramm


## 5.2 Technische Informationen


### 5.2.1 Gateway


    Die zentrale Komponente wird einmal gehostet*. Es dient als Vermittler von dezentralen Verbindungen zwischen Apps und den IRIS–Clients in den Gesundheitsämtern, um die verschlüsselten Daten weiterzugeben, und verteilt diese an die IRIS-Clients weiter. 


    Das Gateway hält zudem einen nur für Gesundheitsämter zugänglichen Suchindex vor, in dem an IRIS-kompatible Apps angeschlossene Betriebe und Einrichtungen hinterlegt sind. Hierüber können die Gesundheitsämter elektronische Datenanfragen an den Betrieb bzw. die Einrichtung senden, welche vom Gateway dann automatisch übermittelt werden. Oft liegen die angefragten Daten dem Gesundheitsamt dann binnen weniger Minuten vor.


    Das Gateway verfügt über einen öffentlichen Endpunkt, welcher aus dem Internet zugänglich sein muss.


    Außerdem verfügt das Gateway über einen privaten Endpunkt, welche für die Clients zugänglich sein muss. Dieser Endpunkt sollte idealerweise nicht aus dem Internet erreichbar sein, darf es aber aufgrund der verwendeten Authentifizierung der Clients durch Client-Zertifikate auch sein.


    Bei dem Gateway handelt es sich um Applikationen, die als Docker Images bereitgestellt werden.


    _*Das Gateway wird in einem staatlichen RZ (AKDB) gehostet._


### 5.2.2 Client


    Den IRIS-Client gibt es für jedes Gesundheitsamt ein Mal. Die Clients können zentral in einem Rechenzentrum gehostet werden, solange sichergestellt ist, dass aus dem Gesundheitsamt auf den Client zugegriffen werden kann. 


    Wenn ein Gesundheitsamt SORMAS verwendet, muss sichergestellt sein, dass der Client auf SORMAS zugreifen kann. Da die REST-APIs der SORMAS-Instanzen derzeit i.d.R. aus dem Internet zugänglich sind, sollte dies keine besondere Herausforderung darstellen. Der Zugriff auf SORMAS erfolgt per vorhandener REST-API.


    Sollte das Gesundheitsamt eine andere Fachanwendung zur Weiterbearbeitung der Daten verwenden, so muss auch diese entsprechend erreichbar sein .


    Da der IRIS-Client die vom Gateway erhaltenen Daten entschlüsselt und die Mitarbeiter im Gesundheitsamt auf den Client per Web-Oberfläche zugreifen, ist eine Firewall, die den Zugriff durch Dritte verhindert empfehlenswert, aber nicht zwingend notwendig, da der Client selbstverständlich eine Authentifizierung (Login) verwendet.


    Bei dem Client handelt es sich um Applikationen, die als Docker Images bereitgestellt werden.


## 5.3 Installation, Support, Weiterentwicklung


    Die Installation der Iris-Clients für Gesundheitsämter kann erfolgen durch:



*   Den Betreiber des kommunalen Rechenzentrums, in dem der Client betrieben werden soll
*   Einen „IRIS Trusted Partner“, der in der Regel auch noch weitere digitale Services bereitstellt, gerne erteilen wir hier weitere Auskünfte
*   Einen empfohlenen Anbieter, gerne erteilen wir hier weitere Auskünfte
*   Für weitere Funktionsbedarfe: sprechen Sie uns an, bzw. wenden Sie sich auch gern an das Entwicklungsteam auf GitHub. Dort gibt es (in Kürze) auch ein Forum.
*   Weitere Unterlagen werden aktuell erstellt und stehen in Kürze bereit


## 5.4 Datenschutz- und Sicherheitskonzept


    Ein umfassendes IRIS Datenschutzkonzept, die Risikoabschätzung sowie die geplanten Penetrationstest sind in aktuell (Stand 01.04.21) in Umsetzung. Wir werden hier versuchen so viel wie möglich bereits parallel zur Fertigstellung der Entwicklung zu erstellen.


    Viele der angebundenen digitalen Lösungen sind bereits seit bis zu 12 Monaten in Betrieb und entsprechende datenschutzrechtliche Prüfungen und Bewertungen liegen vor.


    Im Rahmen der Anbindung findet ein Onboarding-Prozess statt, bei dem grundlegende technische Fragen und Daten- sowie IT-Sicherheitskonzepte abgefragt werden. Außerdem verpflichten sich die Verantwortlichen der anzuschließenden Lösungen den Code of Conduct einzuhalten.


    IRIS übernimmt keinerlei inhaltliche Prüfung der Unterlagen. Die Anbindung der Applikationen leitet sich aus den CoronaSchutzVO der Länder ab.


## 5.5 Anbindung von weiteren digitalen Lösungen 


    Die vorläufige Spezifikation der API und Schnittstellen-Spezifikation zum Anbinden weiterer digitaler Lösungen ist verfügbar unter folgendem Link:


    [https://github.com/iris-connect/eps](https://github.com/iris-connect/eps) 


## 5.6 Expertise des IRIS Entwicklerteams


    Das Entwickler-Team hinter IRIS setzt sich cross-funktional zusammen und besitzt eine breite praktische Erfahrung und detaillierte Kenntnisse in den Bereichen:



*   Umsetzung von CoronaSchVO-konformen Kontaktdatenerfassungs-Lösungen, welche persönliche Daten verarbeiten
*   Datenschutz und IT-Sicherheit
*   Implementierung und Roll-out von reichweitenstarken Kontakterfassungs-Lösungen mit direkter Anbindung an das Gateway (in Kooperation mit weiteren Lösungen)
*   Kenntnis der Architektur und des Source-Code der Fachanwendung SORMAS zur sicheren, schnellen und störungsfreien Integration von SORMAS mit dem IRIS System (Client/Gateway) und den damit verbundenen Funktionen.
*   Kenntnisse über weitere Fachanwendungen wie z.B. BaySIM sowie Prozess- und Datenmigrationen von Bestands- in Zielsysteme
*   Arbeitsweise im Gesundheitsamt bei Ausbruchsermittlung und Kontaktpersonen-Nachverfolgung und die verschiedenen Nutzerrollen und Zuständigkeiten, insbesondere beim Einsatz von SORMAS
*   Geläufige medizinische und infektionsepidemiologische Terminologie

**_Diese Kombination aus IT-KnowHow mit der praktischen Realität zeichnet IRIS aus._**


# 6 Roadmap und Rollout-Zeitplan


    Die hier genannten Zeitangaben sind ohne Gewähr.


## 6.1 IRIS Client 1.0


    Benutzeroberfläche zur Ereignis-Abfrage an digitale Kontakterfassungslösungen: Beta-Version verfügbar, geplante Fertigstellung Anfang Mai


## 6.2 IRIS Client 2.0 


    Benutzeroberfläche zur Indexfall-Abfrage an digitale Kontakttagebücher: in Umsetzung, geplante Fertigstellung Anfang/Mitte Mai


## 6.3 SORMAS-Connector 


    Integration des IRIS-Clients in SORMAS: Beta-Version verfügbar, geplante Fertigstellung Mitte Mai


## 6.4 Vorläufiger Fahrplan



*   Fertigstellung eines Demonstrators zum 01.04.21. \
Dieser soll verständlich das Gesamtkonstrukt aus QR-Codes, Bürgern, einer Vielzahl digitaler Lösungen und Gesundheitsamt präsentieren.
*   Betriebsstart iris-connect über AKDB/govdigital: Ende April
*   Einsatz IRIS-Client erste Test-GAs: Ende April
*   Einsatz IRIS-Client 1.0 in Modell-GAs ohne SORMAS-Integration: Mitte Mai
*   Einsatz IRIS-Client 1.0 in Modell-GAs mit SORMAS-Integration: Ende Mai
*   Breiter Rollout IRIS-Client für alle GA: Mitte Juni
*   Sukzessive Ausweitung Funktionsumfang IRIS-Client 2.0: fortlaufend


## 6.5 Vertragspartner


    Vertragspartner ist die Björn Steiger Stiftung.
