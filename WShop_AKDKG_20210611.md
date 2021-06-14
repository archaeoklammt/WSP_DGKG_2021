title : Von Daten zu Geodaten und Visualisierungen mit einem Raumbezug

author : Anne Klammt

ORCID : [000-0003-3697-9241](https://orcid.org/0000-0003-3697-9241) 

date : 11/06/2021

context : Workshop des AK Digitale Kunstgeschichte zur vDHd2021, 10/06-11/06/2021 

license : [CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0/)

# Von Daten zu Geodaten und Visualsierungen mit einem Raumbezug

## Daten und Geodaten in der Wikidata

### Datenbegriff

Unter "Daten" verstehe ich an dieser Stelle, Werte bzw. Angaben wie eine Temperaturangabe, ein Name, ein Koordinatenpaar. Die Kombination von Daten und ihre semantische Verknüpfung erzeugt dann eine Information, wie "die Temperatur im Depot des Museums X am Ort XYZ". 

"Geodaten" meinen an dieser Stelle Daten, die einen Raumbezug ausdrücken. Der Raumbezug kann auf verschiedene Weise ausgedrückt werden, etwa durch einen Ortsnamen, eine postalische Adresse oder, wie es in diesem Kontext relevant ist, über Lagedaten in einem Raumbezugsystem, also etwa den Rechts- und Hochwerten, die man in der Wikipedia findet.

### Raumbezug formulieren

Geodaten können sehr oft bereits in einer Weise formuliert werden, die dem Prinzip der Triple entspricht oder eben der einfachen Syntax von Subject-Property-Object. Gezeigt wird dies am Beispiel verschiedener Angaben zum Raumbezug die für das französische Museum Réattu in der Wikidata angelegt sind.

Subjekt [Museum X] Property [liegt in] Objekt [Ort]

[Musée Réattu (Q1688538)](https://www.wikidata.org/wiki/Q1688538) + [P159](https://www.wikidata.org/wiki/Property:P159) + [Arles (Q48292)](https://www.wikidata.org/wiki/Q48292)]

---

Subjekt [Museum X] Property [hat Adresse] Objekt [Strasse Hausnummer]

[Musée Réattu (Q1688538)](https://www.wikidata.org/wiki/Q1688538) + [P6375](https://www.wikidata.org/wiki/Property:P6375) + 10, rue du Grand-Prieuré

---

Subjekt [Museum X] Property [hat Koordinaten] Objekt [Rechtswert / Hochwert]

[Musée Réattu (Q1688538)](https://www.wikidata.org/wiki/Q1688538) + [P625](https://www.wikidata.org/wiki/Property:P625) + [43°40'45.019"N / 4°37'40.382"E](https://geohack.toolforge.org/geohack.php?params=43.679172_N_4.627884_E_globe:earth&language=en)

---



### Koordinaten als Properties von Wikidata-Elementen

In der Wikidata finden sich (bezogen auf den vorliegenden thematischen Zusammenhang) insbesondere bei Institutionen - Universitäten, Forschungseinrichtungen, Archive usw. - Koordinatenpaare zur Angabe einer Mittelpunktkoordinate. Den Elementen werden diese Koordinaten über die Wikidata Eigenschaft / Property: [coordinate location (P625)](https://www.wikidata.org/wiki/Property:P625) zugeordnet.

Diese Koordinatenpaare ermöglichen die einfache Anzeige der Objekte z. B. in Google Earth, dem DARIAH-DE Geobrowser, OSM Streetmap oder auch die Erstellung interaktiver Kartierungen auf der eigenen Webseite mittels [Leaflet.js](https://leafletjs.com/).


Beispiele mit der Property aus unserem Kontext

1. Wikidata-Element [arthistoricum.net (Q708067)](https://www.wikidata.org/wiki/Q708067) mit zwei Einträgen /values entsprechend der Standorte der zwei am Fachinformationsdienst beteiligten Bibliotheken

2. Wikidata-Elemente [Deutsches Forum für Kunstgeschichte Paris (Q253771)](https://www.wikidata.org/wiki/Q253771) und [Deutsches Forum für Kunstgeschichte, Bibliothek (Q28739317)](https://www.wikidata.org/wiki/Q28739317)

Anmerkungen zum Beispiel DFK Paris 

Die Angaben zur Adresse des DFK Paris stimmen nicht mit den angegebenen Geokoordinaten überein ! In der [History des Elements (Q28739317)](https://www.wikidata.org/w/index.php?title=Q28739317&diff=prev&oldid=1438141242) kann man erkennen, dass die postalische Adresse geändert wurde, aber nicht die Koordinaten. Dabei stimmt die neue Adresse mit der schon früher angelegten [Referenz der Deutschen ISIL-Agentur und Sigelstelle](https://sigel.staatsbibliothek-berlin.de/suche.html?q=DFK%20Paris&sort=sortby%20isl%2Fsort.ascending) überein.

Offene Fragen

* Wie könnte man so vorgehen, dass die Angaben leichter zu pflegen sind? 
* Ausgehend von der Erfahrung mit den beiden Wikidata-Elementen des DFK Paris: Welche möglichen Änderungsvorschläge hätten Sie/hättest Du für das Element [arthistoricum.net (Q708067)](https://www.wikidata.org/wiki/Q708067) ?


### Normdaten verwenden, um Wikidata-Elementen einen Raumbezug zu geben 

Das Einfügen der property "coordinate location" ist immer dann ein Gewinn, wenn es kein Wikidata-Element gibt, an das sich der Raumbezug verknüpft (etwa ein Institut an dem ein Forschungsprojekt angedockt ist) oder ein anderes Verzeichnis über einen "Identifier" zu verknüpfen ist, an dem die Lage verzeichnet ist. Koordinaten anzulegen ist auch dann sinnvoll, wenn sie nicht in der für einen bestimmten Use Case nötigen Qualität eingetragen sind (es gibt etwa keine Koordinaten für die einzelnen Institute einer Universität - Achtung, eben diese Angaben können jedoch auch schnell veralten).

Vielfach aber gibt es kontrollierte Datensammlungen und Vokabulare, bzw. Gazetteer, die bereits den Lagebezug vorhalten. Diese können dabei entweder als Identifier des Wikidata-Elements angelegt werden, also vergleichbar mit der GND Nummer einer Person, oder als Referenz für den Eintrag der Koordinaten

Beispiele 

1. [Geonames](https://www.geonames.org/) als Identifier des Wikidata Element "Hamburg ([Q1055](https://www.wikidata.org/wiki/Q1055))" 
2. [ISIL](https://sigel.staatsbibliothek-berlin.de/suche/?isil=DE-Y7) als Identifier des Wikidata-Element"[Deutsches Forum für Kunstgeschichte, Bibliothek (Q28739317)](https://www.wikidata.org/wiki/Q28739317)" und dort auch als Referenz (Belegstelle) für den Eintrag der Koordinaten (coordinate location (P625)).

Frage zum Beispiel DFK Paris 

Was könnte der Vorteil sein, so wie am Beispiel 2 vorzugehen? Was ist der Nachteil? 

## Geodaten der Wikidata nutzen

### Geodaten mit Koordinaten über den Query-Service beziehen
Die Geodaten (gemeint an dieser Stelle sind solche Daten mit Geokoordinaten) können über den Query-Service abgefragt und dort entweder direkt visualisiert werden oder über den Export ausgelesen und in ein weiteres Tool überführt werden, also etwa ein Export im Format csv und die Verwendung des Files in QGIS.

Die Herausforderung liegt in der Formulierung der Abfrage, und da es sich bei Wikidata nicht um einen Thesaurus handelt und auch nicht um eine Ontologie, wird man oft mehrere Abfragen oder auch recht komplexe Abfragen mit zahlreichen Optionen (in SPARQL: OPTIONAL) stellen müssen, um ein Themenfeld zu erschließen. 

So könnte es Sinn machen, zum einen nach Dingen, Personen oder Sachverhalten (items) zu suchen, für die eine solche Property eingetragen ist, die Koordinaten anbietet, zum anderen aber nach solchen, denen Identifier zugeordnet wurden, die wiederum auf Verzeichnisse verweisen, in denen Lageangaben gepflegt werden. 

Beispiel

1. Abfrage Lagekoordinaten der Institutionen, an denen Mitglieder des Arbeitskreises Digitale Kunstgeschichte beschäftigt sind oder waren-> [https://w.wiki/3TX2](https://w.wiki/3TX2). 

---

SPARQL Abfrage

\# defaultView:Map

SELECT ?MitgliedLabel ?employerLabel ?coord WHERE {
  ?Mitglied wdt:P463 wd:Q42738658;
  wdt:P108 ?employer.
  
  ?employer wdt:P625 ?coord

  SERVICE wikibase:label { bd:serviceParam wikibase:language "en". }
}




Übersetzt steht dort: *"Suche nach Wikidata-Elementen, die die Eigenschaft haben, ein Mitglied des Arbeitskreises Digitale Kunstgeschichte zu sein, und für die es zudem einen (oder mehrere) Einträge mit der Eigenschaft Employer gibt, für die also Arbeitgeber angegeben sind. Zeige mir von diesen Arbeitgebern die Koordinaten an. Gebe mir dabei aus, den Namen des Mitglieds (?MitgliedLabel),den Namen des Arbeitgebers (?employerLabel) und schließlich die Koordinaten (?coord). Die Ansicht der Ergebnisse soll als Karte angezeigt werden"*


---


Ergebnis: 09/06/2021, 13:03

| MitgliedLabel	| employerLabel	| coord |
| --- | -- | --|
|Holger Simon |	University of Cologne	| Point(6.928611111 50.928055555) |
|Lisa Dieckmann	| University of Cologne	| Point(6.928611111 50.928055555) |
|Hubertus Kohle	| Ludwig Maximilian University of Munich	| Point(11.580277777 48.150833333) |
|Stephan Hoppe	| Ludwig Maximilian University of Munich	| Point(11.580277777 48.150833333) |
|Thorsten Wuebbena |	Heidelberg University	| Point(8.706388888 49.410277777) |
|Georg Schelbert | 	Humboldt University of Berlin	| Point(13.393333333 52.518055555) |
|Michael Müller	| Humboldt University of Berlin	| Point(13.393333333 52.518055555) |
|Michael Müller| 	Freie Universität Berlin	| Point(13.290555555 52.453055555) |
|Anna Schreurs	| University of Freiburg	| Point(7.846944444 47.994166666) |
|Ute Verstegen	| University of Marburg	| Point(8.773611111 50.810833333) |
|Thorsten Wuebbena	| Deutsches Forum für Kunstgeschichte	| Point(2.335739722 48.867) |
|Anne Klammt	| Deutsches Forum für Kunstgeschichte	| Point(2.335739722 48.867) |
|Ralph Knickmeier	| Belvedere	| Point(16.38049 48.19139) |
|Georg Schelbert	| Bibliotheca Hertziana – Max Planck Institute of Art History	| Point(12.48414 41.90534) |
|Martin Raspe	| Bibliotheca Hertziana – Max Planck Institute of Art History	| Point(12.48414 41.90534) |
|Fabian Cremer	| Göttingen State and University Library	| Point(9.93639 51.5397) |
|Thorsten Wuebbena	| Saarland University	| Point(7.04166667 49.25555556) |
|Georg Schelbert	| University of Trier	| Point(6.687777777 49.7475) |
|Anna Schreurs	| Kunsthistorisches Institut in Florenz	| Point(11.264 43.7772) |
|Maria Effinger	| University Library Heidelberg	| Point(8.70583 49.4097) |
|Anna Schreurs	| Institute of Art History, Goethe-University Frankfurt	| Point(8.652256388 50.1184875) |
|Thorsten Wuebbena	| Institute of Art History, Goethe-University Frankfurt	| Point(8.652256388 50.1184875) |

Beobachtung

Ist dieses Ergebnis vollständig? Es macht einen vollständigen Eindruck, aber bei genauerem Hinschauen zeigt sich, dass z. B. mein Wikidata-Element ([Q81833150](https://www.wikidata.org/wiki/Q81833150)) nur einmal vertreten ist, obwohl es noch zwei weitere Einträge der Eigenschaft [employer (P108)](https://www.wikidata.org/wiki/Property:P108) aufweist. Zustande gekommen ist dies, weil der von der Abfrage erfasste Eintrag als "[preferred Rank](https://www.wikidata.org/wiki/Q71533031)" ausgezeichnet war, um ihn als aktuell von den anderen Einträgen zu unterscheiden. Nach dem Herausnehmen des Ranks und einem erneuten Durchführen der Anfrage erscheinen nun auch die Einträge. 

Bereits die Prüfung dieser kleinen Anzahl von Ergebnissen ist nicht trivial und die Unstimmigkeit bzw. die gegenüber der ursprünglichen Aussage *"an denen Mitglieder des Arbeitskreises Digitale Kunstgeschichte beschäftigt sind oder waren"* auftretende Divergenz, nicht unmittelbar zu erkennen, ohne Vorwissen. 


### Geodaten aus der Abfrage in QGIS und Google Earth anzeigen

Der Query-Service bietet verschiedene Formate zum Export an, die die Nutzung bzw., weitere Bearbeitung der Ergebnisse mit vielen verschiedenen Programmen und Anwendungen ermöglicht (Excel, Openrefine, Recogito usw.). So kann etwa der Export im Format CSV (*comma separted values*) nach einer leichten Aufbereitung in QGIS genutzt werden. Diese Aufbereitung betrifft die Aufgliederung der Rechts- und Hochwerte in zwei Spalten und das Einfügen einer ID.

Beispiel Überarbeitung 

| ID | MitgliedLabel	| employerLabel	| Typ | XCOOR | YCOOR |
| --- | --- | ---| ---| ---| ---|
| 43 |Holger Simon |	University of Cologne	| Point| 6.928611111 | 50.928055555 |
| 44 |Lisa Dieckmann	| University of Cologne	| Point | 6.928611111 | 50.928055555 |
| 45 |Hubertus Kohle	| Ludwig Maximilian University of Munich	| Point | 11.580277777 | 48.150833333 |

Raumbezugssystem [EPSG 4326](https://epsg.org/search/by-name?sessionkey=kg8npac56o&searchedTerms=4326) WGS84.

Für die Nutzung in Google Earth müssen die Daten in das Format KML überführt werden ([Keyhole Markup Language in der Wikipedia](https://de.wikipedia.org/wiki/Keyhole_Markup_Language)).

Kurzer Workflow

* Die wie oben vorbereitete csv-Datei **(dabei ist das ID Feld nicht notwendig)* in einen der verschiedenen Konverter in KML formatieren. Wichtige Schritte sind hierbei die Angabe, in welcher Spalte/in welchem Feld die Rechtswerte (X Koordinate) und in welchem die Hochwerte (Y Koordinate) sind. *Kleine Hilfe: Orte in Deutschland haben einen Rechtswert, der immer deutlich niedriger ausfällt als der Hochwert.*

* Anschließend kann das KML-Layer direkt in Google Earth geöffnet werden (lokale Installation vorausgesetzt).

  * Hier verwendet für Beispieldaten nach der oben gezeigten Aufbereitung
[ConvertCSV (Convert CSV to KML)](https://www.convertcsv.com/csv-to-kml.htm) mit den Eistellungen Name Field "2", Description Field "3", Latitude Field "6", Longitude Field "5". Die Zahlen entsprechen dabei der Anzahl der Spalten/Felder von links nach rechts.

---

Ausschnitt aus der KML-Datei

\<?xml version="1.0" encoding="UTF-8"?>

\<kml xmlns="http://earth.google.com/kml/2.0">

\<Document>

\<Placemark>

\<name>1\</name>

\<description>Holger Simon University of Cologne\</description>

\<Point>\<coordinates>50.928055555,6.928611111,0\</coordinates>\</Point>

\</Placemark>

\<Placemark>

\<name>2\</name>

\<description>Lisa Dieckmann University of Cologne\</description>

\<Point>\<coordinates>50.928055555,6.928611111,0\</coordinates>\</Point>

\</Placemark>

...

\</Document>

\</kml>

---

## Ausblick oder Geodaten für die Wikidata-Abfrage über andere Datenservices beziehen

Im Abschnitt zur Frage, wie der Raumbezug in der Wikidata angelegt werden kann, wurde am Beispiel des Eintrags zur Bibliothek des DFK Paris problematisiert, dass Normdaten aus spezifischen Bereichen ggfs. zu einer besseren oder zumindest kontrollierten Qualität der Einträge führen können.
 
Gezeigt wurde hier als Gazetteer bereits Geonames als Gazetteer für geographische Objekte. Dies kann eine interessante Ressource sein, wenn es wichtig ist auch, die administrativen Bezüge einzubeziehen (Verteilung von Objekten pro Landkreis, Bezirk, Bundesland etc.). Die reinen Geokoordinaten "wissen" dies nicht über sich.

Für eine Vielzahl der wissenschaftlichen Einrichtungen, Museen und Archive, die im Zusammenhang mit den Personen aus unserer Abfrage stehen, bietet die GND interessante Daten, die wiederum semantisch reich sind, dafür ist oft die Präzision der Koordinaten weniger genau. Hier ist je nach Fragestellung zu entschieden, wie relevant die Lagegenauigkeit bzw. die Granularität der Geodaten ist.

Steht der Aufbau einer eigenen Sammlung von Orten bzw. Objekten mit Raumbezug oder aber auch die Extraktion von Ortsnamen aus Texten oder historischen Karten im Mittelpunkt seines Projekts empfiehlt es sich von Beginn an in der Logik von Gazettern zu arbeiten. Ein sehr niedrigschwelliges, dabei aber ausgereiftes Tool hierfür ist [Recogito](https://recogito.pelagios.org/).





