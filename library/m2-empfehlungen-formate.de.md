Title: Empfehlungen für OGD Formate
Category: Library
Template: document
Tags: publish
Date: 2015-11-10
Slug: m2-empfehlungen-formate
Authors:
Summary:
Lang: de
Hidden: yes


Um das Potential von offenen Behördendaten nutzen zu können, müssen
diese in Formaten bereitgestellt werden, welche
möglichst einfach zu verwenden sind. Unter offenen Behördendaten
versteht man Datensätze, die kostenfrei und im Idealfall in
maschinenlesbarer Form zur Sekundärnutzung allen Interessierten zur
Verfügung stehen. Das vorliegende Dokument
definiert Kriterien für die Publikation von Datensätzen im OGD Portal
und gibt Empfehlungen zu spezifischen Formaten und Schnittstellen ab.


Die OGD-Strategie Schweiz definiert die drei Ziele „Freigabe von
Behördendaten“, „Koordinierte Publikation und Bereitstellung der
Behördendaten“ und „Etablierung einer Open-Data-Kultur“ (siehe [\#1, OGD
Strategie Schweiz 2014 – 2018](#_Referenzen)). Für die zu verwendenden
Formate werden im Ziel „Freigabe von Behördendaten“ klare Vorgaben
gemacht:

„Der Bund stellt der Öffentlichkeit seine für OGD geeigneten Daten in
*maschinenlesbaren* und *offenen Formaten* zur freien Weiterverwendung
zur Verfügung.“ (\#1, S. 3499)

Diese Kriterien finden ihre Entsprechung im Grundsatz 2 „Offene und
wiederverwendbare Behördendaten“:

„Die Daten werden in *maschinenlesbarer Form* angeboten, verständlich
und zweckmässig beschrieben und dauerhaft zur Verfügung gestellt. Es
sollen möglichst *offene Formate* angewandt werden.“ (\#1, S. 3502)


Im vorliegenden Dokument werden die Kriterien „maschinenlesbar“ und
„offen“ genauer beschrieben sowie die Bedeutung von "verständlich und
zweckmässig beschrieben" erläutert. Davon abgeleitet werden Empfehlungen
zur Publikation von Datensätzen abgegeben.

**Ziel des Dokuments**

Dieses Dokument beschreibt die Kriterien für Formate und
Austauschformen, in denen die Daten auf der OGD-Plattform zugänglich
sein sollen, und gibt Empfehlungen bezüglich der zu verwendenden Formate
ab. Die Liste der empfohlenen Formate ist nicht abschliessend. Es gilt
der Grundsatz, dass eine Datenpublikation in irgendeinem Format
wünschenswerter, ist als keine Publikation.


**Zielpublikum**

Das Dokument richtet sich an Datenproduzenten und Datenlieferanten bzw.
die Institutionen, die Daten als OGD zur Verfügung stellen wollen.

Üblicherweise wird zur Illustration in der Diskussion um *Open Data* und
*Linked Data* auf das Fünf-Sterne-Modell von Tim Berners-Lee verwiesen
(siehe [\#4, Berners Lee, Tim, Linked Data](#_Referenzen)). Gemäss
diesem Modell lassen sich *Open Data* in fünf Stufen unterteilen, wobei
die ersten drei Stufen im Wesentlichen *Open Data* und die zwei letzten
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

```
  ------- ------------------------------------------------------------------------------------
  ★       Datenpublikation mit offener Lizenz in irgendeinem Format
  ★★      Datenpublikation in einem strukturierten Format (bspw. Excel statt Tabelle in PDF)
  ★★★     Datenpublikation in einem offenen Format (bspw. CSV statt Excel)
  ★★★★    Verwendung von eindeutigen Identifikatoren (URI) für Entitäten
  ★★★★★   Verlinkung der publizierten Daten mit anderen Daten, um Kontext zu schaffen
  ------- ------------------------------------------------------------------------------------
```

**Tabelle 1:** <span style="font-weight: normal">Aus [\#2, Open
Government Data – Grundlagenstudie Schweiz, S. 86](#_Referenzen); [\#5,
5](#_Referenzen)</span>[<span style="font-weight: normal">★</span><span
style="font-weight: normal"> Open Data (Webseite)</span>](#_Referenzen)



Am wichtigsten ist, dass die Datensätze mit offener Lizenz publiziert
werden. Für verschiedene Nutzer können hingegen verschiedene Formate
angeboten werden, um den spezifischen Anforderungen der Nutzer gerecht
zu werden.


Die zentralen Kriterien für die Datenpublikation im OGD-Portal sind
Maschinenlesbarkeit und Offenheit (siehe [\#1 OGD Strategie
Schweiz](#_Referenzen)). Diese Kriterien Maschinenlesbarkeit und
Offenheit sind im Folgenden rot gekennzeichnet und werden in Abschnitt
3.2 bei den Formatempfehlungen explizit berücksichtigt.


## Maschinenlesbarkeit

Das Format und die enthaltenen Daten können von einem Programm
automatisiert verarbeitet werden.

"Maschinenlesbar ist ein [...] Format, das so strukturiert ist, dass
Softwareanwendungen konkrete Daten, einschließlich einzelner
Sachverhaltsdarstellungen und deren interner Struktur, leicht
identifizieren, erkennen und extrahieren können".


Mit dieser Definition ist beispielsweise eine Textdatei erst dann
maschinenlesbar, wenn die darin enthaltenen Daten so strukturiert
dargestellt sind, dass sie mit einem passenden Algorithmus (Programm)
korrekt interpretiert und verarbeitet werden können. Ein (X)HTML-Text
(eine Webseite) ist demnach nicht maschinenlesbar - ein Browser kann die
Inhalte nur für Menschen lesbar auf dem Bildschirm darstellen. Erst wenn
die Inhalte der Webseite semantisch strukturiert ausgezeichnet werden
(z.B. unter Verwendung des Vokabulars schema.org), können die Inhalte
von einem Programm als Datenstrukturen erkannt und entsprechend
verarbeitet werden. Ausserdem ist bei textbasierten Formaten eine
standardisierte Zeichenkodierung notwendig (wenn möglich UTF-8), um auch
spezielle Zeichen (z.B. Umlaute) korrekt interpretieren zu können.


Um einen passenden Algorithmus zur Verarbeitung der strukturierten Daten
programmieren zu können, ist das maschinenlesbare Format noch nicht
ausreichend. Die Daten müssen zusätzlich "verständlich und zweckmässig
beschrieben" sein. Falls die Struktur der Daten einem Standard folgt,
genügt die Angabe des betreffenden Standards (z.B. schema.org).
Andernfalls muss die Beschreibung der Datenstruktur in die Metadaten
integriert werden.


## Offenheit

Die Spezifikation des Formats ist offen gelegt und öffentlich
zugänglich.

"Offen ist ein Dateiformat, das plattformunabhängig ist und der
Öffentlichkeit ohne Einschränkungen, die der Weiterverwendung von
Dokumenten hinderlich wären, zugänglich gemacht
wird".


Die Offenheit bzw. die Zugänglichkeit der Spezifikation ist für die
lückenlose Interpretierbarkeit der durch das Format kodierten
Information entscheidend. Dazu gehört auch, dass der Standard
verständlich, überschaubar und eindeutig sein soll; dass dieser Standard
lizenzfrei ist und weit verbreitet ist.\
 Dieses Kriterium muss erfüllt sein, damit ein Format als offen gelten
kann.


Beide Kriterien Maschinenlesbarkeit und Offenheit weisen mehrere
Dimensionen auf, die im Folgenden beschrieben werden. Die nachfolgenden,
blau gekennzeichneten Dimensionen, sollen von den Datenlieferanten bei
der Auswahl geeigneter Formate, bzw. Austauschformen für ihre Datensätze
mitberücksichtigt werden.


## Standard

Das Format wird durch ein Standardgremium periodisch überprüft und
aktualisiert (international, national).

Die Standards von (inter-)nationalen Organisationen sind langlebiger und
weniger revisionsanfällig, verleihen einem Format also Stabilität. Ein
Standardgremium ist grundsätzlich unabhängiger und glaubwürdiger als
eine einzelne Firma, welche die Rechte an einem Format besitzt.


## Lizenzfrei

Formate sind nicht durch auferlegte Lizenzen in der Herstellung oder
Benutzung limitiert.

Verhinderung einer Herstellerabhängigkeit. Verminderung bzw.
Ausschaltung des potentiellen Risikos, dass der Lizenzinhaber jederzeit
Änderungen vornehmen und durchsetzen kann.


## Verbreitung

Das Format ist weit verbreitet.

Grosse Verbreitung bedeutet eine zum heutigen Zeitpunkt abschätzbare
relativ grosse Benutzerzahl wie auch eine gewisse Diversität der
Benutzer, eine grosse Anzahl existierender Dateien im entsprechenden
Format, Unterstützung des Formats durch viele voneinander unabhängige
Applikationen und Programmbibliotheken. Ebenso ist die geografische
Verbreitung gemeint.

(( chart here ))

Download: (( link to PDF ))
