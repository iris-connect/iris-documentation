# Häufig gestellte Fragen von App-Anbieter

## Gibt es für jedes GA eine eindeutige Reference?
Ja, jedes GA wird eindeutig authentifizierbar sein. Dies wird durch Verwendung eines Zertifikats der Bundesdruckerei gewährleistet.
 
## Wie kann man sich an IRIS connect andocken?
Es wird einen Onboarding Prozess geben. Davor werden Dokumente wie IT-Sicherheitskonzept und Datenschutzkonzept angefordert werden.
Diese müssen vorliegen, IRIS connect wird diese nicht prüfen, aber auf Verlangen der zuständigen Stellen herausgeben. 
Außerdem muss ein Whitepaper, das die Funktion und den Grund für den Betrieb bzw. das sammeln der Daten beschreibt, veröffentlicht werden.

Der Code of Conduct (CoC) gibt hier weitere Details, ist allerdings noch nicht final. Der CoC wird sich an den Kriterien von D64 orientierten. 
Open Source ist kein muss, aber schön. Zur Kommunikation mit den IRIS connect Diensten stellen wir einen Service bereit, der in der Infrastruktur
des Anbieters ohne weitere Abhängigkeiten betrieben werden kann. Details zur Implementierung veröffentlichen wir über ein GitHub Repository.

<a href="https://github.com/iris-connect/iris-documentation/blob/main/connect_your_app_to_IRIS/technical_details/app_onboarding.md">Connect your app to IRIS connect</a>

## Was muss ich als App-Anbieter tun, um meine App an IRIS connect technisch anzubinden?
IRIS connect besteht technisch aus mehreren Modulen. Das relevante Modul für die Integration der Apps in IRIS ist der EPS (EndPointService).
Der Provider "hostet" sich selbst einen internen EPS (kommt aus dem IRIS Projekt) und muss auf seiner Seite einen JSON-RPC Client und einen 
Server (Endpoint) implementieren. Die Adresse des internen Servers wird beim internen EPS hinterlegt.
Kommt dann am EPS eine Anfrage des GA an, spricht der EPS den internen JSON-RPC Endpunkt an.

Der EPS bietet selbst auch einen JSON-RPC Server an, den der Provider über seinen internen Client bedient. 
So können Requests an die anderen Akteure versendet werden.

## Wie kommt die Datenabfrage eines Gesundheitsamtes beim App-Anbieter oder beim Betreiber an? Gibt es ein Portal dafür?
IRIS connect bietet mit dem IRIS connect-Client ein Portal für die Gesundheitsämter. Apps werden nur über technische Schnittstellen angebunden. Das bedeutet, dass Benachrichtigungen sowie nötige Interaktionen durch die jeweilige App erfolgen müssen. Da es verschiedene Konzepte gibt, wie die Apps die Daten speichern (zentral oder dezentral) und verschlüsseln (symmetrisch oder asymmetrisch) bzw. wie die Schlüssel verwaltet werden (PKI, manuell, etc.) kann keine allgemeingültige Aussage über den Ablauf getroffen werden.

Datenanfragen des GAs werden an die Provider übertragen. Die Daten können dann vom Provider direkt zur Verfügung gestellt werden (falls die Daten 
im Backend vorliegen) oder im Falle einer externen Entschlüsselung aus dem Browser ans Gesundheitsamt übertragen werden. Zwei Beispiele sollen hier aufzeigen, wie der Ablauf in unterschiedlichen Konzepten aussehen kann.

### 1. Lösung mit durch einen öffentlichen Schlüssel des Betreibers zentral gespeicherten Daten:
- Datenabfrage vom Gesundheitsamt geht ein (Location, Zeitraum, öffentlicher Schlüssel des GA) signiert vom GA Zertifikat.
- EPS verifiziert die Abfrage (Autorisierung und Authentifizierung)
- EPS leitet die Abfrage an die App
- App meldet dem Betreiber das Vorliegen einer Datenabfrage vom Gesundheitsamt und verlangt die nötige Interaktion
- Betreiber bestätigt die Abfrage, womit die Daten in seinem Client abgefragt und entschlüsselt werden, um sie dann wieder mit dem GA Schlüssel
  verschlüsselt an den App-Server zu übertragen
- App-Server leitet die verschlüsselten Daten an den EPS weiter
- EPS leitet die Daten an den IRIS connect-Client des Gesundheitsamtes (dieser Schritt ist stark vereinfacht...)

