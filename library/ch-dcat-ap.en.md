---
Title: DCAT-AP for Switzerland format
Category: Library
Template: document
Tags: publish
Date: 2016-02-09
Slug: ch-dcat-ap
Summary:
Lang: en
toc_run: true
Link_RDF: /samples/ogdch_dcatap_import.rdf
---

The ‹Open Government Data› project organisation have worked out a joint solution for metadata. The portal opendata.swiss implements these standards - see [Publish on opendata.swiss](/en/publish/opendata-swiss).

Have a look at the following file for a quickstart: [full dataset example](/samples/ogdch_dcatap_import.rdf) (RDF)

### Namespaces

```xml
<rdf:RDF
  xmlns:dct="http://purl.org/dc/terms/"
  xmlns:dc="http://purl.org/dc/elements/1.1/"
  xmlns:dcat="http://www.w3.org/ns/dcat#"
  xmlns:foaf="http://xmlns.com/foaf/0.1/"
  xmlns:xsd="http://www.w3.org/2001/XMLSchema#"
  xmlns:rdfs="http://www.w3.org/2000/01/rdf-schema#"
  xmlns:rdf="http://www.w3.org/1999/02/22-rdf-syntax-ns#"
  xmlns:vcard="http://www.w3.org/2006/vcard/ns#"
  xmlns:odrs="http://schema.theodi.org/odrs#"
  xmlns:schema="http://schema.org/">
```

### Internationalisation

The DCAT-AP for Switzerland Standard expects that text elements of the datasets and their distributions be translated in the following four languages:
* French (fr)
* German (de)
* Italian (it)
* English (en)

The multi-lingual elements have to contain the `xml:lang` attribute, as the following example show:

```xml
<dct:title xml:lang="fr">FR Titre</dct:title>
<dct:title xml:lang="de">DE Titel</dct:title>
<dct:title xml:lang="it">IT Titolo</dct:title>
<dct:title xml:lang="en">EN Title</dct:title>
```

### DCAT-AP reference documentation

#### Definition of `dcat:Catalog`

|             |             |
|-------------|-------------|
| Content     | Contains nested elements of type `<dcat:dataset>` |
| Mandatory   | yes         |
| Cardinality | 1..1        |
| Attributes  |             |
| Description | Catalog with datasets |

Example:
```xml
<dcat:Catalog>
    <dcat:dataset>
        [...]
    </dcat:dataset>
    [further dcat:dataset]
</dcat:Catalog>
```

##### `dcat:dataset`

