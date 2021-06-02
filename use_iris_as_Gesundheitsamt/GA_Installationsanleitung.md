# Anleitung für die Installation und Einrichtung des IRIS Clients
Eine Anleitung für die Installation und Einrichtung des IRIS-Client befindet sich direkt im [zugehörigen Repository](https://github.com/iris-connect/iris-client/blob/develop/infrastructure/deployment/docs/Installation.md).

## Zertifikate für den Client
### Wofür werden die Zertifikate benötigt?
Die Zertifikate werden benötigt, um möglichst sicherzustellen, dass Anfragen beim IRIS-Gateway auch wirklich von einer autorisierten Stelle (Gesundheitsamt) kommen.
Dies entspricht in etwa dem Verfahren für die Deutsche Einreise Anmeldung (DEA), die über die Bundesdruckerei als Webanwendung entwickelt und ausgerollt wurde. 
Für die Anbindung an IRIS benötigt ein GA vier Zertifikate. Deren Funktion wird weiter unten beschrieben. 

### Welche Zertifikate gibt es?
Für die Anbindung an IRIS benötigt ein GA vier Schlüsselpaare bzw. Zertifikate, von denen zwei durch die 
Bundesdruckerei (BDr) bzw. deren Vertrauensdiensteanbieter D-Trust herausgegeben werden. 
Die anderen werden im Anschluss vom GA oder dessen IT-Dienstleister, je nachdem, wer den IRIS-Client betreibt, 
ohne Zutun der Bundesdruckerei erstellt.

1. TLS-Zertifikat für IRIS-Client-Backend im GA  
   * Anwendungsfall: Identität des GA im Internet. Insbesondere TLS-Server-Authentication für eingehende Verbindungen aus Webbrowsern oder mobilen Apps über den IRIS Public Proxy.
   * Herausgabe: BDr/D-Trust
2. Signaturzertifikat für Vertreter:in des GA  
   * Anwendungsfall: Identität des GA im EPS-Netzwerk. Insbesondere Signatur von Service-Directory-Einträgen und mTLS-Zertifikaten (3) sowie E2E-Zertifikaten (4) im GA 
   * Herausgabe: BDr/D-Trust
3. mTLS-Zertifikat für EPS-Server im GA  
   * Anwendungsfall: Absicherung der Kommunikation zwischen EPS-Servern.
   * Herausgabe: GA
4. E2E-Zertifikate für IRIS-Client-Backend im GA  
   * Anwendungsfall: Insbesondere zur Umsetzung der DSK-Anforderungen an Betreiber von
     digitaler Kontaktdatenerfassung, wonach zusätzlich zur Transportverschlüsselung (TLS)
     eine zweite Verschlüsselungsschicht auf Anwendungsebene (Inhaltsverschlüsselung)
     umzusetzen ist.
   * Herausgabe: GA


### Wie bekomme ich die Zertifikate von der Bundesdruckerei?
Für die Anbindung an IRIS auf Landesebene ist die Mitwirkung einer Landesbehörde nötig. 
Diese tritt im Rahmen der Identitätsprüfung gegenüber der Bundesdruckerei stellvertretend für alle GÄ des Landes auf. 
Die GÄ brauchen den Prüfungsprozess entsprechend nicht separat zu durchlaufen.

Hier der Ablauf, um die ersten beiden Zertifikate zu bekommen:
1. Behörde stellt den GÄ ggf. eine (Sub-)Domain bereit, die im Kontext von IRIS genutzt werden kann.
1. Vertreter:in der Behörde nennt der BDr auf sicherem Weg eine Vertreter:in je GA.
1. BDr prüft Identität von Vertreter:in der Behörde und deren Vertretungsberechtigung.
1. BDr übermittelt Zugangsdaten zum Antragsportal je GA auf sicherem Wege an die Behörde, die sie an die Vertreter der GÄ weiterleitet.
1. GA erstellt kryptographische Schlüssel und stellt für diese Zertifikatsanfragen sicher im Antragsportal ein.
1. Nach Prüfung und Domainvalidierung der (Sub-)Domain des GA stellt die BDr die Zertifikate bereit.
1. GA kann die Zertifikate & Domain nun im IRIS-Client gemäß Anleitung konfigurieren.
1. GA erstellt weitere Zertifikate ohne Zutun der BDr gemäß Anleitung.

> Hinweis:  
> In Kürze folgen hier weiteren Ausführungen und technische Details.
> Dazu werden gerade letzte Unschärfen mit der Bundesdruckerei geklärt.