### 2. Lösung mit durch den App-Anbieter verwalteten privaten Schlüsseln:
- Datenabfrage vom Gesundheitsamt geht ein (Location, Zeitraum, öffentlicher Schlüssel des GA) signiert vom GA Zertifikat.
- EPS verifiziert die Abfrage (Autorisierung und Authentifizierung)
- EPS leitet die Abfrage an die App
- App meldet dem Betreiber das Vorliegen einer Datenabfrage vom Gesundheitsamt
- App-Server holt sich den privaten Schlüssel, entschlüsselt die abgefragten Daten, um sie dann wieder mit dem GA Schlüssel zu verschlüsseln
- App-Server leitet die verschlüsselten Daten an den EPS weiter
- EPS leitet die Daten an den IRIS-Client des Gesundheitsamtes (dieser Schritt ist stark vereinfacht...)

## Kann ich als Unternehmen auch die IRIS connect Lizenz für den Kreis bezahlen, die sonst vom GA getragen müsste?
Die Software wird Open Source betrieben und generell unentgeltlich zur Verfügung gestellt. Daher fallen keine Lizenzkosten an.
Für die Gesundheitsämter bzw. deren koordinierende IT-Stelle wird ein Support- und Pflegevertrag durch die Björn Steiger Dienstleistung
GmbH angeboten. Dieser gewährleistet die Zurverfügungstellung der benötigten Zertifikate, telefonischen Support (Mo-Fr 9:00-18:00) und die
Softwarepflege. 

## Gibt es einen Test Monat?
Die Software wird Open Source betrieben und generell unentgeltlich zur Verfügung gestellt. Daher kann der IRIS Client jederzeit
heruntergeladen, installiert und getestet werden. Zum Produktivbetrieb im Gesundheitsamt ist allerdings ein Zertifikat erforderlich,
welches im Rahmen des Pflegevertrages für die Dauer von 12 Monaten zur Verfügung gestellt wird. 
 
## Was zahle ich als App für die Anbindung an IRIS connect?
Als Anbieter einer digitalen Lösung zur Kontaktdatenverfolgung zahlst Du nichts für die Anbindung – Du musst diese aber selbst durchführen.
Für Deine Anbindung sind bestimmte Anforderungen zu beachten, die sowohl technische als auch Sicherheits- und Datenschutzrechtliche Aspekte
betreffen. Eine ausführliche Dokumentation der Voraussetzungen zur Anbindung befindet sich hier.

`Link zu Github Anbieter API folgt`  
 
## Gibt es Standardanschreiben für GAs für die Vorstellung von IRIS connect?
Es gibt ein “Erklär-Dokument” zu IRIS connect, welches wir zur Verfügung stellen können. Wir weisen darauf hin, dass sich das Dokument regelmäßig
aktualisieren kann. Außerdem stellen wir Dir gerne ein paar leicht verständliche Folien mit einem typischen Einsatzszenario für IRIS connect vor.
Daneben gibt es eine Internetseite zu IRIS connect, die das Thema verständlich aufbereitet. In Kürze sind dort auch Presseberichte zu IRIS connect hinterlegt.
Weitergehende technische Informationen für die Gesundheitsämter werden aktuell erarbeitet und finden sich bald im GitHub-Repo.
 
## Wie lange gilt die GA Lizenz von IRIS connect?
Die Software wird Open Source betrieben und generell unentgeltlich zur Verfügung gestellt. Daher fallen keine Lizenzkosten an,
noch gibt es eine Lizenzdauer oder -gültigkeit. Der Produktivbetrieb im Gesundheitsamt ist allerdings nur mit einem Zertifikat
der Bundesdruckerei möglich, welches jeweils eine Gültigkeit von 12 Monaten besitzt. Ebenfalls zeitlich begrenzt ist der optionale
Support- und Pflegevertrag. Weitere Informationen hierzu finden sich im GitHub-Repo.
 
## Kann man über IRIS connect auch Registrierte Gäste mit einem Knopfdruck via SMS kontaktieren?
Nein, das ist nicht auf Seiten IRIS connect geplant. Diese Funktion könnte theoretisch auf Seiten der Anbieter der digitalen Lösung zur Kontaktdatenerfassung
implementiert sein, um Gäste über eine Übermittlung ihrer Daten an ein Gesundheitsamt per SMS zu informieren. IRIS connect übermittelt die Daten zur
Weiterbearbeitung an die IfSG Fachanwendung, die in den Gesundheitsämtern betrieben werden - dort können die nächsten Aufgaben geplant werden.
 
