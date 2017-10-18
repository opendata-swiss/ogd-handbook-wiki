---
Title: Harvester
Category: Support
Handbook: yes
Tags:
Date: 2016-08-03
Slug: harvester
Authors:
Lang: en
Draft: yes
toc_run: false
Summary: Harvesters are an easy way to publish large numbers of datasets. The only requirement is to have metadata available in the DCAT-AP Switzerland format via a URL.
---

If you have a rather large amount of datasets (>= 100), you can use our harvesters to automatically update them at regular intervals.

All metadata must be available in the [DCAT-AP Switzerland format](/en/library/ch-dcat-ap). You must provide a catalog as an RDF file ([see the example](/samples/ogdch_dcatap_import.rdf) for reference).

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

The RDF XML harvester is [based on ckanext-dcat](https://github.com/ckan/ckanext-dcat#rdf-dcat-harvester). As a publisher you must provide a valid catalog endpoint to fetch all datasets.
If the amount of datasets exeeds best practices to be fetched in one request (e.g. more than 1'000 datasets), it is recommend to implement pagination using the [Hydra vocabulary](http://www.w3.org/ns/hydra/spec/latest/core/).

Example:

```xml
  <hydra:PagedCollection rdf:about="http://opendata.swiss/catalog.xml?page=3">
    <hydra:lastPage>http://opendata.swiss/catalog.xml?page=4</hydra:lastPage>
    <hydra:itemsPerPage rdf:datatype="http://www.w3.org/2001/XMLSchema#integer">1000</hydra:itemsPerPage>
    <hydra:totalItems rdf:datatype="http://www.w3.org/2001/XMLSchema#integer">3479</hydra:totalItems>
    <hydra:firstPage>http://opendata.swiss/catalog.xml?page=1</hydra:firstPage>
    <hydra:previousPage>http://opendata.swiss/catalog.xml?page=2</hydra:previousPage>
  </hydra:PagedCollection>
```