|             |             |
|-------------|-------------|
| Content     | Contains single nested element of type `dcat:Dataset`. See [Definition of dcat:Dataset](#definition-of-dataset). |
| Mandatory   | yes         |
| Cardinality | 1..n        |
| Attributes  |             |
| Description | Wrapper for a dataset of the catalog |

Example:
```xml
<dcat:dataset>
    <dcat:Dataset rdf:about="http://swisstopo/325">
        [Content of dataset]
    </dcat:Dataset>
</dcat:dataset>
[further dcat:dataset]
```

<a name="definition-of-dataset"></a>
#### Definition of `dcat:Dataset`

|             |             |             |
|-------------|-------------|-------------|
| Mandatory   | yes         |             |
| Cardinality | 1..1        |             |
| Attributes  | Name        | `rdf:about`  |
|             | Content     | Unique identifier for dataset |
|             | Mandatory   | yes         |
| Description | A single dataset of the catalog |             |

Example:
```xml
<dcat:Dataset rdf:about="http://swisstopo/325">
    [Content of dataset]
</dcat:Dataset>
```

##### `dct:identifier`

|             |             |
|-------------|-------------|
| Type        | `rdfs:Literal` http://www.w3.org/TR/rdf-schema/#ch_literal |
| Mandatory   | yes         |
| Cardinality | 1..1        |
| Description | Unique identifier of the dataset across all publishers. A good way to make sure this identifier is unique is to link the source system ID with the ID of the publisher: `[Source-Dataset-ID]@[Source-Organisation-ID]`. It is recommended that the identifier consists out of the following characters: `A-Za-z`, `0-9` without special characters, except `-` and `_` |

Example:
```xml
<dct:identifier>325@swisstopo</dct:identifier>
```

##### `dct:title`

|             |             |             |
|-------------|-------------|-------------|
| Type        | `rdfs:Literal` http://www.w3.org/TR/rdf-schema/#ch_literal |             |
| Mandatory   | yes         |             |
| Cardinality | 1..n (one for each language) |             |
| Attributes  | Name        | `xml:lang`  |
|             | Content     | `en`, `de`, `fr`, `it` |
|             | Description | Language of the element |
|             | Mandatory   | yes         |
| Description | Title of the dataset in the language defined by the `xml:lang` attribute |             |

Example:
```xml
<dct:title xml:lang="de">Eisenbahnlärm Nacht</dct:title>
```

##### `dct:description`

|             |             |             |
|-------------|-------------|-------------|
| Type        | `rdfs:Literal` http://www.w3.org/TR/rdf-schema/#ch_literal |             |
| Mandatory   | yes - in all the languages in which [distributions](#definition-of-distribution) are available |             |
| Cardinality | 1..n (one for each language) |             |
| Attributes  | Name        | `xml:lang`     |
|             | Content     | `en`, `de`, `fr`, `it` |
|             | Description | Language of the element |
|             | Mandatory   | yes         |
| Description | Description of the dataset in the language defined by the `xml:lang` attribute |             |

Example:
```xml
<dct:description xml:lang="de">Die Karte zeigt, welcher Lärmbelastung die Bevölkerung durch den Schienenverkehr ausgesetzt ist.</dct:description>
```

##### `dct:issued`

|             |             |             |
|-------------|-------------|-------------|
| Type        | Date and time in [ISO-8601](https://en.wikipedia.org/wiki/ISO_8601) format |             |
| Mandatory   | Can be left out if there is no [distribution](#definition-of-distribution) |             |
| Cardinality | 0..1        |             |
| Attributes  | Name        | `rdf:datatype` |
|             | Content     | http://www.w3.org/2001/XMLSchema#dateTime |
|             | Description | Type of the field |
|             | Mandatory   | yes         |
| Description | Date of the first publication of this dataset. If this date is unknown, the date of the first publication on opendata.swiss can be used. If that date is in the future, the dataset is not displayed. |             |

Example:
```xml
<dct:issued rdf:datatype="http://www.w3.org/2001/XMLSchema#dateTime"> 2013-04-26T01:00:00Z</dct:issued>
```

##### `dct:modified`

|             |             |             |
|-------------|-------------|-------------|
| Type        | Date and time in [ISO-8601](https://en.wikipedia.org/wiki/ISO_8601) format |             |
| Mandatory   | Only when the dataset has changed since the first publication |             |
| Cardinality | 0..1        |             |
| Attributes  | Name        | `rdf:datatype` |
|             | Content     | http://www.w3.org/2001/XMLSchema#dateTime |
|             | Description | Type of the field |
|             | Mandatory   | yes         |
| Description | Date of the last change (since the first publication on opendata.swiss) |             |

Example:
```xml
<dct:modified rdf:datatype="http://www.w3.org/2001/XMLSchema#dateTime"> 2013-04-26T01:00:00Z</dct:modified>
```

##### `dct:publisher`

|             |             |
|-------------|-------------|
| Elements    | `rdf:Description` |
| Type        | Nested element |
| Mandatory   | yes         |
| Cardinality | 1..n        |
| Description | The publishers of the dataset. `rdf:about` is an optional attribute. |

Example:
```xml
<dct:publisher>
    <rdf:Description rdf:about="https://www.bafu.admin.ch/">
        <rdfs:label>Bundesamt für Landestopografie swisstopo</rdfs:label>
    </rdf:Description>
</dct:publisher>
```

##### `dct:contactPoint`

|             |             |
|-------------|-------------|
| Elements    | `vcard:Organization` |
| Type        | `vcard:Kind` |
| Mandatory   | yes         |
| Cardinality | 1..n        |
| Description | One or more contact email addresses for this dataset `vcard:fn`. Description of the point of contact `vcard:hasEmail` has an attribute `rdf:resource` which contains the email of the point of contact (including mailto:) |

Example:
```xml
<dcat:contactPoint>
    <vcard:Organization>
        <vcard:fn>Abteilung Lärm BAFU</vcard:fn>
        <vcard:hasEmail rdf:resource="mailto:noise@bafu.admin.ch"/>
    </vcard:Organization>
</dcat:contactPoint>

<dcat:contactPoint>
    <vcard:Individual>
        <vcard:fn>Sekretariat BAFU</vcard:fn>
        <vcard:hasEmail rdf:resource="mailto:sekretariat@bafu.admin.ch"/>
    </vcard:Individual>
</dcat:contactPoint>
```

##### `dct:theme`

|             |             |             |
|-------------|-------------|-------------|
| Type        | `skos:Concept` http://www.w3.org/2009/08/skos-reference/skos.html#Concept |             |
| Mandatory   | yes         |             |
| Cardinality | 1..n        |             |
| Attributes  | Name        | `rdf:resource` |
|             | Description | URI to the category |
|             | Mandatory   | yes         |
| Description | Categorisation of the data. In the `rdf:resource` attribute, the unique URI of the category from [SKOS-RDF](/samples/opendataswiss-themes.rdf) (RDF) must be given. The following values are accepted from Themes: <ul><li>http://opendata.swiss/themes/work</li><li>http://opendata.swiss/themes/construction</li><li>http://opendata.swiss/themes/population</li><li>http://opendata.swiss/themes/education</li><li>http://opendata.swiss/themes/energy</li><li>http://opendata.swiss/themes/finances</li><li>http://opendata.swiss/themes/geography</li><li>http://opendata.swiss/themes/legislation</li><li>http://opendata.swiss/themes/health</li><li>http://opendata.swiss/themes/trade</li><li>http://opendata.swiss/themes/industry</li><li>http://opendata.swiss/themes/crime</li><li>http://opendata.swiss/themes/culture</li><li>http://opendata.swiss/themes/agriculture</li><li>http://opendata.swiss/themes/mobility</li><li>http://opendata.swiss/themes/public-order</li><li>http://opendata.swiss/themes/politics</li><li>http://opendata.swiss/themes/prices</li><li>http://opendata.swiss/themes/territory</li><li>http://opendata.swiss/themes/social-security</li><li>http://opendata.swiss/themes/statistical-basis</li><li>http://opendata.swiss/themes/tourism</li><li>http://opendata.swiss/themes/administration</li><li>http://opendata.swiss/themes/national-economy</li></ul> |             |

Example:
```xml
<dcat:theme rdf:resource="http://opendata.swiss/themes/population"/>
```

##### `dct:language`

|             |             |
|-------------|-------------|
| Type        | `rdfs:Literal` ISO 639-1 two-letter code |
| Content     | `en`, `de`, `fr`, `it` |
| Mandatory   | no          |
| Cardinality | 0..n (for each language) |
| Attributes  |             |
| Description | Should contain all languages for which a [distribution](#definition-of-distribution) is available. This field is not validated and is used for display purposes. If all distributions are language-independant, this field can be left out. |

Example:
```xml
<dct:language>de</dct:language>
```

##### `dct:relation`

|             |             |
|-------------|-------------|
| Elements    | `rdf:Description` |
| Type        | Nested element |
| Mandatory   | no          |
| Cardinality | 0..n        |
| Description | A relation to a document. The `rdf:about` must link to a related document. |

Example:
```xml
<dct:relation>
    <rdf:Description rdf:about="http://www.bafu.admin.ch/laerm/index.html?lang=de">
        <rdfs:label>Webseite des BAFU</rdfs:label>
    </rdf:Description>
</dct:relation>
```

##### `dcat:keyword`

|             |             |             |
|-------------|-------------|-------------|
| Type        | `rdfs:Literal` http://www.w3.org/TR/rdf-schema/#ch_literal |             |
| Mandatory   | no          |             |
| Cardinality | 0..n        |             |
| Attributes  | Name        | `xml:lang` |
|             | Content     | `en`, `de`, `fr`, `it` |
|             | Description | Language of the element |
|             | Mandatory   | yes         |
| Description | Keyword who describes this dataset |             |

Example:
```xml
<dcat:keyword xml:lang="de">Nacht</dcat:keyword>
<dcat:keyword xml:lang="fr">Nuit</dcat:keyword>
<dcat:keyword xml:lang="it">Noche</dcat:keyword>
<dcat:keyword xml:lang="en">Night</dcat:keyword>
```

##### `dcat:landingPage`

|             |             |
|-------------|-------------|
| Type        | `foaf:Document` http://xmlns.com/foaf/spec/#term_Document |
| Mandatory   | no          |
| Cardinality | 0..1        |
| Attributes  |             |
| Description | Website of the dataset with related information |

Example:
```xml
<dcat:landingPage>http://www.bafu.admin.ch/laerm/index.html?lang=de</dcat:landingPage>
```

##### `dcat:spatial`

|             |             |
|-------------|-------------|
| Type        | `dct:Location` http://dublincore.org/documents/2012/06/14/dcmi-terms/?v=terms#Location |
| Mandatory   | no          |
| Cardinality | 0..n        |
| Attributes  |             |
| Description | Geographical classification of the dataset. Can be a description, coordinates, a bounding-box or a polygon. This field currently supports GeoJSON with the [LOCN extension](https://www.w3.org/community/locadd/wiki/LOCN_extension:_Metadata). |

Example:
```xml
<dct:spatial rdf:resource="http://publications.europa.eu/mdr/authority/country/ZWE"/>
<dct:spatial>Bern</dct:spatial>
<dct:spatial>
  <dct:Location>
    <locn:geometry rdf:datatype="https://www.iana.org/assignments/media-types/application/vnd.geo+json">
    <![CDATA[
      {
        "type":"Polygon",
        "crs":{"type":"name","properties":{"name":"urn:ogc:def:crs:OGC:1.3:CRS84"}},
        "coordinates":[[[-6.41736,55.7447],[2.05827,55.7447],[2.05827,49.8625],[-6.41736,49.8625],[-6.41736,55.7447]]]
      }
    ]]>
    </locn:geometry>
  </dct:Location>
</dct.spatial>
```

See also: [How should dct:spatial and dct:Location be used?](https://joinup.ec.europa.eu/release/how-should-dctspatial-and-dctlocation-be-used)

##### `dcat:coverage`

|             |             |
|-------------|-------------|
| Type        | `dct:LocationPeriodOrJurisdiction` http://dublincore.org/documents/2012/06/14/dcmi-terms/?v=terms#LocationPeriodOrJurisdiction |
| Mandatory   | no          |
| Cardinality | 0..n        |
| Attributes  |             |
| Description | This field is currently not used, use `dcat:spatial` instead. |

Example:
```xml
<dct:coverage/>
```

##### `dcat:temporal`

|             |             |
|-------------|-------------|
| Type        | `dct:PeriodOfTime` http://dublincore.org/documents/2012/06/14/dcmi-terms/?v=terms#terms-PeriodOfTime |
| Mandatory   | no          |
| Cardinality | 0..n        |
| Attributes  |             |
| Description | One or more time period(s) that cover the dataset. `<schema:startDate>` contains the start date, `<schema:endDate>` contains the end date format for dates: http://www.w3.org/2001/XMLSchema#date |

Example:
```xml
<dct:temporal>
    <dct:PeriodOfTime>
        <schema:startDate rdf:datatype="http://www.w3.org/2001/XMLSchema#date">1905-03-01</schema:startDate>
        <schema:endDate rdf:datatype="http://www.w3.org/2001/XMLSchema#date">2013-01-05</schema:endDate>
    </dct:PeriodOfTime>
</dct:temporal>
```

##### `dct:accrualPeriodicity`

|             |             |             |
|-------------|-------------|-------------|
| Mandatory   | no          |             |
| Cardinality | 0..n        |             |
| Attributes  | Name        | `rdf:resource` |
|             | Type        | `dct:Frequency` |
|             | Mandatory   | yes         |
| Description | The frequency in which this dataset is updated. Values for `dct:Frequency`: http://dublincore.org/groups/collections/frequency/ |             |

Example:
```xml
<dct:accrualPeriodicity rdf:resource="http://purl.org/cld/freq/daily"/>
```

##### `rdfs:seeAlso`

|             |             |
|-------------|-------------|
| Type        | `rdfs:Literal` http://www.w3.org/TR/rdf-schema/#ch_literal |
| Mandatory   | no          |
| Cardinality | 0..n        |
| Attributes  |             |
| Description | Link to related datasets. Contains the identifier of the linked dataset. |

Example:
```xml
<rdfs:seeAlso>326@swisstopo</rdfs:seeAlso>
```

##### `dcat:distribution`

|             |             |
|-------------|-------------|
| Content     | Contains single nested element of type `dcat:Distribution`. See [Definition of `dcat:Distribution`](#definition-of-distribution). |
| Mandatory   | yes         |
| Cardinality | 1..n        |
| Attributes  |             |
| Description | Wrapper for a distribution of the dataset |

Example:
```xml
<dcat:distribution>
    <dcat:Distribution rdf:about="http://swisstopo/325/ch.bafu.laerm-bahnlaerm_nacht">
        [Content of distribution]
    </dcat:Distribution>
</dcat:distribution>
[further distributions]
```

<a name="definition-of-distribution"></a>
#### Definition of `dcat:Distribution`

|             |             |             |
|-------------|-------------|-------------|
| Mandatory   | yes         |             |
| Cardinality | 1..1        |             |
| Attributes  | Name        | `rdf:about`  |
|             | Content     | Unique identifier for distribution |
|             | Mandatory   | yes         |
| Description | A single distribution of the dataset |             |

Example:
```xml
<dcat:Distribution rdf:about="http://swisstopo/325/ch.bafu.laerm-bahnlaerm_nacht">
    [Content of distribution]
</dcat:Distribution>
```

##### `dcat:identifier`

|             |             |
|-------------|-------------|
| Type        | `rdfs:Literal` http://www.w3.org/TR/rdf-schema/#ch_literal |
| Mandatory   | no          |
| Cardinality | 0..1        |
| Attributes  |             |
| Description | Identifier of the distribution in the source system |

Example:
```xml
<dct:identifier>ch.bafu.laerm-bahnlaerm_nacht</dct:identifier>
```

##### `dcat:title`

|             |             |             |
|-------------|-------------|-------------|
| Type        | `rdfs:Literal` http://www.w3.org/TR/rdf-schema/#ch_literal |             |
| Mandatory   | no - except if the distribution does not contain all the content of the dataset. |             |
| Cardinality | 0..n (one for each language) |             |
| Attributes  | Name        | `xml:lang`  |
|             | Content     | `en`, `de`, `fr`, `it` |
|             | Description | Language of the element |
|             | Mandatory   | yes         |
| Description | The title of the distribution in the language defined by the `xml:lang?` attribute. If this element is left out, the `dct:title` of the dataset is used instead. |             |

Example:
```xml
<dct:title xml:lang="de">WMS (ch.bafu.laerm-bahnlaerm_nacht)</dct:title>
```

##### `dct:description`

|             |             |             |
|-------------|-------------|-------------|
| Type        | `rdfs:Literal` http://www.w3.org/TR/rdf-schema/#ch_literal |             |
| Mandatory   | no - except if the distribution does not contain all the content of the dataset. |             |
| Cardinality | 0..n (one for each language) |             |
| Attributes  | Name        | `xml:lang`  |
|             | Content     | `en`, `de`, `fr`, `it` |
|             | Description | Language of the element |
|             | Mandatory   | yes         |
| Description | Description of the distribution in the language defined by the `xml:lang` attribute |             |

Example:
```xml
<dct:title xml:lang="de">WMS (ch.bafu.laerm-bahnlaerm_nacht)</dct:title>
```

##### `dct:issued`

|             |             |             |
|-------------|-------------|-------------|
| Type        | Date and time in [ISO-8601](https://en.wikipedia.org/wiki/ISO_8601) format |             |
| Mandatory   | yes         |             |
| Cardinality | 1..1        |             |
| Attributes  | Name        | `rdf:datatype` |
|             | Content     | http://www.w3.org/2001/XMLSchema#dateTime |
|             | Description | Type of the field |
|             | Mandatory   | yes         |
| Description | Date of the publication of this distribution |             |

Example:
```xml
<dct:issued rdf:datatype="http://www.w3.org/2001/XMLSchema#dateTime"> 2013-05-11T00:00:00Z</dct:issued>
```

##### `dct:modified`

|             |             |             |
|-------------|-------------|-------------|
| Type        | Date and time in [ISO-8601](https://en.wikipedia.org/wiki/ISO_8601) format |             |
| Mandatory   | Only when the distribution has changed since the first publication. If this distribution was changed several times, this corresponds to the date of the latest change. |             |
| Cardinality | 0..1        |             |
| Attributes  | Name        | `rdf:datatype` |
|             | Content     | http://www.w3.org/2001/XMLSchema#dateTime |
|             | Description | Type of the field |
|             | Mandatory   | yes         |
| Description | Date of the last change of the distribution |             |

Example:
```xml
<dct:modified rdf:datatype="http://www.w3.org/2001/XMLSchema#dateTime"> 2015-04-26T00:00:00Z</dct:modified>
```

##### `dct:language`

|             |             |             |
|-------------|-------------|-------------|
| Type        | `rdfs:Literal` ISO 639-1 two-letter code |             |
| Content     | `en`, `de`, `fr`, `it` |             |
| Mandatory   | no          |             |
| Cardinality | 0..n (for each language) |             |
| Attributes  |             |             |
| Description | Languages in which this distribution is available. If the distribution is language-independant, this can be left out. |             |

Example:
```xml
<dct:language>de</dct:language>
```

##### `dcat:accessURL`

|             |             |             |
|-------------|-------------|-------------|
| Type        | http://www.w3.org/2001/XMLSchema#anyURI |             |
| Mandatory   | yes         |             |
| Cardinality | 1..n        |             |
| Attributes  | Name        | `rdf:datatype` |
|             | Content     | http://www.w3.org/2001/XMLSchema#anyURI |
|             | Description | Type of the field |
|             | Mandatory   | yes         |
| Description | URL where the distribution can be found. This could be either a download URL, an API URL or a landing page URL. If the distribution is only available through a landing page, this field must contain the URL of the landing page. If a download URL was given for this distribution, this field has to contain the same value. |             |

Example:
```xml
<dcat:accessURL rdf:datatype="http://www.w3.org/2001/XMLSchema#anyURI"> http://wms.geo.admin.ch/</dcat:accessURL>
```

##### `dct:downloadURL`

|             |             |             |
|-------------|-------------|-------------|
| Type        | http://www.w3.org/2001/XMLSchema#anyURI |             |
| Mandatory   | no          |             |
| Cardinality | 0..n        |             |
| Attributes  | Name        | `rdf:datatype` |
|             | Content     | http://www.w3.org/2001/XMLSchema#anyURI |
|             | Description | Type of the field |
|             | Mandatory   | yes         |
| Description | URL of a data file, if the distribution can be downloaded. For each of these, a `dcat:accessURL` has to exist. |             |

Example:
```xml
<dcat:downloadURL rdf:datatype="http://www.w3.org/2001/XMLSchema#anyURI"> http://data.geo.admin.ch.s3.amazonaws.com/ch.fill/data.zip</dcat:downloadURL>
```

##### `dct:rights`

|             |             |             |
|-------------|-------------|-------------|
| Type        | `rdfs:Literal` http://www.w3.org/TR/rdf-schema/#ch_literal |             |
| Content     | Possible values: <ul><li>NonCommercialAllowed-CommercialAllowed-ReferenceNotRequired (acceptable for opendata.swiss, Open Definition compliant)</li><li>NonCommercialAllowed-CommercialAllowed-ReferenceRequired (acceptable for opendata.swiss, Open Definition compliant)</li><li>NonCommercialAllowed-CommercialWithPermission-ReferenceNotRequired (acceptable for opendata.swiss)</li><li>NonCommercialAllowed-CommercialWithPermission-ReferenceRequired (acceptable for opendata.swiss)</li><li>NonCommercialAllowed-CommercialNotAllowed-ReferenceNotRequired (not acceptable for opendata.swiss)</li><li>NonCommercialAllowed-CommercialNotAllowed-ReferenceRequired (not acceptable for opendata.swiss)</li><li>NonCommercialNotAllowed-CommercialNotAllowed-ReferenceNotRequired (not acceptable for opendata.swiss)</li><li>NonCommercialNotAllowed-CommercialNotAllowed-ReferenceRequired (not acceptable for opendata.swiss)</li><li>NonCommercialNotAllowed-CommercialAllowed-ReferenceNotRequired (not acceptable for opendata.swiss)</li><li>NonCommercialNotAllowed-CommercialAllowed-ReferenceRequired (not acceptable for opendata.swiss)</li><li>NonCommercialNotAllowed-CommercialWithPermission-ReferenceNotRequired (not acceptable for opendata.swiss)</li><li>NonCommercialNotAllowed-CommercialWithPermission-ReferenceRequired (not acceptable for opendata.swiss)</li></ul> |             |
| Mandatory   | yes         |             |
| Cardinality | 1..1        |             |
| Description | Rights statement of this distribution. This is composed of 3 elements that can be summarized in a string literal: - Non-commercial use: allowed or not allowed - Commercial use: allowed, allowed with permission and not allowed - Reference: required or not required |             |
Example:
```xml
<dct:rights>NonCommercialAllowed-CommercialAllowed-ReferenceNotRequired</dct:rights>
```

##### `dct:license`

|             |             |
|-------------|-------------|
| Type        | `dct:LicenseDocument` |
| Mandatory   | no          |
| Cardinality | 0..1        |
| Attributes  |             |
| Description | Not used, see `dct:rights`. This field ensures compatibility to other metadata standards. |

Example:
```xml
<dct:license/>
```

##### `dct:byteSize`

|             |             |
|-------------|-------------|
| Type        | `rdfs:Literal` http://www.w3.org/TR/rdf-schema/#ch_literal |
| Mandatory   | no - except if the distribution is available as a data download (see `downloadURL`). |
| Cardinality | 0..1        |
| Attributes  |             |
| Description | Size of the data in bytes |

Example:
```xml
<dcat:byteSize>1024</dcat:byteSize>
```

##### `dct:mediaType`

|             |             |
|-------------|-------------|
| Type        | `dct:MediaTypeOrExtent` http://www.iana.org/assignments/media-types/media-types.xhtml |
| Mandatory   | no - except if the distribution is available as a data download (see `downloadURL`). |
| Cardinality | 0..1        |
| Attributes  |             |
| Description | This value will be used to display the ressource-format if the `downloadURL` is empty. Only values from the list of IANA MIME types http://www.iana.org/assignments/media-types/media-types.xhtml |

Example:
```xml
<dcat:mediaType>text/html</dcat:mediaType>
```

##### `dct:format`

|             |             |
|-------------|-------------|
| Type        | `dct:MediaTypeOrExtent` |
| Mandatory   | no          |
| Cardinality | 0..1        |
| Attributes  |             |
| Description | If neither the `downloadURL` nor the `mediaType` provide a valid format this value is used to display the format of the ressource. |

Example:
```xml
<dct:format/>
```

##### `dct:coverage`

|             |             |
|-------------|-------------|
| Type        | `dct:LocationPeriodOrJurisdiction` http://dublincore.org/documents/2012/06/14/dcmi-terms/?v=terms#LocationPeriodOrJurisdiction |
| Mandatory   | no          |
| Cardinality | 0..n        |
| Attributes  |             |
| Description | Distributions can be classified by their location or time period (for example, one for each canton, one for each year, etc.) |

Example:
```xml
<dct:coverage/>
```

#### Common fields

##### `rdf:Description`

|             |             |             |
|-------------|-------------|-------------|
| Type        | `rdfs:label` |             |
| Mandatory   | yes         |             |
| Cardinality | 1..1        |             |
| Attributes  | Name        | `rdf:about` |
|             | Mandatory   | no         |
| Description | The description of the dataset/distribution |             |



The following documents on the selection and definition of OGD standards for metadata are available in the Library:

* [CH DCAT AP Reference](/de/library/ch-dcat-ap)
* [DCAT Application Profile](/en/library/dcat-application)
* [DCAT: Catalog](/en/library/dcat-catalog)
* [DCAT: Dataset](/en/library/dcat-dataset)
* [DCAT: Distribution](/en/library/dcat-distribution)
