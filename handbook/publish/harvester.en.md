---
Title: Harvester
Category: Publish
Handbook: yes
Tags:
Date: 2016-08-03
Slug: harvester
Authors:
Lang: en
Draft: yes
toc_run: true
Summary: Harvesters are an easy way to publish large numbers of datasets. The only requirement is to have metadata available in the DCAT-AP Switzerland format via a URL.
---

<a name="harvester"></a>
# Harvester

If you have a rather large amount of datasets (>= 100), you can use our harvesters to automatically update them at regular intervals.

All metadata must be available in the [DCAT-AP for Switzerland format](/en/library/ch-dcat-ap). You must provide a catalog as an RDF file ([see the example](/samples/ogdch_dcatap_import.rdf) for reference).

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

The RDF XML harvester is [based on ckanext-dcat](https://github.com/ckan/ckanext-dcat#rdf-dcat-harvester>). As a publisher you must provide a valid catalog endpoint to fetch all datasets.
If the amount of datasets exeeds best practices to be fetched in one request (e.g. more than 1'000 datasets), it is recommend to implement pagination using the [Hydra vocabulary](http://www.w3.org/ns/hydra/spec/latest/core/).

```xml

  @prefix hydra: <http://www.w3.org/ns/hydra/core#> .
  
  <http://example.com/catalog.rdf?page=1> a hydra:PagedCollection ;
      hydra:firstPage "http://example.com/catalog.rdf?page=1" ;
      hydra:itemsPerPage 100 ;
      hydra:lastPage "http://example.com/catalog.rdf?page=3" ;
      hydra:nextPage "http://example.com/catalog.rdf?page=2" ;
      hydra:totalItems 283 .
```

