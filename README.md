## Ich bin vom Gesundheitsamt, wo muss ich hin?
Hier finden Sie die [Installationsanleitung](./use_iris_as_Gesundheitsamt/GA_Installationsanleitung.md), hier ein [Video der Installation](https://www.youtube.com/watch?v=JI8rbT1gNgs).
Die [Bedienungsanleitung für Mitarbeitende im Gesundheitsamt](https://uploads-ssl.webflow.com/609e55b08d9aef989925de0d/60c87415c75c1da665d3f7aa_IRIS%20Benutzeranleitung%20v.1.pdf) ist auf dem Internetauftritt [iris-connect.de](https://iris-connect.de) verfügbar.

## Übersicht der Dokumentationen
### Einführung - Dies ist IRIS connect
|     | Name und Link             | Sprache    | Beschreibung                                                      |
| --- | ------------------------- | ---------- | ----------------------------------------------------------------- |
| 1.1 | [About](https://github.com/iris-connect/iris-documentation/blob/main/README.md#about-this-project) | Eng | |
| 1.2 | [Funktionsweise](https://github.com/iris-connect/iris-documentation/blob/handbook-chapters/use_iris_as_Gesundheitsamt/handbuch/03_IRIS_Funktionsweise.md)|Deu| |
| 1.2.1| [Gästelisten](https://github.com/iris-connect/iris-documentation/blob/handbook-chapters/use_iris_as_Gesundheitsamt/handbuch/03b_IRIS_Ereignisverfolgung.md)|Deu|<B>Ereignisfall-Nachverfolgung</B>|
| 1.2.2| [Kontakttagebücher](https://github.com/iris-connect/iris-documentation/blob/handbook-chapters/use_iris_as_Gesundheitsamt/handbuch/03a_IRIS_Indexfall.md)|Deu|<B>Indexfall-Nachverfolgung</B>|
|1.3	| [Technische Beschreibungen](https://github.com/iris-connect/iris-documentation/blob/handbook-chapters/use_iris_as_Gesundheitsamt/handbuch/05_IRIS_Technischer_Betrieb.md)| Deu ||
|1.3.1| [Architektur (inkl. Client)](https://github.com/iris-connect/iris-client/blob/develop/infrastructure/deployment/docs/Architektur.md) |Eng||
|1.3.2| [Gateway](https://github.com/iris-connect/iris-gateway/blob/develop/README.adoc)|Eng||
|1.3.3| [EPS](https://github.com/iris-connect/eps/blob/master/README.md)|Eng||
|1.3.4| [IT- Sicherheitskonzept](https://github.com/iris-connect/iris-security/blob/master/Doc%20Sicherheitskonzept/Sicherheitskonzept.md)|Deu||
|1.3.5| Datenschutzkonzept
|1.4  |	[Changelog](https://github.com/iris-connect/iris-client/blob/develop/CHANGELOG.md)|||
### Für Gesundheitsämter
|     | Name und Link             | Sprache    | Beschreibung                                                      |
| --- | ------------------------- | ---------- | ----------------------------------------------------------------- |
|2.1  | [Prozessbeschreibung Anbindung](https://github.com/iris-connect/iris-documentation/blob/main/use_iris_as_Gesundheitsamt/GA_Installationsanleitung.md)|Deu||
|2.2  |	[Installationsanleitung Client](https://github.com/iris-connect/iris-client/blob/develop/infrastructure/deployment/docs/Installation.md)|Deu||
|2.2.1|	[Docker Installation](https://github.com/iris-connect/iris-client/blob/develop/infrastructure/deployment/docs/Installation-Docker-Compose.md)|Deu|1. Schritt (Docker wird empfohlen)|
|2.2.2|	[Standalone Installation](#)|Deu|alternativer 1. Schritt ohne Docker|
|2.2.3| Proxy|Deu|2. Schritt|
|2.2.4| [Zertifikatsausstellung](https://github.com/iris-connect/iris-client/blob/develop/infrastructure/deployment/docs/Certificate-Process-Staging.md)|Deu|3. Schritt|
|2.3  |	[Bedienungsanleitung für Endnutzer](https://docs.google.com/document/d/1--VHwB3q_Ci1b_LYtAhrvrWx5WNDSbpWWH_YrNIF7JM/edit#heading=h.u4qwc9teio72)|Deu|Dies ist die <B>Anleitung für die Mitarbeiter</B>, die die Kontaktverfolgung durchführen.|
|2.4  |	[FAQ Gesundheitsämter](https://github.com/iris-connect/iris-documentation/blob/main/use_iris_as_Gesundheitsamt/FAQ_GA_IT-Verantwortliche.md)|Deu||
### Für Kontakterfassungs-Apps
|     | Name und Link             | Sprache    | Beschreibung                                                      |
| --- | ------------------------- | ---------- | ----------------------------------------------------------------- |
|3.1	|	[Prozessbeschreibung Anbindung (technischer Teil)](https://github.com/iris-connect/iris-documentation/blob/main/connect_your_app_to_IRIS/technical_details/app_onboarding.md)|Eng||
|3.2	| [Term and Conditions bzw. AGB](https://github.com/iris-connect/iris-documentation/blob/main/connect_your_app_to_IRIS/Connect_App_to_IRIS_administration.md) | Eng | noch nachzuliefernde AGB
|3.3  | [Code of Conduct for Apps](https://github.com/iris-connect/iris-documentation/blob/main/connect_your_app_to_IRIS/Code_of_Conduct_Apps_for_IRIS_draft.md)|Eng|1. Schritt|
|3.4	|	Zertifikatsausstellung||2.Schritt|
|3.5  | EPS||3. Schritt|
|3.6	|	Schnittstellenbeschreibung||4. Schritt|		
|3.7	|	[FAQ Kontakterfassungs-Apps](https://github.com/iris-connect/iris-documentation/blob/main/connect_your_app_to_IRIS/apps_FAQ.md)|||
### Community and Open Development
|     | Name und Link             | Sprache    | Beschreibung                                                      |
| --- | ------------------------- | ---------- | ----------------------------------------------------------------- |
|4.1	|	[Contribute to IRIS connect](https://github.com/iris-connect/iris-client#participation)|Eng||
|4.2	|	[Contributor License Agreement](https://github.com/iris-connect/iris-client/tree/develop/.clas)|Eng||
|4.3	|	[Code of Conduct](https://github.com/iris-connect/iris-documentation/blob/main/CODE_OF_CONDUCT_community.md)|Eng||



## About this Project

This project aims to enable public health offices to request and receive data for contact tracing, provived by individuals who might be diagnosed with a communicable disease or provided by localities, an infected person has visited.

During the COVID-19 pandemic several applications have been developed that help organising this data for individuals or localities. What has been missing is a standardized way for public health officials to access this data, across the many different solutions in place optimized for their individual use case, for the specific hygiene concept.

It is made with a lot of enthusiasm and dedicated to the general public, as we hope it will allow for more social interaction, and in case it is used, to speed up and facilitate processes for contact tracing.

Everything presented here is part of a living open development process. We are agile and very open for reported issues. Contributors are always welcome!

## Who We Are

IRIS is an initiative of the [Innovationsverbund Öffentliche Gesundheit](https://inoeg.de) (Innovation Association Public Health), a network of people who proactively work on interoperability within the public health service. The current focus is Germany but of course we are open for international collaboration.

Many individuals with many different backgrounds are contributing (IT, public health, communications, design, legal). A lot of work is done on a volunteer or pro bono basis, but of course a project of this magnitude cannot be developed and maintained only on free time alone.

The project is funded mainly by the [Björn Steiger Foundation](https://steiger-stiftung.de) (Thank You!) who also is responsible for the procedural operation.

## Credits

Many people and organisations have been and are contributing to this project. Many people from IT departments and public health offices give their skills and knowledge. Also many other skills are required: design, communications, legal issues, data privacy to only name a few.

## Code of Conduct

Our [Code of Conduct](./CODE_OF_CONDUCT_community.md) defines standards for how to engage within our community.

## Working Language

Falls Sie Dinge auf Deutsch beitragen möchten, können Sie das gerne machen. Eventuell werden Dinge dann auch von anderen Menschen entsprechend übersetzt.

Our working language is english. Since the product has been initially developed with the German public health service as first adopter, some documents are also in German. We are working on providing a more internationally suited version as well.


## Our Documentation

This repository contains the developer documentation and related content. The user documentation is currently produced and will be published soon.

### Project Scope

Target is to provide a software that enables public health services to request and access the data they need at the time of need. Of course within the valid legal frameworks.

### Technical Documentation

The technical documentation is split in
* [setup/installation of the client for public health offices](https://github.com/iris-connect/iris-client/blob/develop/infrastructure/deployment/Installation.md)
* [connecting an application for contact data collection to IRIS](/connect_your_app_to_IRIS) 
* IT-Security documentation (to be published soon)

## Repositories

| Repository                | Description                                                                  |
| ------------------------- | ---------------------------------------------------------------------------- |
| [eps](https://github.com/iris-connect/eps)  | The endpoint sever modules                                 |
| [iris-client](https://github.com/iris-connect/iris-client)  | The client for public health agencies     |
| [iris-documentation](https://github.com/iris-connect/iris-documentation)  | The place to collect documentation. Some documents are also inside the respective repositories. |



## Licensing

The code is released under AGPL 3.0, the documentation under CC BY-SA 4.0

## How to Contribute

For now, please refer to
https://github.com/iris-connect/iris-client/blob/develop/README.adoc
