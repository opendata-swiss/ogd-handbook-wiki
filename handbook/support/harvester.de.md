---
Title: Harvester
Category: Support
Handbook: yes
Tags:
Date: 2016-08-03
Slug: harvester
Authors:
Lang: de
Draft: yes
toc_run: true
Summary: Mit einem Harvester lassen sich grössere Datenmengen einfach und schnell publizieren. Voraussetzung dafür sind Metadaten im Format DCAT-AP Switzerland, welche über eine URL verfügbar sind.
---

<a name="harvester"></a>
# Harvester

Bei grösseren Mengen an Datensätzen (>= 100), können Harvester verwendet werden um die Datensätze regelmässig zu aktualisieren.

Die Metadatan müssen dazu im [DCAT-AP Switzerland format](/de/library/ch-dcat-ap) vorliegen. Sie müssen einen Katalog als RDF-Datei zur Verfügung stellen ([Beispiel RDF](/samples/ogdch_dcatap_import.rdf)).

```xml
  <rdf:RDF>
    <dcat:Catalog>
      <dcat:dataset>
        <dcat:Dataset>
        ...
        </dcat:Dataset>
      </dcat:dataset>
      <dcat:dataset>
        <dcat:Dataset>
        ...
        </dcat:Dataset>
      </dcat:dataset>
      <dcat:dataset>
        <dcat:Dataset>
        ...
        </dcat:Dataset>
      </dcat:dataset>
      ...
    </dcat:Catalog>
  </rdf:RDF>
```

Der RDF XML Harvester [basiert auf der CKAN-Extension ckanext-dcat](https://github.com/ckan/ckanext-dcat#rdf-dcat-harvester). Als Datenlieferant müssen Sie einen gültigen "catalog endpoint" für alle Datensätze zur Verfügung stellen.
Falls Sie so viele Datensätze anbieten, dass sich diese nicht mehr mit einer einzigen Anfrage holen lassen (z.B. mehr als 1'000 Datensätze), ist die Empfehlung Pagination mit dem [Hydra Vocabulary](http://www.w3.org/ns/hydra/spec/latest/core/) zu implementieren.

Beispiel:

```xml
  <hydra:PagedCollection rdf:about="http://opendata.swiss/catalog.xml?page=3">
    <hydra:lastPage>http://opendata.swiss/catalog.xml?page=4</hydra:lastPage>
    <hydra:itemsPerPage rdf:datatype="http://www.w3.org/2001/XMLSchema#integer">1000</hydra:itemsPerPage>
    <hydra:totalItems rdf:datatype="http://www.w3.org/2001/XMLSchema#integer">3479</hydra:totalItems>
    <hydra:firstPage>http://opendata.swiss/catalog.xml?page=1</hydra:firstPage>
    <hydra:previousPage>http://opendata.swiss/catalog.xml?page=2</hydra:previousPage>
  </hydra:PagedCollection>
```