## Gibt es PPT Vorlagen zum bearbeiten bei dem ich das eigene App Logo einbinden kann?
Wir stellen Dir gerne ein paar leicht verständliche Folien mit einem typischen Einsatzszenario für IRIS connect zur Verfügung, die Du in Deine eigene
Präsentation integrieren kannst. 

## Wo finde ich die technische Dokumentation von IRIS connect?
Hier gibt es mehrere Quellen.
* Wird im IRIS connect Konzept Dokument drauf eingegangen. Siehe Frage nach “Standardanschreiben für GAs für die Vorstellung von IRIS connect”. 
* API Dokumentation auf Github 
* Sicherheitskonzept Ordner auf Github 
 
## Muss man als App Anbieter Open Source sein oder reicht es, wenn IRIS connect selbst Open Source ist?
Nein, man muss die eigene Lösung nicht Open Source anbieten. Open Source wird aber grundsätzlich präferiert, denn durch Open Source können andere peers den 
Code anschauen und mögliche Sicherheitslücken identifizieren (Peer-Review). Viele Lösungen sind jedoch in andere proprietäre Systeme eingebunden, daher 
ist das nicht immer möglich. Nichtsdetotrotz haben wir seitens IRIS connect ein paar Regeln definiert, die vor einer Anbindung erfüllt sein müssen. Wir gehen auf 
den Aspekt im Code of Conduct ein.
 
## Sollte es eine koordinierte Kontaktaufnahme zu GAs geben oder kann das jeder App Anbieter einzeln tun?
Hinter IRIS connect gibt es kein “Vertriebskonzept” und auch keine Vertriebsorganisation, die vor Ort die GAs vom Einsatz überzeugen möchte.
IRIS connect ist Open Source, wird unentgeltlich zur Verfügung gestellt und ist einfach notwendig, um digital erfasste Kontaktdaten von einer Vielzahl
Anbieter sicher ins Gesundheitsamt zu übertragen. Sicherlich sind häufig mehrere Lösungsanbieter nebeneinander in einer Kommune aktiv - 
genau das ist die Idee hinter IRIS connect: Es müssen/können/dürfen nicht alle Betriebe innerhalb einer Region mit der gleichen Lösung arbeiten. 
Uns ist bewusst, dass viele Gesundheitsämter direkt mit den Lösungsanbietern vor Ort sprechen, die hauptsächlich in der lokalen Wirtschaft
im Einsatz sind. Hier stellen wir sehr gerne Kommunikationsmaterial zur Verfügung, damit IRIS connect einheitlich und abgestimmt vorgestellt werden kann, 
wenn die Frage nach der Datenübermittlung gestellt wird.

## Gibt es einen CSV Export aus dem IRIS Client?
Ja, IRIS connect ermöglicht zum einen eine direkte Weiterverarbeitung der ausgewählten Daten in SORMAS oder alternativ einen CSV-Export zur Weiterbearbeitung 
in beliebigen anderen IfSG Fachanwendungen. Da IRIS connect eine Open Source Lösung ist, können natürlich auch weitere direkte Integrationen neben SORMAS entstehen.

## Wie werden Menschen ohne Smartphone abgeholt?
IRIS ist nicht die Lösung zur Kontaktdatenerfassung - sondern nur der digitale, sichere Weg bereits erfasster Daten – in die Gesundheitsämter hinein.
Ob die Daten z.B. durch den Wirt eingetragen oder vom Gast per Handykamera, Webformular oder App erfasst wurden, spielt keine Rolle.

## Ist IRIS exklusiv?
Die Software wird Open Source betrieben. Die Nutzungsrechte sind ausführlich im GitHub-Repository beschrieben.

## Nachprüfungsverfahren der Luca vergabe pro Bundesland - wie kann man sich beteiligen?
Dies ist keine IRIS connect relevante Frage. Aber ganz generell gilt: IRIS connect ist keine konkurrierende Anwendung zu Luca, sondern spannt ein Dach auf, 
unter dem Lösungen aus den verschiedensten Anwendungsbereichen ihre Daten zur Verfügung stellen können.

## Wer ist die Björn Steiger Stiftung?
Die Björn Steiger Stiftung ist eine gemeinnützige Stiftung bürgerlichen Rechts - und seit Ende der 1960er unterwegs mit der Mission
“Wir retten Menschenleben”. Gestartet mit der Einführung der bundesweiten Notrufnummer 112, dem Aufstellen der orangenen Notrufsäulen über
die öffentliche Verfügbarmachung von Defibrilatoren bis hin zum aktuellen Engagement bei der digitalen Pandemiebewältigung. Weitere Informationen
finden sich hier (https://www.steiger-stiftung.de).
