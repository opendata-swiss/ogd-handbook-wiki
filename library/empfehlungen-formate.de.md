Title: Empfehlungen für OGD Formate
Category: Library
Template: document
Tags: publish
Date: 2015-12-09
Slug: empfehlungen-formate
Authors:
Summary:
Lang: de
Hidden: yes
toc_run: true
Link_PDF: https://bar-files.opendata.swiss/owncloud/index.php/s/8gexg7qtjhiLlZd
Link_DOC: https://bar-files.opendata.swiss/owncloud/index.php/s/9D3VHdnkS2pm1JJ


## Einleitung

Um das Potential von offenen Behördendaten nutzen zu können, müssen
diese in Formaten[^1] bereitgestellt werden, welche möglichst einfach zu
verwenden sind. Unter offenen Behördendaten versteht man Datensätze, die
kostenfrei und im Idealfall in maschinenlesbarer Form zur
Sekundärnutzung allen Interessierten zur Verfügung stehen<sup>[^2](#footnote-2)</sup>. Das
vorliegende Dokument definiert Kriterien für die Publikation von
Datensätzen im OGD Portal und gibt Empfehlungen zu spezifischen Formaten
und Schnittstellen ab.

Die OGD-Strategie Schweiz definiert die drei Ziele „Freigabe von
Behördendaten“, „Koordinierte Publikation und Bereitstellung der
Behördendaten“ und „Etablierung einer Open-Data-Kultur“ (siehe [\#1, OGD
Strategie Schweiz 2014 – 2018](#referenzen)). Für die zu verwendenden
Formate werden im Ziel „Freigabe von Behördendaten“ klare Vorgaben
gemacht:

> „Der Bund stellt der Öffentlichkeit seine für OGD geeigneten Daten in
> *maschinenlesbaren* und *offenen Formaten* zur freien Weiterverwendung
> zur Verfügung.“ (\#1, S. 3499)

Diese Kriterien finden ihre Entsprechung im Grundsatz 2 „Offene und
wiederverwendbare Behördendaten“:

> „Die Daten werden in *maschinenlesbarer Form* angeboten, verständlich
> und zweckmässig beschrieben und dauerhaft zur Verfügung gestellt. Es
> sollen möglichst *offene Formate* angewandt werden.“ (\#1, S. 3502)

Im vorliegenden Dokument werden die Kriterien „maschinenlesbar“ und
„offen“ genauer beschrieben sowie die Bedeutung von "verständlich und
zweckmässig beschrieben" erläutert. Davon abgeleitet werden Empfehlungen
zur Publikation von Datensätzen abgegeben.

## Ziel des Dokuments & Zielpublikum

**Ziel des Dokuments**

Dieses Dokument beschreibt die Kriterien für Formate und
Austauschformen, in denen die Daten auf der OGD-Plattform zugänglich
sein sollen, und gibt Empfehlungen bezüglich der zu verwendenden Formate
ab. Die Liste der empfohlenen Formate ist nicht abschliessend. Es gilt
der Grundsatz, dass eine Datenpublikation in irgendeinem Format
wünschenswerter ist als keine Publikation.

**Zielpublikum**

Das Dokument richtet sich an Datenproduzenten und Datenlieferanten bzw.
die Institutionen, die Daten als OGD zur Verfügung stellen wollen.

## Grundlagen & Auswahlkriterien

Üblicherweise wird zur Illustration in der Diskussion um *Open Data* und
*Linked Data* auf das Fünf-Sterne-Modell von Tim Berners-Lee verwiesen
(siehe [\#4, Berners Lee, Tim, Linked Data](#referenzen)). Gemäss diesem
Modell lassen sich *Open Data* in fünf Stufen unterteilen, wobei die
ersten drei Stufen im Wesentlichen *Open Data* und die zwei letzten
*Linked Open Data* beschreiben. Das Sterne-Modell hat aber Schwächen, so
sind darin beispielsweise Webservices oder Application Programming
Interfaces (APIs) nur ungenügend abgedeckt.

Die OGD Strategie Schweiz konzentriert sich zurzeit darauf, die
Kategorie ★★★ zu erreichen, d.h. die Publikation der Daten in offenen
Formaten sicherzustellen.

Datensätze, die nicht der Kategorie ★★★ entsprechen, sollen dennoch auf
dem OGD Portal publiziert werden können. Das OGD-Portal wird mit den
entsprechenden Datenlieferanten Migrationspläne erarbeiten, um
langfristig die Kategorie ★★★ zu erreichen.

<pre>
  ★       Datenpublikation mit offener Lizenz in irgendeinem Format
  ------- ------------------------------------------------------------------------------------
  ★★      Datenpublikation in einem strukturierten Format (bspw. Excel statt Tabelle in PDF)
  ★★★     Datenpublikation in einem offenen Format (bspw. CSV statt Excel)
  ★★★★    Verwendung von eindeutigen Identifikatoren (URI) für Entitäten
  ★★★★★   Verlinkung der publizierten Daten mit anderen Daten, um Kontext zu schaffen
</pre>

Tabelle 1: Aus [\#2, Open Government Data – Grundlagenstudie Schweiz, S.
86](#referenzen); [\#5, 5 ★ Open Data (Webseite)](#referenzen)

Am wichtigsten ist, dass die Datensätze mit offener Lizenz publiziert
werden. Für verschiedene Nutzer können hingegen verschiedene Formate
angeboten werden, um den spezifischen Anforderungen der Nutzer gerecht
zu werden.

Die zentralen Kriterien für die Datenpublikation im OGD-Portal sind
Maschinenlesbarkeit und Offenheit (siehe [\#1 OGD Strategie
Schweiz](#referenzen)). Diese Kriterien Maschinenlesbarkeit und
Offenheit sind im Folgenden rot gekennzeichnet.

1)  **Maschinenlesbarkeit**

  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Maschinenlesbarkeit                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           Das Format und die enthaltenen Daten können von einem Programm automatisiert verarbeitet werden.
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- --------------------------------------------------------------------------------------------------
  "Maschinenlesbar ist ein [...] Format, das so strukturiert ist, dass Softwareanwendungen konkrete Daten, einschließlich einzelner Sachverhaltsdarstellungen und deren interner Struktur, leicht identifizieren, erkennen und extrahieren können"<sup>[^3](#footnote-3)</sup>.

  Mit dieser Definition ist beispielsweise eine Textdatei erst dann maschinenlesbar, wenn die darin enthaltenen Daten so strukturiert dargestellt sind, dass sie mit einem passenden Algorithmus (Programm) korrekt interpretiert und verarbeitet werden können. Ein (X)HTML-Text (eine Webseite) ist demnach nicht maschinenlesbar - ein Browser kann die Inhalte nur für Menschen lesbar auf dem Bildschirm darstellen. Erst wenn die Inhalte der Webseite semantisch strukturiert ausgezeichnet werden (z.B. unter Verwendung des Vokabulars schema.org), können die Inhalte von einem Programm als Datenstrukturen erkannt und entsprechend verarbeitet werden. Ausserdem ist bei textbasierten Formaten eine standardisierte Zeichenkodierung notwendig (wenn möglich UTF-8), um auch spezielle Zeichen (z.B. Umlaute) korrekt interpretieren zu können.

  Um einen passenden Algorithmus zur Verarbeitung der strukturierten Daten programmieren zu können, ist das maschinenlesbare Format noch nicht ausreichend. Die Daten müssen zusätzlich "verständlich und zweckmässig beschrieben" sein. Falls die Struktur der Daten einem Standard folgt, genügt die Angabe des betreffenden Standards (z.B. schema.org). Andernfalls muss die Beschreibung der Datenstruktur in die Metadaten integriert werden.
  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

1)  **Offenheit**<sup>[^4](#footnote-4)</sup>

  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Offenheit                                                                                                                                                                                                                                                                                                           Die Spezifikation des Formats ist offen gelegt und öffentlich zugänglich.
  ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ---------------------------------------------------------------------------
  "Offen ist ein Dateiformat, das plattformunabhängig ist und der Öffentlichkeit ohne Einschränkungen, die der Weiterverwendung von Dokumenten hinderlich wären, zugänglich gemacht wird"<sup>[^5](#footnote-5)</sup>.

  Die Offenheit bzw. die Zugänglichkeit der Spezifikation ist für die lückenlose Interpretierbarkeit der durch das Format kodierten Information entscheidend. Dazu gehört auch, dass der Standard verständlich, überschaubar und eindeutig sein soll; dass dieser Standard lizenzfrei ist und weit verbreitet ist.\
  Dieses Kriterium muss erfüllt sein, damit ein Format als offen gelten kann.
  -----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Beide Kriterien Maschinenlesbarkeit und Offenheit weisen mehrere
Dimensionen auf, die im Folgenden beschrieben werden. Die nachfolgenden,
blau gekennzeichneten Dimensionen, sollen von den Datenlieferanten bei
der Auswahl geeigneter Formate, bzw. Austauschformen für ihre Datensätze
mitberücksichtigt werden.

  Standard                                                                                                                                                                                                                                                                               Das Format wird durch ein Standardgremium periodisch überprüft und aktualisiert (international, national).
  -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ------------------------------------------------------------------------------------------------------------
  Die Standards von (inter-)nationalen Organisationen sind langlebiger und weniger revisionsanfällig, verleihen einem Format also Stabilität. Ein Standardgremium ist grundsätzlich unabhängiger und glaubwürdiger als eine einzelne Firma, welche die Rechte an einem Format besitzt.

  Lizenzfrei                                                                                                                                                                        Formate sind nicht durch auferlegte Lizenzen in der Herstellung oder Benutzung limitiert.
  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- -------------------------------------------------------------------------------------------
  Verhinderung einer Herstellerabhängigkeit. Verminderung bzw. Ausschaltung des potentiellen Risikos, dass der Lizenzinhaber jederzeit Änderungen vornehmen und durchsetzen kann.

  Verbreitung                                                                                                                                                                                                                                                                                                                                                                 Das Format ist weit verbreitet.
  --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ---------------------------------
  Grosse Verbreitung bedeutet eine zum heutigen Zeitpunkt abschätzbare relativ grosse Benutzerzahl wie auch eine gewisse Diversität der Benutzer, eine grosse Anzahl existierender Dateien im entsprechenden Format, Unterstützung des Formats durch viele voneinander unabhängige Applikationen und Programmbibliotheken. Ebenso ist die geografische Verbreitung gemeint.

## Anwendungsfälle und Formate

Je nach Anwendungsfall können offene Daten ganz unterschiedliche Formate
aufweisen. Häufig werden die Daten in Tabellenform vorliegen. Aber auch
Bilder, Tonaufnahmen oder Videos können Datensätze oder Bestandteile von
Datensätzen darstellen. Entsprechend gross ist die Vielfalt von
Formaten, in denen Daten auf dem OGD Portal veröffentlicht werden
können.

Die folgende Tabelle listet die wichtigsten, für die Publikation auf dem
OGD Portal in Frage kommenden offenen Formate zusammen mit dem Verweis
auf den jeweiligen Standard auf.

  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  **Anwendungsfälle und Datenformate**           **Verweis auf Standard / Quasi-Standard** (wenn verfügbar)
  ---------------------------------------------- ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  **Strukturierte Daten **

  Comma Separated Values (CSV)                   [RFC 4180](https://tools.ietf.org/html/rfc4180)

  JavaScript Object Notation (JSON)              [RFC 4627](http://tools.ietf.org/html/rfc4627)

  Extensible Markup Language (XML)               [W3C REC](http://www.w3.org/TR/2008/REC-xml-20081126/)

  Resource Description Framework (RDF)           [W3C REC](http://www.w3.org/standards/techs/rdf#w3c_all)

  Office Open XML Spreadsheet (XLSX)             [ISO/IEC 29500](http://www.iso.org/iso/catalogue_detail?csnumber=51463)

  Open Document Spreadsheet (ODS)                [ISO/IEC 26300-1:2015](http://www.iso.org/iso/home/store/catalogue_ics/catalogue_detail_ics.htm?csnumber=66363)

  **Textdokumente / Berichte**

  Text (TXT)                                     ISO Latin-1 ([ISO 8859-1](http://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.htm?csnumber=28245)) und\
                                                 ISO Latin-9 ([ISO 8859-15](http://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.htm?csnumber=29505))

                                                 Universal Coded Character Set (UCS) ([ISO 10646](http://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.htm?csnumber=63182))

                                                 US-ASCII (ANSI X3.4-1986, bzw. ISO/IEC 646-US oder ISO/IEC 646:1991-IRV): [ISO/IEC 646:1991 ](http://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.htm?csnumber=4777)

  Extensible Hypertext Markup Language (XHTML)   [W3C REC](http://www.w3.org/TR/2001/REC-xhtml11-20010531/)

  Portable Document Format (PDF)                 [ISO 32000-1:2008](http://www.iso.org/iso/catalogue_detail.htm?csnumber=51502) (nur PDF 1.7), [ISO 19005](http://www.iso.org/iso/catalogue_detail?csnumber=38920) (PDF/A)

  Office Open XML Document (DOCX)                [ISO/IEC 29500](http://www.iso.org/iso/catalogue_detail?csnumber=51463)

  Open Document Text (ODT)                       [ISO/IEC 26300-1:2015](http://www.iso.org/iso/home/store/catalogue_ics/catalogue_detail_ics.htm?csnumber=66363)

  **Geodaten**

  GeoJSON (JSON)                                 <http://geojson.org>

  KML (XML)                                      [OGC KML](http://www.opengeospatial.org/standards/kml)

  GML (Geography Markup Language)                [OGC GML](http://www.opengeospatial.org/standards/gml)

  INTERLIS                                       <http://www.interlis.ch>

  INTERLIS/GML (gemäss eCH-0118)                 [eCH-0118](http://www.ech.ch/vechweb/page?p=dossier&documentNumber=eCH-0118)

  ESRI Shapefile<sup>[^6](#footnote-6)</sup>                             [ESRI Shapefile Technical Description](http://www.esri.com/library/whitepapers/pdfs/shapefile.pdf)

  GeoPackage                                     [OGC GeoPackage](http://www.geopackage.org/)

  GeoTIFF                                        <http://trac.osgeo.org/geotiff>

  **Bild-/Grafikformate**

  TIFF (Tagged Image File Format)                [TIFF Revision 6.0](http://partners.adobe.com/public/developer/en/tiff/TIFF6.pdf)

  JPEG2000                                       [ISO/IEC 15444-1 :2004](http://www.iso.org/iso/catalogue_detail.htm?csnumber=37674)

  PNG                                            [ISO/IEC 15948:2004](http://www.iso.org/iso/catalogue_detail.htm?csnumber=29581)

  SVG                                            [W3C REC](http://www.w3.org/TR/2003/REC-SVG11-20030114/)

  **Audio-/Videodaten**

  FLAC                                           [FLAC Format Spezifikation](https://xiph.org/flac/format.html)

  WebM                                           Web M [Documentation](http://www.webmproject.org/docs/)

  Ogg Vorbis                                     [Vorbis I specification](https://gever.edi.intra.admin.ch/edi/fscasp/content/bin/fscvext.dll?&cx=YBXkwy-nRRWNpd2F&tz=-120&cs=COO.1.1001.1.91460&pv=12080030&hx=D4-BE-D9-4F-DC-FF;CM010797;400&ax=COO.1.1001.1.32498&fscargs=COO.1.1001.1.48791;1;;venv_object%3DCOO.2080.100.3.154178)

  MPEG4                                          [ISO/IEC 14496-10](http://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.htm?csnumber=61490) Coding of audio-visual objects -- Part 10: Advanced Video Coding

                                                 [ISO/IEC 14496-3](http://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.htm?csnumber=53943) Coding of audio-visual objects -- Part 3: Audio

                                                 [ISO/IEC 14496-14](http://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.htm?csnumber=53943) Coding of audio-visual objects -- Part 14: MP4 file format

                                                 [ISO/IEC 14496-17](http://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.htm?csnumber=39478) Coding of audio-visual objects -- Part 17: Timed Text subtitle format

  Wave<sup>[^7](#footnote-7)</sup>                                       [Multimedia Programming Interface and Data Specifications 1.0](http://www.kk.iij4u.or.jp/~kondo/wave/mpidata.txt)
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

  **Weitere Austauschformen**
  ----------------------------------------------------------- ------------------------------------------------------------------------------------------------------
  WMS (Web Map Service) - nur eine Darstellung der Geodaten
  WFS (Web Feature Service) für Geodaten
  SPARQL (Protokoll und Abfragesprache)
  ODATA (Open Data Protocol)

Tabelle 3: Quelle: [\#2, Open Government Data – Grundlagenstudie
Schweiz](#referenzen), S. 88; Eigene Ergänzungen

Gepackte Dateien im ZIP Format sind grundsätzlich erwünscht, sofern der
Inhalt in einem geeigneten offenen Format vorliegt. Bei grösseren
Datensätzen im CSV oder JSON Format ist eine ZIP-Komprimierung zu
empfehlen.

## Empfehlungen

Grundsätzlich sind im OGD-Portal strukturierte Daten zu verwenden.
Textdokumente und Berichte dienen der Erläuterung der strukturierten
Daten. Es sind Formate zu verwenden, welche für den Inhalt der Daten
angemessen sind und die der Benutzer sinnvoll weiterverwenden kann.<sup>[^8](#footnote-8)</sup>
Es ist erlaubt, den gleichen Datensatz in mehreren Datenformaten auf dem
OGD Portal zu publizieren.

-   Für **strukturierte Daten** sind „einfache“ Formate wie CSV, XML
    oder JSON komplexeren Formaten wie ODS und XSLX vorzuziehen. Bei
    regelmässiger Publikation kann die Bereitstellung einer
    programmierbaren Schnittstelle (API)/eines Webdienstes erheblichen
    Zusatznutzen stiften.\
    Proprietäre, nicht-offene Formate (wie XLS) sind zu vermeiden. Dies
    auch, weil nicht davon ausgegangen werden kann, dass der Benutzer
    eine entsprechende Applikation zur Anzeige oder Weiterverarbeitung
    der Daten besitzt.

-   Für **Textdokumente und Berichte** sind (X)HTML, XML, ODT
    vorzuziehen. Falls eine maschinelle Weiterverarbeitung des Texts
    angestrebt wird („Natural Language Processing“), ist HTML/XML
    vorzuziehen. Dokumentationen zu angebotenen Datensätzen
    (Datenmodelle, Codelisten etc.) können als ODT, PDF oder DOCX
    publiziert werden. Falls es sich um einen Bericht handelt, der
    strukturierte Daten interpretiert und darstellt, sollten die
    zugrunde liegenden strukturierten Daten in angemessenen Formaten
    ebenfalls publiziert werden. Zu vermeiden sind ältere, proprietäre
    Formate wie DOC.

-   Für **vektorielle Geodaten** wird idealerweise ein modellkonformer
    Austausch vorgesehen, der mit INTERLIS oder INTERLIS/GML (gemäss
    eCH-0118) sichergestellt werden kann. Zusätzlich kann für einen
    vereinfachten Zugang zu den Geodaten ein anderes Format des Kapitels
    4 zur Verfügung gestellt werden.

-   Für **Raster-Geodaten** wird GeoTIFF empfohlen.

## Referenzen

  --------------------------------------------------------------------------------------------------------------------------------------------------------------------
  \#   Titel                                                Quelle, Link
  ---- ---------------------------------------------------- ----------------------------------------------------------------------------------------------------------
  1    OGD Strategie Schweiz\                               <http://www.egovernment.ch/umsetzung/00881/00883/index.html?lang=de>
       2014 – 2018

  2    Open Government Data – Grundlagenstudie Schweiz      <http://www.egovernment.ch/umsetzung/00881/00883/index.html?lang=de>

  3    G8 Open Data Charter\                                <https://www.gov.uk/government/uploads/system/uploads/attachment_data/file/207772/Open_Data_Charter.pdf>
       (Englisch)

  4    Berners Lee, Tim, Linked Data                        <http://www.w3.org/DesignIssues/LinkedData.html>

  5    5 ★ Open Data (Webseite)                             <http://5stardata.info/>

  6    Choosing appropriate formats                         <https://www.gov.uk/service-manual/user-centred-design/choosing-appropriate-formats.html>

  7    Konzeptbericht Ellipse – Archivierung von Geodaten   <http://www.bar.admin.ch/themen/00876/00939/index.html?lang=de>
  --------------------------------------------------------------------------------------------------------------------------------------------------------------------

## Anhang

## Formate in der OGD Praxis

Die folgende Tabelle zeigt die am meisten bereitgestellten Formate in
den nationalen OGD-Portalen in den USA, UK, D, A und CH:

                    Portal
  ----------------- ------------- ------------ ------------ ------------ ----------- -------------
  **Format**<sup>[^9](#footnote-9)</sup>    **US**        **UK**
  html              29**'**877    1'747
  xml               27**'**255    338
  csv               9'302         3'797
  pdf               15'379        1'041
  zip               13'309        193
  xls               4'463         1'835
  json              8'418         0
  wms               5'077         1'453
  rdf               5'849         278
  xlsx              165           0
  Weitere           63'824        292
  **Gesamtdaten**   **182'918**   **10'974**

Tabelle 2: Anzahl Formate in div. Portalen, sortiert nach Gesamtsumme
mit Stichtag 23.04.2015

Das Containerformat ZIP wird vor allem im US-Portal verwendet.
Betrachtet man nur diese fünf ausgewählten europäischen Portale, tritt
an die Stelle von ZIP die deutsche Eigenheit „Kartenviewer“, was im
wesentlichen Links auf Darstellungsdienste für Geoinformationen sind.

Ein wichtiges Format in der Schweiz ist das Open Document Spreadsheet
(ODS) mit 1'701 Datensätzen, mehrheitlich vom Bundesamt für Statistik.


<a name="footnote-1"></a>
[^1]: Der Begriff „Format“ bezieht sich auf das Element
    **dcat:mediaType** in der Metadatenformat-Definition von
    **DCAT:Distribution** im Projekt „OGD Schweiz“
    ([Projektergebnisse](../customXml/item1.xml))

<a name="footnote-2"></a>
[^2]: FAQ Open Government Data,
    http://www.opendata.admin.ch/de/faq\#was-ist-open-government-data

<a name="footnote-3"></a>
[^3]: RICHTLINIE 2013/37/EU DES EUROPÄISCHEN PARLAMENTS UND DES RATES
    vom 26. Juni 2013 zur Änderung der Richtlinie 2003/98/EG über die
    Weiterverwendung von Informationen des öffentlichen Sektors
    (http://eur-lex.europa.eu/legal-content/DE/TXT/PDF/?uri=CELEX:32013L0037&from=DE)

<a name="footnote-4"></a>
[^4]: Die Kriterien zur Offenheit stammen aus dem Konzeptbericht
    Ellipse, siehe [\#9, Konzeptbericht Ellipse zur Archivierung von
    Geodaten](#referenzen).

<a name="footnote-5"></a>
[^5]: RICHTLINIE 2013/37/EU DES EUROPÄISCHEN PARLAMENTS UND DES RATES
    vom 26. Juni 2013 zur Änderung der Richtlinie 2003/98/EG über die
    Weiterverwendung von Informationen des öffentlichen Sektors
    (http://eur-lex.europa.eu/legal-content/DE/TXT/PDF/?uri=CELEX:32013L0037&from=DE)

<a name="footnote-6"></a>
[^6]: Weit verbreitetes Format, jedoch proprietär (ESRI
    ArcGIS-Software). Es existieren Programmbibliotheken.

<a name="footnote-7"></a>
[^7]: Es existiert kein publizierter Standard für WAVE Dateien. Das
    WAVE-Format ist eine Implementierung des Ressource Interchange
    Formats (RIFF). Dieses ist als gemeinsame Publikation von IBM
    Corporation und Microsoft Corporation, August 1991 freigegeben
    (http://www-mmsp.ece.mcgill.ca/documents/audioformats/wave/Docs/riffmci.pdf).

<a name="footnote-8"></a>
[^8]: Dieser Abschnitt wurde stark von der britischen Lösung inspiriert,
    siehe [\#6, Choosing appropriate formats](#referenzen)

<a name="footnote-9"></a>
[^9]: Wo möglich und sinnvoll wurden verschiedene Formatbezeichnungen
    zusammengefasst. So kennt beispielsweise das US Portal die
    Bezeichnungen „xls“, „xlsx“ und „excel“. Das deutsche Portal kennt
    sowohl die MIME Typen „application/csv“ wie auch die Kurzbezeichnung
    „csv“.\
    Im US Portal an zweiter Stelle steht das binäre Format „Originator
    Data Format“ mit 27‘793 Datensätzen, welches auschliesslich von der
    National Oceanic and Atmospheric Administration (NOAA) produziert
    wird. Dieses Format wurde hier nicht berücksichtigt.
