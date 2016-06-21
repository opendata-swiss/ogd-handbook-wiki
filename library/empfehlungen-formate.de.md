---
Title: Empfehlungen für OGD Formate
Category: Library
Template: document
Tags: publish
Date: 2015-12-09
Slug: empfehlungen-formate
Authors:
Summary:
Lang: de
toc_run: true
Link_PDF: https://bar-files.opendata.swiss/owncloud/index.php/s/aS8LsxUtTe7cIAz
Link_DOC: https://bar-files.opendata.swiss/owncloud/index.php/s/9D3VHdnkS2pm1JJ
---

## 1 Einleitung

Um das Potential von offenen Behördendaten nutzen zu können, müssen
diese in Formaten[^1] bereitgestellt werden, welche möglichst einfach zu
verwenden sind. Unter offenen Behördendaten versteht man Datensätze, die
kostenfrei und im Idealfall in maschinenlesbarer Form zur
Sekundärnutzung allen Interessierten zur Verfügung stehen[^2]. Das
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

## 2 Ziel des Dokuments & Zielpublikum

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

## 3 Grundlagen & Auswahlkriterien

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

*Tabelle 1: Aus [\#2, Open Government Data – Grundlagenstudie Schweiz, S.
86](#referenzen); [\#5, 5 ★ Open Data (Webseite)](#referenzen)*

Am wichtigsten ist, dass die Datensätze mit offener Lizenz publiziert
werden. Für verschiedene Nutzer können hingegen verschiedene Formate
angeboten werden, um den spezifischen Anforderungen der Nutzer gerecht
zu werden.

Die zentralen Kriterien für die Datenpublikation im OGD-Portal sind
Maschinenlesbarkeit und Offenheit (siehe [\#1 OGD Strategie
Schweiz](#referenzen)). Diese Kriterien Maschinenlesbarkeit und
Offenheit sind im Folgenden rot gekennzeichnet.

#### (1) Maschinenlesbarkeit

| <font color="red">**Maschinenlesbarkeit**</font> | Das Format und die enthaltenen Daten können von einem Programm automatisiert verarbeitet werden. |
|-------------------------|-------------------|

"Maschinenlesbar ist ein [...] Format, das so strukturiert ist, dass Softwareanwendungen konkrete Daten, einschließlich einzelner Sachverhaltsdarstellungen und deren interner Struktur, leicht identifizieren, erkennen und extrahieren können"[^3].

Mit dieser Definition ist beispielsweise eine Textdatei erst dann maschinenlesbar, wenn die darin enthaltenen Daten so strukturiert dargestellt sind, dass sie mit einem passenden Algorithmus (Programm) korrekt interpretiert und verarbeitet werden können. Ein (X)HTML-Text (eine Webseite) ist demnach nicht maschinenlesbar - ein Browser kann die Inhalte nur für Menschen lesbar auf dem Bildschirm darstellen. Erst wenn die Inhalte der Webseite semantisch strukturiert ausgezeichnet werden (z.B. unter Verwendung des Vokabulars schema.org), können die Inhalte von einem Programm als Datenstrukturen erkannt und entsprechend verarbeitet werden. Ausserdem ist bei textbasierten Formaten eine standardisierte Zeichenkodierung notwendig (wenn möglich UTF-8), um auch spezielle Zeichen (z.B. Umlaute) korrekt interpretieren zu können.

Um einen passenden Algorithmus zur Verarbeitung der strukturierten Daten programmieren zu können, ist das maschinenlesbare Format noch nicht ausreichend. Die Daten müssen zusätzlich "verständlich und zweckmässig beschrieben" sein. Falls die Struktur der Daten einem Standard folgt, genügt die Angabe des betreffenden Standards (z.B. schema.org). Andernfalls muss die Beschreibung der Datenstruktur in die Metadaten integriert werden.

#### (2) Offenheit

| <font color="red">**Offenheit**</font>[^4] | Die Spezifikation des Formats ist offen gelegt und öffentlich zugänglich. |
|---------------|-------------------|

"Offen ist ein Dateiformat, das plattformunabhängig ist und der Öffentlichkeit ohne Einschränkungen, die der Weiterverwendung von Dokumenten hinderlich wären, zugänglich gemacht wird"[^5].

Die Offenheit bzw. die Zugänglichkeit der Spezifikation ist für die lückenlose Interpretierbarkeit der durch das Format kodierten Information entscheidend. Dazu gehört auch, dass der Standard verständlich, überschaubar und eindeutig sein soll; dass dieser Standard lizenzfrei ist und weit verbreitet ist.\
Dieses Kriterium muss erfüllt sein, damit ein Format als offen gelten kann.

Beide Kriterien Maschinenlesbarkeit und Offenheit weisen mehrere
Dimensionen auf, die im Folgenden beschrieben werden. Die nachfolgenden,
blau gekennzeichneten Dimensionen, sollen von den Datenlieferanten bei
der Auswahl geeigneter Formate, bzw. Austauschformen für ihre Datensätze
mitberücksichtigt werden.

| <font color="blue">**Standard**</font> | Das Format wird durch ein Standardgremium periodisch überprüft und aktualisiert (international, national). |
|--------------|-------------------|

Die Standards von (inter-)nationalen Organisationen sind langlebiger und weniger revisionsanfällig, verleihen einem Format also Stabilität. Ein Standardgremium ist grundsätzlich unabhängiger und glaubwürdiger als eine einzelne Firma, welche die Rechte an einem Format besitzt.

| <font color="blue">**Lizenzfrei**</font> | Formate sind nicht durch auferlegte Lizenzen in der Herstellung oder Benutzung limitiert. |
|----------------|-------------------|

Verhinderung einer Herstellerabhängigkeit. Verminderung bzw. Ausschaltung des potentiellen Risikos, dass der Lizenzinhaber jederzeit Änderungen vornehmen und durchsetzen kann.

| <font color="blue">**Verbreitung**</font> | Das Format ist weit verbreitet. |
|-----------------|-------------------|

Grosse Verbreitung bedeutet eine zum heutigen Zeitpunkt abschätzbare relativ grosse Benutzerzahl wie auch eine gewisse Diversität der Benutzer, eine grosse Anzahl existierender Dateien im entsprechenden Format, Unterstützung des Formats durch viele voneinander unabhängige Applikationen und Programmbibliotheken. Ebenso ist die geografische Verbreitung gemeint.

## 4 Anwendungsfälle und Formate

Je nach Anwendungsfall können offene Daten ganz unterschiedliche Formate
aufweisen. Häufig werden die Daten in Tabellenform vorliegen. Aber auch
Bilder, Tonaufnahmen oder Videos können Datensätze oder Bestandteile von
Datensätzen darstellen. Entsprechend gross ist die Vielfalt von
Formaten, in denen Daten auf dem OGD Portal veröffentlicht werden
können.

Die folgende Tabelle listet die wichtigsten, für die Publikation auf dem
OGD Portal in Frage kommenden offenen Formate zusammen mit dem Verweis
auf den jeweiligen Standard auf.

<table border="0" cellspacing="0" cellpadding="0" width="96%" class="Table7"><colgroup><col width="346"/><col width="325"/></colgroup><tr class="Table71"><td style="text-align:left;width:7.922cm; " class="Table7_A1"><p class="P5"><span class="T23">Anwendungsfälle und Datenformate</span></p></td><td style="text-align:left;width:7.437cm; " class="Table7_A1"><p class="P5"><span class="T23">Verweis auf Standard / Quasi-Standard </span><span class="T6">(wenn verfügbar)</span></p></td></tr><tr class="Table71"><td colspan="2" style="text-align:left;width:7.922cm; " class="Table7_A2"><p class="P5"><span class="T25">Strukturierte</span><span class="T23"> Daten        </span></p></td></tr><tr class="Table71"><td style="text-align:left;width:7.922cm; " class="Table7_A3"><p class="P5"><span class="T6">Comma Separated Values (CSV)</span></p></td><td style="text-align:left;width:7.437cm; " class="Table7_B3"><p class="P6"><a href="https://tools.ietf.org/html/rfc4180" class="Internet_20_link"><span class="T14">RFC 4180</span></a></p></td></tr><tr class="Table71"><td style="text-align:left;width:7.922cm; " class="Table7_A4"><p class="P5"><span class="T29">JavaScript Object Notation (JSON)</span></p></td><td style="text-align:left;width:7.437cm; " class="Table7_B4"><p class="P6"><a href="http://tools.ietf.org/html/rfc4627" class="Internet_20_link"><span class="T15">RFC 4627</span></a></p></td></tr><tr class="Table71"><td style="text-align:left;width:7.922cm; " class="Table7_A5"><p class="P5"><span class="T29">Extensible Markup Language (XML)</span></p></td><td style="text-align:left;width:7.437cm; " class="Table7_B5"><p class="P6"><a href="http://www.w3.org/TR/2008/REC-xml-20081126/" class="Internet_20_link"><span class="T15">W3C REC</span></a></p></td></tr><tr class="Table71"><td style="text-align:left;width:7.922cm; " class="Table7_A6"><p class="P5"><span class="T29">Resource Description Framework (RDF)</span></p></td><td style="text-align:left;width:7.437cm; " class="Table7_B6"><p class="P6"><a href="http://www.w3.org/standards/techs/rdf#w3c_all" class="Internet_20_link"><span class="T15">W3C REC</span></a></p></td></tr><tr class="Table71"><td style="text-align:left;width:7.922cm; " class="Table7_A7"><p class="P5"><span class="T19">Office Open XML Spreadsheet (XLSX)</span></p></td><td style="text-align:left;width:7.437cm; " class="Table7_B7"><p class="P6"><a href="http://www.iso.org/iso/catalogue_detail?csnumber=51463" class="Internet_20_link"><span class="T14">ISO/IEC 29500</span></a></p></td></tr><tr class="Table71"><td style="text-align:left;width:7.922cm; " class="Table7_A8"><p class="P5"><span class="T6">Open Document Spreadsheet (ODS)</span></p></td><td style="text-align:left;width:7.437cm; " class="Table7_B8"><p class="P6"><a href="http://www.iso.org/iso/home/store/catalogue_ics/catalogue_detail_ics.htm?csnumber=66363" class="Internet_20_link"><span class="T8">ISO/IEC 26300-1:2015</span></a></p></td></tr><tr class="Table71"><td colspan="2" style="text-align:left;width:7.922cm; " class="Table7_A2"><p class="P5"><span class="T21">Textdokumente / Berichte</span></p></td></tr><tr class="Table71"><td style="text-align:left;width:7.922cm; " class="Table7_A10"><p class="P5"><span class="T19">Text (TXT)</span></p></td><td style="text-align:left;width:7.437cm; " class="Table7_B10"><p class="P17"><span class="T17">ISO Latin-1 (</span><a href="http://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.htm?csnumber=28245" class="Internet_20_link"><span class="T17">ISO 8859-1</span></a><span class="T17">) und <br/>ISO Latin-9 (</span><a href="http://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.htm?csnumber=29505" class="Internet_20_link"><span class="T17">ISO 8859-15</span></a><span class="T17">) </span></p><p class="P17"><span class="T13">Universal Coded Character Set (UCS) (</span><a href="http://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.htm?csnumber=63182" class="Internet_20_link"><span class="T13">ISO 10646</span></a><span class="T13">) </span></p><p class="P4"><span class="T13">US-ASCII (ANSI X3.4-1986, </span><span class="T12">bzw. ISO/IEC 646-US oder ISO/IEC 646:1991-IRV</span><span class="T13">):  </span><a href="http://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.htm?csnumber=4777" class="Internet_20_link"><span class="T13">ISO/IEC 646:1991 </span></a><span class="T13"> </span></p></td></tr><tr class="Table71"><td style="text-align:left;width:7.922cm; " class="Table7_A11"><p class="P5"><span class="T19">Extensible Hypertext Markup Language (XHTML)</span></p></td><td style="text-align:left;width:7.437cm; " class="Table7_B11"><p class="P6"><a href="http://www.w3.org/TR/2001/REC-xhtml11-20010531/" class="Internet_20_link"><span class="T13">W3C REC</span></a></p></td></tr><tr class="Table71"><td style="text-align:left;width:7.922cm; " class="Table7_A12"><p class="P5"><span class="T31">Portable</span><span class="T29"> Document Format (PDF)</span></p></td><td style="text-align:left;width:7.437cm; " class="Table7_B12"><p class="P6"><a href="http://www.iso.org/iso/catalogue_detail.htm?csnumber=51502" class="Internet_20_link"><span class="T8">ISO 32000-1:2008</span></a><span class="T8"> (nur PDF 1.7), </span><a href="http://www.iso.org/iso/catalogue_detail?csnumber=38920" class="Internet_20_link"><span class="T8">ISO 19005</span></a><span class="T8"> (PDF/A)</span></p></td></tr><tr class="Table71"><td style="text-align:left;width:7.922cm; " class="Table7_A13"><p class="P5"><span class="T29">Office Open XML Document (DOCX)</span></p></td><td style="text-align:left;width:7.437cm; " class="Table7_B13"><p class="P6"><a href="http://www.iso.org/iso/catalogue_detail?csnumber=51463" class="Internet_20_link"><span class="T14">ISO/IEC 29500</span></a></p></td></tr><tr class="Table71"><td style="text-align:left;width:7.922cm; " class="Table7_A14"><p class="P5"><span class="T29">Open Document Text (ODT)</span></p></td><td style="text-align:left;width:7.437cm; " class="Table7_B14"><p class="P12"><a href="http://www.iso.org/iso/home/store/catalogue_ics/catalogue_detail_ics.htm?csnumber=66363" class="Internet_20_link"><span class="T8">ISO/IEC 26300-1:2015</span></a></p></td></tr><tr class="Table71"><td colspan="2" style="text-align:left;width:7.922cm; " class="Table7_A2"><p class="P13"><span class="T30">Geodaten</span></p></td></tr><tr class="Table71"><td style="text-align:left;width:7.922cm; " class="Table7_A16"><p class="P5"><span class="T29">GeoJSON (JSON)</span></p></td><td style="text-align:left;width:7.437cm; " class="Table7_B16"><p class="P12"><a href="http://geojson.org" class="Internet_20_link"><span class="T15">http://geojson.org</span></a><span class="T15"> </span></p></td></tr><tr class="Table71"><td style="text-align:left;width:7.922cm; " class="Table7_A17"><p class="P5"><span class="T29">KML (XML)</span></p></td><td style="text-align:left;width:7.437cm; " class="Table7_B17"><p class="P12"><a href="http://www.opengeospatial.org/standards/kml" class="Internet_20_link"><span class="T15">OGC KML</span></a></p></td></tr><tr class="Table71"><td style="text-align:left;width:7.922cm; " class="Table7_A18"><p class="P5"><span class="T29">GML (Geography Markup Language)</span></p></td><td style="text-align:left;width:7.437cm; " class="Table7_B18"><p class="P12"><a href="http://www.opengeospatial.org/standards/gml" class="Internet_20_link"><span class="T15">OGC GML</span></a></p></td></tr><tr class="Table71"><td style="text-align:left;width:7.922cm; " class="Table7_A19"><p class="P5"><span class="T45">INTERLIS</span></p></td><td style="text-align:left;width:7.437cm; " class="Table7_B19"><p class="P12"><a href="http://www.interlis.ch" class="Internet_20_link"><span class="T15">http://www.interlis.ch</span></a></p></td></tr><tr class="Table71"><td style="text-align:left;width:7.922cm; " class="Table7_A20"><p class="P5"><span class="T45">INTERLIS/GML (gemäss eCH-0118)</span></p></td><td style="text-align:left;width:7.437cm; " class="Table7_B20"><p class="P12"><a href="http://www.ech.ch/vechweb/page?p=dossier&amp;documentNumber=eCH-0118" class="Internet_20_link"><span class="T15">eCH-0118</span></a></p></td></tr><tr class="Table71"><td style="text-align:left;width:7.922cm; " class="Table7_A21"><div class="P5"><span class="T29">ESRI Shapefile</span><span class="T29"><span class="Footnote_20_anchor" title="Footnote:  Weit verbreitetes Format, jedoch proprietär (ESRI ArcGIS-Software). Es existieren Programmbibliotheken."><a href="#ftn6" id="body_ftn6">6</a></span></span></div></td><td style="text-align:left;width:7.437cm; " class="Table7_B21"><p class="P6"><a href="http://www.esri.com/library/whitepapers/pdfs/shapefile.pdf" class="Internet_20_link"><span class="T15">ESRI Shapefile Technical Description</span></a></p></td></tr><tr class="Table71"><td style="text-align:left;width:7.922cm; " class="Table7_A22"><p class="P5"><span class="T29">GeoPackage</span></p></td><td style="text-align:left;width:7.437cm; " class="Table7_B22"><p class="P12"><a href="http://www.geopackage.org/" class="Internet_20_link"><span class="T15">OGC GeoPackage</span></a></p></td></tr><tr class="Table71"><td style="text-align:left;width:7.922cm; " class="Table7_A23"><p class="P5"><span class="T29">GeoTIFF</span></p></td><td style="text-align:left;width:7.437cm; " class="Table7_B23"><p class="P12"><a href="http://trac.osgeo.org/geotiff" class="Internet_20_link"><span class="T15">http://trac.osgeo.org/geotiff</span></a></p></td></tr><tr class="Table71"><td colspan="2" style="text-align:left;width:7.922cm; " class="Table7_A2"><p class="P5"><span class="T30">Bild-/Grafikformate</span></p></td></tr><tr class="Table71"><td style="text-align:left;width:7.922cm; " class="Table7_A25"><p class="P5"><span class="T31">TIFF (Tagged Image File Format)</span></p></td><td style="text-align:left;width:7.437cm; " class="Table7_B25"><p class="P6"><a href="http://partners.adobe.com/public/developer/en/tiff/TIFF6.pdf" class="Internet_20_link"><span class="T8">TIFF Revision 6.0</span></a><span class="T9"> </span></p></td></tr><tr class="Table71"><td style="text-align:left;width:7.922cm; " class="Table7_A26"><p class="P5"><span class="T29">JPEG2000</span></p></td><td style="text-align:left;width:7.437cm; " class="Table7_B26"><p class="P12"><a href="http://www.iso.org/iso/catalogue_detail.htm?csnumber=37674" class="Internet_20_link"><span class="T15">ISO/IEC 15444-1 :2004</span></a></p></td></tr><tr class="Table71"><td style="text-align:left;width:7.922cm; " class="Table7_A27"><p class="P5"><span class="T29">PNG</span></p></td><td style="text-align:left;width:7.437cm; " class="Table7_B27"><p class="P12"><a href="http://www.iso.org/iso/catalogue_detail.htm?csnumber=29581" class="Internet_20_link"><span class="T15">ISO/IEC 15948:2004</span></a></p></td></tr><tr class="Table71"><td style="text-align:left;width:7.922cm; " class="Table7_A28"><p class="P5"><span class="T29">SVG</span></p></td><td style="text-align:left;width:7.437cm; " class="Table7_B28"><p class="P12"><a href="http://www.w3.org/TR/2003/REC-SVG11-20030114/" class="Internet_20_link"><span class="T15">W3C REC</span></a></p></td></tr><tr class="Table71"><td colspan="2" style="text-align:left;width:7.922cm; " class="Table7_A2"><p class="P13"><span class="T30">Audio-/Videodaten</span></p></td></tr><tr class="Table71"><td style="text-align:left;width:7.922cm; " class="Table7_A30"><p class="P5"><span class="T29">FLAC</span></p></td><td style="text-align:left;width:7.437cm; " class="Table7_B30"><p class="P12"><a href="https://xiph.org/flac/format.html" class="Internet_20_link"><span class="T15">FLAC Format Spezifikation</span></a></p></td></tr><tr class="Table71"><td style="text-align:left;width:7.922cm; " class="Table7_A31"><p class="P5"><span class="T29">WebM</span></p></td><td style="text-align:left;width:7.437cm; " class="Table7_B31"><p class="P12"><span class="T15">Web M </span><a href="http://www.webmproject.org/docs/" class="Internet_20_link"><span class="T15">Documentation</span></a></p></td></tr><tr class="Table71"><td style="text-align:left;width:7.922cm; " class="Table7_A32"><p class="P5"><span class="T29">Ogg Vorbis</span></p></td><td style="text-align:left;width:7.437cm; " class="Table7_B32"><p class="P12"><a href="https://gever.edi.intra.admin.ch/edi/fscasp/content/bin/fscvext.dll?&amp;cx=YBXkwy-nRRWNpd2F&amp;tz=-120&amp;cs=COO.1.1001.1.91460&amp;pv=12080030&amp;hx=D4-BE-D9-4F-DC-FF;CM010797;400&amp;ax=COO.1.1001.1.32498&amp;fscargs=COO.1.1001.1.48791;1;;venv_object%3DCOO.2080.100.3.154178" class="Internet_20_link"><span class="T15">Vorbis I specification</span></a></p></td></tr><tr class="Table71"><td style="text-align:left;width:7.922cm; " class="Table7_A33"><p class="P5"><span class="T29">MPEG4</span></p></td><td style="text-align:left;width:7.437cm; " class="Table7_B33"><p class="P41"><a href="http://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.htm?csnumber=61490" class="Internet_20_link"><span class="T12">ISO/IEC 14496-10</span></a><span class="T12"> Coding of audio-visual objects -- Part 10: Advanced Video Coding </span></p><p class="P41"><a href="http://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.htm?csnumber=53943" class="Internet_20_link"><span class="T12">ISO/IEC 14496-3</span></a><span class="T12"> Coding of audio-visual objects -- Part 3: Audio </span></p><p class="P41"><a href="http://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.htm?csnumber=53943" class="Internet_20_link"><span class="T12">ISO/IEC 14496-14</span></a><span class="T12"> Coding of audio-visual objects -- Part 14: MP4 file format </span></p><p class="P10"><a href="http://www.iso.org/iso/home/store/catalogue_tc/catalogue_detail.htm?csnumber=39478" class="Internet_20_link"><span class="T32">ISO/IEC 14496-17</span></a><span class="T32"> Coding of audio-visual objects -- Part 17: Timed Text subtitle format </span></p></td></tr><tr class="Table71"><td style="text-align:left;width:7.922cm; " class="Table7_A34"><div class="P5"><span class="T29">Wave</span><span class="T29"><span class="Footnote_20_anchor" title="Footnote:  Es existiert kein publizierter Standard für WAVE Dateien. Das WAVE-Format ist eine Implementierung des Ressource Interchange Formats (RIFF). Dieses ist als gemeinsame Publikation von IBM Corporation und Microsoft Corporation, August 1991 freigegeben (http://www-mmsp.ece.mcgill.ca/documents/audioformats/wave/Docs/riffmci.pdf)."><a href="#ftn7" id="body_ftn7">7</a></span></span></div></td><td style="text-align:left;width:7.437cm; " class="Table7_B34"><p class="P6"><a href="http://www.kk.iij4u.or.jp/~kondo/wave/mpidata.txt" class="Internet_20_link"><span class="T15">Multimedia Programming Interface and Data Specifications 1.0</span></a><span class="T15"> </span></p></td></tr></table><p class="Standard"> </p><table border="0" cellspacing="0" cellpadding="0" width="96%" class="Table8"><colgroup><col width="346"/><col width="325"/></colgroup><tr class="Table81"><td colspan="2" style="text-align:left;width:7.927cm; " class="Table8_A1"><p class="P14"><span class="T30">Weitere </span><span class="T23">Austauschformen</span></p></td></tr><tr class="Table81"><td style="text-align:left;width:7.927cm; " class="Table8_A2"><p class="P5"><span class="T34">WMS (Web Map Service) - nur eine Darstellung der Geodaten</span></p></td><td style="text-align:left;width:7.433cm; " class="Table8_B2"><p class="P11"><a href="http://www.opengeospatial.org/standards/wms" class="Internet_20_link"><span class="T8">WMS-Beschreibung des OGS (Open Geospatial Consortium)</span></a></p></td></tr><tr class="Table81"><td style="text-align:left;width:7.927cm; " class="Table8_A3"><p class="P5"><span class="T19">WFS (Web Feature Service) für Geodaten</span></p></td><td style="text-align:left;width:7.433cm; " class="Table8_B3"><p class="P6"><a href="http://www.opengeospatial.org/standards/wfs" class="Internet_20_link"><span class="T16">OGC WFS</span></a></p></td></tr><tr class="Table81"><td style="text-align:left;width:7.927cm; " class="Table8_A4"><p class="P5"><span class="T6">SPARQL (Protokoll und Abfragesprache)</span></p></td><td style="text-align:left;width:7.433cm; " class="Table8_B4"><p class="P6"><a href="http://www.w3.org/TR/sparql11-overview/" class="Internet_20_link"><span class="T8">W3C SPARQL</span></a></p></td></tr><tr class="Table81"><td style="text-align:left;width:7.927cm; " class="Table8_A5"><p class="P5"><span class="T6">ODATA (Open Data Protocol)</span></p></td><td style="text-align:left;width:7.433cm; " class="Table8_B5"><p class="P6"><a href="http://www.odata.org" class="Internet_20_link"><span class="T9">http://www.odata.org</span></a></p></td></tr></table>

*Tabelle 3: Quelle: [\#2, Open Government Data – Grundlagenstudie Schweiz](#referenzen), S. 88; Eigene Ergänzungen*

Gepackte Dateien im ZIP Format sind grundsätzlich erwünscht, sofern der
Inhalt in einem geeigneten offenen Format vorliegt. Bei grösseren
Datensätzen im CSV oder JSON Format ist eine ZIP-Komprimierung zu
empfehlen.

## 5 Empfehlungen

Grundsätzlich sind im OGD-Portal strukturierte Daten zu verwenden.
Textdokumente und Berichte dienen der Erläuterung der strukturierten
Daten. Es sind Formate zu verwenden, welche für den Inhalt der Daten
angemessen sind und die der Benutzer sinnvoll weiterverwenden kann.[^8]
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

## 6 Referenzen

<table border="0" cellspacing="0" cellpadding="0" class="Table9"><colgroup><col width="44"/><col width="236"/><col width="429"/></colgroup><tr class="Table91"><td style="text-align:left;width:0.998cm; " class="Table9_A1"><p class="P18"><span class="T5">#</span></p></td><td style="text-align:left;width:5.394cm; " class="Table9_A1"><p class="P18"><span class="T5">Titel</span></p></td><td style="text-align:left;width:9.807cm; " class="Table9_A1"><p class="P18"><span class="T5">Quelle, Link</span></p></td></tr><tr class="Table91"><td style="text-align:left;width:0.998cm; " class="Table9_A2"><p class="P7"><span class="T7">1</span></p></td><td style="text-align:left;width:5.394cm; " class="Table9_B2"><p class="P7"><span class="T7">OGD Strategie Schweiz <br/>2014 – 2018</span></p></td><td style="text-align:left;width:9.807cm; " class="Table9_C2"><p class="P6"><a href="http://www.egovernment.ch/umsetzung/00881/00883/index.html?lang=de" class="Internet_20_link">http://www.egovernment.ch/umsetzung/00881/00883/index.html?lang=de</a><span class="T48"> </span></p></td></tr><tr class="Table91"><td style="text-align:left;width:0.998cm; " class="Table9_A3"><p class="P7"><span class="T20">2</span></p></td><td style="text-align:left;width:5.394cm; " class="Table9_B3"><p class="P7"><span class="T7">Open Government Data – Grundlagenstudie Schweiz</span></p></td><td style="text-align:left;width:9.807cm; " class="Table9_C3"><p class="P6"><a href="http://www.egovernment.ch/umsetzung/00881/00883/index.html?lang=de" class="Internet_20_link">http://www.egovernment.ch/umsetzung/00881/00883/index.html?lang=de</a><span class="T48"> </span></p></td></tr><tr class="Table91"><td style="text-align:left;width:0.998cm; " class="Table9_A4"><p class="P7"><span class="T20">3</span></p></td><td style="text-align:left;width:5.394cm; " class="Table9_B4"><p class="P7"><span class="T20">G8 Open Data Charter <br/>(Englisch)</span></p></td><td style="text-align:left;width:9.807cm; " class="Table9_C4"><p class="P6"><a href="https://www.gov.uk/government/uploads/system/uploads/attachment_data/file/207772/Open_Data_Charter.pdf" class="Internet_20_link"><span class="T50">https://www.gov.uk/government/uploads/system/uploads/attachment_data/file/207772/Open_Data_Charter.pdf</span></a><span class="T51"> </span></p></td></tr><tr class="Table91"><td style="text-align:left;width:0.998cm; " class="Table9_A5"><p class="P7"><span class="T20">4</span></p></td><td style="text-align:left;width:5.394cm; " class="Table9_B5"><p class="P7"><span class="T20">Berners Lee, Tim, Linked Data</span></p></td><td style="text-align:left;width:9.807cm; " class="Table9_C5"><p class="P6"><a href="http://www.w3.org/DesignIssues/LinkedData.html" class="Internet_20_link"><span class="T50">http://www.w3.org/DesignIssues/LinkedData.html</span></a><span class="T51"> </span></p></td></tr><tr class="Table91"><td style="text-align:left;width:0.998cm; " class="Table9_A6"><p class="P7"><span class="T20">5</span></p></td><td style="text-align:left;width:5.394cm; " class="Table9_B6"><p class="P7"><span class="T20">5 </span><span class="T41">★</span><span class="T20"> Open Data (Webseite)</span></p></td><td style="text-align:left;width:9.807cm; " class="Table9_C6"><p class="P6"><a href="http://5stardata.info/" class="Internet_20_link"><span class="T48">http://5stardata.info/</span></a><span class="T49"> </span></p></td></tr><tr class="Table91"><td style="text-align:left;width:0.998cm; " class="Table9_A7"><p class="P7"><span class="T20">6</span></p></td><td style="text-align:left;width:5.394cm; " class="Table9_B7"><p class="P7"><span class="T20">Choosing appropriate formats</span></p></td><td style="text-align:left;width:9.807cm; " class="Table9_C7"><p class="P6"><a href="https://www.gov.uk/service-manual/user-centred-design/choosing-appropriate-formats.html" class="Internet_20_link"><span class="T50">https://www.gov.uk/service-manual/user-centred-design/choosing-appropriate-formats.html</span></a><span class="T51"> </span></p></td></tr><tr class="Table91"><td style="text-align:left;width:0.998cm; " class="Table9_A8"><p class="P7"><span class="T20">7</span></p></td><td style="text-align:left;width:5.394cm; " class="Table9_B8"><p class="P7"><span class="T7">Konzeptbericht Ellipse – Archivierung von Geodaten</span></p></td><td style="text-align:left;width:9.807cm; " class="Table9_C8"><p class="P6"><a href="http://www.bar.admin.ch/themen/00876/00939/index.html?lang=de" class="Internet_20_link">http://www.bar.admin.ch/themen/00876/00939/index.html?lang=de</a><span class="T48"> </span></p></td></tr></table>

## 7 Anhang

## 7.1 Formate in der OGD Praxis

Die folgende Tabelle zeigt die am meisten bereitgestellten Formate in
den nationalen OGD-Portalen in den USA, UK, D, A und CH:

<table border="0" cellspacing="0" cellpadding="0" class="Table10"><colgroup><col width="104"/><col width="94"/><col width="99"/><col width="99"/><col width="99"/><col width="99"/><col width="99"/></colgroup><tr class="Table101"><td style="text-align:left;width:2.39cm; " class="Table10_A1"><p class="P20"> </p></td><td colspan="5" style="text-align:left;width:2.147cm; " class="Table10_A1"><p class="P19"><span class="T7">Portal</span></p></td><td style="text-align:left;width:2.27cm; " class="Table10_A1"><p class="P20"> </p></td></tr><tr class="Table101"><td style="text-align:left;width:2.39cm; " class="Table10_A2"><div class="P7"><span class="T24">Format</span><span class="T24"><span class="Footnote_20_anchor" title="Footnote:  Wo möglich und sinnvoll wurden verschiedene Formatbezeichnungen zusammengefasst. So kennt beispielsweise das US Portal die Bezeichnungen „xls“, „xlsx“ und „excel“. Das deutsche Portal kennt sowohl die MIME Typen „application/csv“ wie auch die Kurzbezeichnung „csv“. Im US Portal an zweiter Stelle steht das binäre Format „Originator Data Format“ mit 27‘793 Datensätzen, welches auschliesslich von der National Oceanic and Atmospheric Administration (NOAA) produziert wird. Dieses Format wurde hier nicht berücksichtigt."><a href="#ftn9" id="body_ftn9">9</a></span></span></div></td><td style="text-align:left;width:2.147cm; " class="Table10_B2"><p class="P7"><span class="T24">US</span></p></td><td style="text-align:left;width:2.268cm; " class="Table10_C2"><p class="P7"><span class="T24">UK</span></p></td><td style="text-align:left;width:2.268cm; " class="Table10_D2"><p class="P7"><span class="T24">EU</span></p></td><td style="text-align:left;width:2.268cm; " class="Table10_E2"><p class="P7"><span class="T24">DE</span></p></td><td style="text-align:left;width:2.267cm; " class="Table10_F2"><p class="P7"><span class="T24">CH</span></p></td><td style="text-align:left;width:2.27cm; " class="Table10_G2"><p class="P7"><span class="T24">Summe</span></p></td></tr><tr class="Table103"><td style="text-align:left;width:2.39cm; " class="Table10_A3"><p class="P7"><span class="T5">html</span></p></td><td style="text-align:left;width:2.147cm; " class="Table10_B3"><p class="P7"><span class="T5">29</span><span class="T23">'</span><span class="T5">877</span></p></td><td style="text-align:left;width:2.268cm; " class="Table10_C3"><p class="P7"><span class="T5">1'747</span></p></td><td style="text-align:left;width:2.268cm; " class="Table10_D3"><p class="P7"><span class="T5">2'335</span></p></td><td style="text-align:left;width:2.268cm; " class="Table10_E3"><p class="P7"><span class="T5">5'204</span></p></td><td style="text-align:left;width:2.267cm; " class="Table10_F3"><p class="P7"><span class="T5">11</span></p></td><td style="text-align:left;width:2.27cm; " class="Table10_G3"><p class="P7"><span class="T26">39'174</span></p></td></tr><tr class="Table103"><td style="text-align:left;width:2.39cm; " class="Table10_A4"><p class="P7"><span class="T5">xml</span></p></td><td style="text-align:left;width:2.147cm; " class="Table10_B4"><p class="P7"><span class="T5">27</span><span class="T23">'</span><span class="T5">255</span></p></td><td style="text-align:left;width:2.268cm; " class="Table10_C4"><p class="P7"><span class="T5">338</span></p></td><td style="text-align:left;width:2.268cm; " class="Table10_D4"><p class="P7"><span class="T5">3'409</span></p></td><td style="text-align:left;width:2.268cm; " class="Table10_E4"><p class="P7"><span class="T5">438</span></p></td><td style="text-align:left;width:2.267cm; " class="Table10_F4"><p class="P7"><span class="T5">1</span></p></td><td style="text-align:left;width:2.27cm; " class="Table10_G4"><p class="P7"><span class="T26">31'441</span></p></td></tr><tr class="Table103"><td style="text-align:left;width:2.39cm; " class="Table10_A5"><p class="P7"><span class="T5">csv</span></p></td><td style="text-align:left;width:2.147cm; " class="Table10_B5"><p class="P7"><span class="T5">9'302</span></p></td><td style="text-align:left;width:2.268cm; " class="Table10_C5"><p class="P7"><span class="T5">3'797</span></p></td><td style="text-align:left;width:2.268cm; " class="Table10_D5"><p class="P7"><span class="T5">10'899</span></p></td><td style="text-align:left;width:2.268cm; " class="Table10_E5"><p class="P7"><span class="T5">7'177</span></p></td><td style="text-align:left;width:2.267cm; " class="Table10_F5"><p class="P7"><span class="T5">17</span></p></td><td style="text-align:left;width:2.27cm; " class="Table10_G5"><p class="P7"><span class="T26">31'192</span></p></td></tr><tr class="Table103"><td style="text-align:left;width:2.39cm; " class="Table10_A6"><p class="P7"><span class="T5">pdf</span></p></td><td style="text-align:left;width:2.147cm; " class="Table10_B6"><p class="P7"><span class="T5">15'379</span></p></td><td style="text-align:left;width:2.268cm; " class="Table10_C6"><p class="P7"><span class="T5">1'041</span></p></td><td style="text-align:left;width:2.268cm; " class="Table10_D6"><p class="P7"><span class="T5">1'527</span></p></td><td style="text-align:left;width:2.268cm; " class="Table10_E6"><p class="P7"><span class="T5">1'917</span></p></td><td style="text-align:left;width:2.267cm; " class="Table10_F6"><p class="P7"><span class="T5">16</span></p></td><td style="text-align:left;width:2.27cm; " class="Table10_G6"><p class="P7"><span class="T26">19'880</span></p></td></tr><tr class="Table103"><td style="text-align:left;width:2.39cm; " class="Table10_A7"><p class="P7"><span class="T5">zip</span></p></td><td style="text-align:left;width:2.147cm; " class="Table10_B7"><p class="P7"><span class="T5">13'309</span></p></td><td style="text-align:left;width:2.268cm; " class="Table10_C7"><p class="P7"><span class="T5">193</span></p></td><td style="text-align:left;width:2.268cm; " class="Table10_D7"><p class="P7"><span class="T5">1'263</span></p></td><td style="text-align:left;width:2.268cm; " class="Table10_E7"><p class="P7"><span class="T5">265</span></p></td><td style="text-align:left;width:2.267cm; " class="Table10_F7"><p class="P7"><span class="T5">19</span></p></td><td style="text-align:left;width:2.27cm; " class="Table10_G7"><p class="P7"><span class="T26">15'049</span></p></td></tr><tr class="Table103"><td style="text-align:left;width:2.39cm; " class="Table10_A8"><p class="P7"><span class="T5">xls</span></p></td><td style="text-align:left;width:2.147cm; " class="Table10_B8"><p class="P7"><span class="T5">4'463</span></p></td><td style="text-align:left;width:2.268cm; " class="Table10_C8"><p class="P7"><span class="T5">1'835</span></p></td><td style="text-align:left;width:2.268cm; " class="Table10_D8"><p class="P7"><span class="T5">6'211</span></p></td><td style="text-align:left;width:2.268cm; " class="Table10_E8"><p class="P7"><span class="T5">510</span></p></td><td style="text-align:left;width:2.267cm; " class="Table10_F8"><p class="P7"><span class="T5">2</span></p></td><td style="text-align:left;width:2.27cm; " class="Table10_G8"><p class="P7"><span class="T26">13'021</span></p></td></tr><tr class="Table103"><td style="text-align:left;width:2.39cm; " class="Table10_A9"><p class="P7"><span class="T5">json</span></p></td><td style="text-align:left;width:2.147cm; " class="Table10_B9"><p class="P7"><span class="T5">8'418</span></p></td><td style="text-align:left;width:2.268cm; " class="Table10_C9"><p class="P7"><span class="T5">0</span></p></td><td style="text-align:left;width:2.268cm; " class="Table10_D9"><p class="P7"><span class="T5">2'567</span></p></td><td style="text-align:left;width:2.268cm; " class="Table10_E9"><p class="P7"><span class="T5">132</span></p></td><td style="text-align:left;width:2.267cm; " class="Table10_F9"><p class="P7"><span class="T5">0</span></p></td><td style="text-align:left;width:2.27cm; " class="Table10_G9"><p class="P7"><span class="T26">11'117</span></p></td></tr><tr class="Table103"><td style="text-align:left;width:2.39cm; " class="Table10_A10"><p class="P7"><span class="T5">wms</span></p></td><td style="text-align:left;width:2.147cm; " class="Table10_B10"><p class="P7"><span class="T5">5'077</span></p></td><td style="text-align:left;width:2.268cm; " class="Table10_C10"><p class="P7"><span class="T5">1'453</span></p></td><td style="text-align:left;width:2.268cm; " class="Table10_D10"><p class="P7"><span class="T5">595</span></p></td><td style="text-align:left;width:2.268cm; " class="Table10_E10"><p class="P7"><span class="T5">3'811</span></p></td><td style="text-align:left;width:2.267cm; " class="Table10_F10"><p class="P7"><span class="T5">95</span></p></td><td style="text-align:left;width:2.27cm; " class="Table10_G10"><p class="P7"><span class="T26">11'031</span></p></td></tr><tr class="Table103"><td style="text-align:left;width:2.39cm; " class="Table10_A11"><p class="P7"><span class="T5">rdf</span></p></td><td style="text-align:left;width:2.147cm; " class="Table10_B11"><p class="P7"><span class="T5">5'849</span></p></td><td style="text-align:left;width:2.268cm; " class="Table10_C11"><p class="P7"><span class="T5">278</span></p></td><td style="text-align:left;width:2.268cm; " class="Table10_D11"><p class="P7"><span class="T5">2'032</span></p></td><td style="text-align:left;width:2.268cm; " class="Table10_E11"><p class="P7"><span class="T5">5</span></p></td><td style="text-align:left;width:2.267cm; " class="Table10_F11"><p class="P7"><span class="T5">0</span></p></td><td style="text-align:left;width:2.27cm; " class="Table10_G11"><p class="P15"><span class="T26">8'164</span></p></td></tr><tr class="Table103"><td style="text-align:left;width:2.39cm; " class="Table10_A12"><p class="P7"><span class="T5">xlsx</span></p></td><td style="text-align:left;width:2.147cm; " class="Table10_B12"><p class="P7"><span class="T5">165</span></p></td><td style="text-align:left;width:2.268cm; " class="Table10_C12"><p class="P7"><span class="T5">0</span></p></td><td style="text-align:left;width:2.268cm; " class="Table10_D12"><p class="P7"><span class="T5">54</span></p></td><td style="text-align:left;width:2.268cm; " class="Table10_E12"><p class="P7"><span class="T5">5'944</span></p></td><td style="text-align:left;width:2.267cm; " class="Table10_F12"><p class="P7"><span class="T5">6</span></p></td><td style="text-align:left;width:2.27cm; " class="Table10_G12"><p class="P15"><span class="T26">6'169</span></p></td></tr><tr class="Table103"><td style="text-align:left;width:2.39cm; " class="Table10_A13"><p class="P7"><span class="T5">Weitere</span></p></td><td style="text-align:left;width:2.147cm; " class="Table10_B13"><p class="P7"><span class="T5">63'824</span></p></td><td style="text-align:left;width:2.268cm; " class="Table10_C13"><p class="P7"><span class="T5">292</span></p></td><td style="text-align:left;width:2.268cm; " class="Table10_D13"><p class="P7"><span class="T5">6'426</span></p></td><td style="text-align:left;width:2.268cm; " class="Table10_E13"><p class="P7"><span class="T5">7'597</span></p></td><td style="text-align:left;width:2.267cm; " class="Table10_F13"><p class="P7"><span class="T5">1'738</span></p></td><td style="text-align:left;width:2.27cm; " class="Table10_G13"><p class="P15"><span class="T26">79'877</span></p></td></tr><tr class="Table103"><td style="text-align:left;width:2.39cm; " class="Table10_A14"><p class="P7"><span class="T23">Gesamtdaten</span></p></td><td style="text-align:left;width:2.147cm; " class="Table10_B14"><p class="P7"><span class="T23">182'918</span></p></td><td style="text-align:left;width:2.268cm; " class="Table10_C14"><p class="P7"><span class="T23">10'974</span></p></td><td style="text-align:left;width:2.268cm; " class="Table10_D14"><p class="P7"><span class="T23">37'318</span></p></td><td style="text-align:left;width:2.268cm; " class="Table10_E14"><p class="P7"><span class="T23">33'000</span></p></td><td style="text-align:left;width:2.267cm; " class="Table10_F14"><p class="P7"><span class="T23">1'905</span></p></td><td style="text-align:left;width:2.27cm; " class="Table10_G14"><p class="P15"><span class="T23">266'115</span></p></td></tr></table>

*Tabelle 2: Anzahl Formate in div. Portalen, sortiert nach Gesamtsumme
mit Stichtag 23.04.2015*

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
