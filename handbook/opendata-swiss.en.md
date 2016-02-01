Title: Publish on opendata.swiss
Category: Publish
Handbook: yes
Tags:
Date: 2016-01-21
Slug: opendata-swiss
Summary: Authorities from the Confederation, cantons and communes as well as third parties that perform tasks on behalf of the state can publish their Open Data on the opendata.swiss portal. Learn how to get your Open Data on opendata.swiss.
Lang: en
Draft: yes


## Table of Contents

1. [Introduction](#introduction)


## Introduction
If you would like to add data to opendata.swiss and your agency or organisation is not yet publishing on opendata.swiss, please continue reading and contact <opendata@bar.admin.ch> for assistance.

opendata.swiss is the production portal, which replaced the pilot portal [opendata.admin.ch](http://opendata.admin.ch) by February 2, 2016, implementing the decisions taken by the ‹Open Government Data› project organisation under the leadership of the [Swiss Federal Archives SFA](http://www.bar.admin.ch/themen/01648/01968/index.html?lang=en) in the pilot phase.

opendata.swiss does not host data directly, but rather aggregates metadata about open data resources in one centralised location. 

## How can I publish my data on opendata.swiss?
You need to publish standardised information about your data, so-called metadata. When we say ‹data›, we mean [‹datasets› and ‹resources›](http://docs.ckan.org/en/ckan-1.8/domain-model.html#overview).
For publishers, opendata.swiss offers the following ways to add their data to the metadata catalogue:

| Use case                            | Solution          |
|-------------------------------------|-------------------| 
| _I want to publish certain datasets, which are updated at rare intervals._  | I manually submit my metadata through a web page on opendata.swiss. | 
| _I want to publish several data and/or data which are updated regularly._ | I manually import my metadata by uploading an XML file – in the DCAT-AP for Switzerland format (documentation see below) – on opendata.swiss. | 
| _I want to publish a large number of datasets and/or datasets which are updated frequently._  | I automatically import my metadata running a metadata harvester. | 
| _I have open geodata, already published or intended to be published via [geo.admin.ch / Federal Spatial Data Infrastructure FSDI](http://www.geo.admin.ch/internet/geoportal/en/home/geoadmin/mission/bgdi.html)_  | I configure corresponding metadata entries in [www.geocat.ch](http://www.geocat.ch/geonetwork/srv/ger/geocat), so it will be published automatically on opendata.swiss. For www.geocat.ch support, please contact <geocat@swisstopo.ch> | 

## How can I test if I am ready?

1. Get the [example XML file](https://github.com/ogdch/dcat-ap-docs/blob/master/ogdch_dcatap_import.rdf).
2. Fill the XML file for your metadata following the documentation of the DCAT-AP for Switzerland format below.
3. Send your XML-file for validation to the portal team: <opendata@bar.admin.ch> 
4. The portal team gets back to you with feedback.

## What is the DCAT-AP for Switzerland format?
The ‹Open Government Data› project organisation have worked out a joint solution; see all documents [M8 - Selection and definition of the OGD standards](http://www.egovernment.ch/umsetzung/00881/00883/01112/index.html?lang=en). The portal opendata.swiss implements these standards.

Have a look at the following example for a quick start:
(Full dataset RDF example: [ogdch_dcatap_import.rdf](https://github.com/ogdch/dcat-ap-docs/blob/master/ogdch_dcatap_import.rdf))

### Namespaces
```
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
```
<dct:title xml:lang="fr">FR Titre</dct:title>
<dct:title xml:lang="de">DE Titel</dct:title>
<dct:title xml:lang="it">IT Titolo</dct:title>
<dct:title xml:lang="en">EN Title</dct:title>
```

### DCAT-AP reference documentation

#### Definition of `dcat:Dataset`

`dct:identifier`

| Attributes  |             |
|-------------|-------------| 
| Type        | `rdfs:Literal` http://www.w3.org/TR/rdf-schema/#ch_literal | 
| Mandatory   | yes         | 
| Cardinality | 1..1        | 
| Description | Unique identifier of the dataset across all publishers. A good way to make sure this identifier is unique is to link the source system ID with the ID of the publisher: `<Source-Dataset-ID>@<Source-Organisation-ID>` | 
| Example     | `<dct:identifier>325@swisstopo</dct:identifier>` | 
| Open point  | Who gives out the publisher ID ? | 

`dct:title`

|             |             |             |
|-------------|-------------|-------------|
| Type        | `rdfs:Literal` http://www.w3.org/TR/rdf-schema/#ch_literal |             |
| Mandatory   | yes         |             |
| Cardinality | 1..n (one for each language) |             |
| Attributes  | Name        | `xml:lang`  |
|             | Content     | `en` `de` `fr` `it` |
|             | Description | Language of the element |
|             | Mandatory   | yes         |
| Description | Title of the dataset in the language defined by the `xml:lang` attribute |             |
| Example     | `<dct:title xml:lang="de">Eisenbahnlärm Nacht</dct:title>` |             |

`dct:description`

|             |             |             |
|-------------|-------------|-------------|
| Type        | `rdfs:Literal` http://www.w3.org/TR/rdf-schema/#ch_literal |             |
| Mandatory   | yes - in all the languages in which distributions are available TODO link to distribution |             |
| Cardinality | 1..n (one for each language) |             |
| Attributes  | Name        | `xml:lang`     |
|             | Content     | `en` `de` `fr` `it` |
|             | Description | Language of the element |
|             | Mandatory   | yes         |
| Description | Description of the dataset in the language defined by the `xml:lang` attribute |             |
| Example     | `<dct:description xml:lang="de">Die Karte zeigt, welcher Lärmbelastung die Bevölkerung durch den Schienenverkehr ausgesetzt ist.</dct:description>` |             |

`dct:issued`

|             |             |             |
|-------------|-------------|-------------|
| Type        | Date and time in [ISO-8601](https://en.wikipedia.org/wiki/ISO_8601) format |             |
| Mandatory   | Can be left out if there is no distribution TODO link to distribution  |             |                
| Cardinality | 0..1        |             |
| Attributes  | Name        | `rdf:datatype` |
|             | Content     | http://www.w3.org/2001/XMLSchema#dateTime | 
|             | Description | Type of the field |
|             | Mandatory   | yes         |
| Description | Date of the first publication of this dataset. If this date is unknown, the date of the first publication in this catalog can be used. If that date is in the future, the dataset is not displayed. |             |
| Example     | `<dct:issued rdf:datatype="http://www.w3.org/2001/XMLSchema#dateTime"> 2013-04-26T01:00:00Z</dct:issued>` |             |

`dct:modified`

|             |             |             |
|-------------|-------------|-------------|
| Type        | Date and time in [ISO-8601](https://en.wikipedia.org/wiki/ISO_8601) format |             |
| Mandatory   | Only when the dataset has changed since the first publication |             |                
| Cardinality | 0..1        |             |
| Attributes  | Name        | `rdf:datatype` |
|             | Content     | http://www.w3.org/2001/XMLSchema#dateTime | 
|             | Description | Type of the field |
|             | Mandatory   | yes         |
| Description | Date of the last change (since the first publication on the portal) |             |
| Example     | `<dct:modified rdf:datatype="http://www.w3.org/2001/XMLSchema#dateTime"> 2013-04-26T01:00:00Z</dct:modified>` |             |

`dct:publisher`

|             |             |             |
|-------------|-------------|-------------|
| Elements    | `rdf:Description` |             |
| Type        | Nested element |             |
| Mandatory   | yes         |             |                
| Cardinality | 1..n        |             |
| Description | The publishers of the dataset. `rdf:about` is an optional attribute that may contain a TERMDAT reference. |             |
Example:
```xml
<dct:publisher> 
  <rdf:Description rdf:about="Reference to TERMDAT-Entry">
    <rdfs:label>Bundesamt für Landestopografie swisstopo</rdfs:label>
  </rdf:Description>
</dct:publisher>
``` 

`dct:contactPoint`

|             |             |             |
|-------------|-------------|-------------|
| Elements    | `vcard:Organization` |             |
| Type        | `vcard:Kind` |             |
| Mandatory   | yes         |             |                
| Cardinality | 1..n        |             |
| Description | One or more contact email addresses for this dataset `vcard:fn`. Description of the point of contact `vcard:hasEmail` has an attribute `rdf:resource` which contains the email of the point of contact (including mailto:) |             |
| Example     | 
```
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
|             |

##### `dct:theme`

|             |             |             |
|-------------|-------------|-------------|
| Type        | `skos:Concept` http://www.w3.org/2009/08/skos-reference/skos.html#Concept |             |
| Mandatory   | yes         |             |                
| Cardinality | 1..n        |             |
| Attributes  | Name        | `rdf:resource` |
|             | Description | URI to the category |
|             | Mandatory   | yes         |
| Description | Categorisation of the data. In the `rdf:resource` attribute, the unique URI of the category from SKOS-RDF must be given. The following values are accepted from Themes: <ul><li>http://opendata.swiss/themes/work</li><li>http://opendata.swiss/themes/construction</li><li>http://opendata.swiss/themes/population</li><li>http://opendata.swiss/themes/education</li><li>http://opendata.swiss/themes/energy</li><li>http://opendata.swiss/themes/finances</li><li>http://opendata.swiss/themes/geography</li><li>http://opendata.swiss/themes/legislation</li><li>http://opendata.swiss/themes/health</li><li>http://opendata.swiss/themes/trade</li><li>http://opendata.swiss/themes/industry</li><li>http://opendata.swiss/themes/crime</li><li>http://opendata.swiss/themes/culture</li><li>http://opendata.swiss/themes/agriculture</li><li>http://opendata.swiss/themes/mobility</li><li>http://opendata.swiss/themes/public-order</li><li>http://opendata.swiss/themes/politics</li><li>http://opendata.swiss/themes/prices</li><li>http://opendata.swiss/themes/territory</li><li>http://opendata.swiss/themes/social-security</li><li>http://opendata.swiss/themes/statistical-basis</li><li>http://opendata.swiss/themes/tourism</li><li>http://opendata.swiss/themes/administration</li><li>http://opendata.swiss/themes/national-economy</li></ul> |             |
| Example     | `<dcat:theme rdf:resource="http://opendata.swiss/themes/population"/>` |             |

`dct:language`

|             |             |             |
|-------------|-------------|-------------|
| Type        | `rdfs:Literal` ISO 639-1 two-letter code |             |
| Content     | `en` `de` `fr` `it` |             |
| Mandatory   | no          |             |
| Cardinality | 0..n (for each language) |             |
| Attributes  |             |             |
| Description | Should contain all languages for which a distribution is available. This field is not validated and is used for display purposes. If all distributions are language-independant, this field can be left out. |             |
| Example     | `<dct:language>de</dct:language>` |             |

`dct:relation`

|             |             |             |
|-------------|-------------|-------------|
| Elements    | `rdf:Description` |             |
| Type        | Nested element |             |
| Mandatory   | no          |             |                
| Cardinality | 0..n        |             |
| Description | A relation to a document. The `rdf:about` must link to a related document. |             |
| Example     | 
```
<dct:relation>
  <rdf:Description rdf:about="http://www.bafu.admin.ch/laerm/index.html?lang=de">
    <rdfs:label>Webseite des BAFU</rdfs:label>
  </rdf:Description>
</dct:relation>
``` 
|             |

`dcat:keyword`

|             |             |             |
|-------------|-------------|-------------|
| Type        | `rdfs:Literal` http://www.w3.org/TR/rdf-schema/#ch_literal |             |
| Mandatory   | no          |             |                
| Cardinality | 0..n        |             |
| Attributes  | Name        | `xml:lang` |
|             | Content     | `en` `de` `fr` `it` | 
|             | Description | Language of the element |
|             | Mandatory   | yes         |
| Description | Keyword who describes that dataset |             |
| Example     | 
```
<dcat:keyword xml:lang="de">Nacht</dcat:keyword>
<dcat:keyword xml:lang="fr">Nuit</dcat:keyword>
<dcat:keyword xml:lang="it">Noche</dcat:keyword>
<dcat:keyword xml:lang="en">Night</dcat:keyword>
``` 
|             |

`dcat:landingPage`

|             |             |             |
|-------------|-------------|-------------|
| Type        | `foaf:Document` http://xmlns.com/foaf/spec/#term_Document |             |
| Mandatory   | no          |             |
| Cardinality | 0..1        |             |
| Attributes  |             |             |
| Description | Website of the dataset with related information |             |
| Example     | `<dcat:landingPage>http://www.bafu.admin.ch/laerm/index.html?lang=de</dcat:landingPage>` |             |

`dcat:spatial`

|             |             |             |
|-------------|-------------|-------------|
| Type        | `dct:Location` http://dublincore.org/documents/2012/06/14/dcmi-terms/?v=terms#Location |             |
| Mandatory   | no          |             |
| Cardinality | 0..n        |             |
| Attributes  |             |             |
| Description | Geographical classification of the dataset. Can be a description, coordinates or a bounding-box. |             |
| Example     | `<dct:spatial rdf:resource="http://publications.europa.eu/mdr/authority/country/ZWE"/>` |             |

`dcat:temporal`

|             |             |             |
|-------------|-------------|-------------|
| Type        | `ct:PeriodOfTime` http://dublincore.org/documents/2012/06/14/dcmi-terms/?v=terms#terms-PeriodOfTime |             |
| Mandatory   | no          |             |                
| Cardinality | 0..n        |             |
| Attributes  |             |             |
| Description | One or more time period(s) that cover the dataset. `<schema:startDate>` contains the start date `<schema:endDate>` contains the end date Format for dates: http://www.w3.org/2001/XMLSchema#date |             |
| Example     | 
```
<dct:temporal>
  <dct:PeriodOfTime>
    <schema:startDate rdf:datatype="http://www.w3.org/2001/XMLSchema#date">1905-03-01</schema:startDate>
    <schema:endDate rdf:datatype="http://www.w3.org/2001/XMLSchema#date">2013-01-05</schema:endDate>
  </dct:PeriodOfTime>
</dct:temporal>
``` 
|             |

`dct:accrualPeriodicity`

|             |             |             |
|-------------|-------------|-------------|
| Mandatory   | no          |             |                
| Cardinality | 0..n        |             |
| Attributes  | Name        | `rdf:resource` |
|             | Type        | `dct:Frequency` |
|             | Mandatory   | yes         |
| Description | The frequency in which this dataset is updated. Values for `dct:Frequency`: http://dublincore.org/groups/collections/frequency/ |             |
| Example     | `<dct:accrualPeriodicity rdf:resource="http://purl.org/cld/freq/daily"/>` |             |

`rdfs:seeAlso`

|             |             |             |
|-------------|-------------|-------------|
| Type        | `rdfs:Literal` http://www.w3.org/TR/rdf-schema/#ch_literal |             |                
| Mandatory   | no          |             |
| Cardinality | 0..n        |             |
| Attributes  |             |             |
| Description | Link to related datasets. Contains the identifier of the linked dataset. |             |
| Example     | `<rdfs:seeAlso>326@swisstopo</rdfs:seeAlso>` |             |

`dcat:distribution`

|             |             |             |
|-------------|-------------|-------------|
| Type        | Nested elements. See [Definition of Distribution](http://dcat-ap-switzerland.readthedocs.org/en/latest/dcat-ap-format.html#definition-of-distribution). |             |
| Mandatory   | no          |             |
| Cardinality | 0..n        |             |
| Attributes  |             |             |
| Description | Distribution of the datasets |             |
| Example     |             |             |

#### Definition of Distribution

`dcat:identifier`

|             |             |
|-------------|-------------| 
| Type        | `rdfs:Literal` http://www.w3.org/TR/rdf-schema/#ch_literal | 
| Mandatory   | no          | 
| Cardinality | 0..1        | 
| Attributes  |             |
| Description | Identifier of the distribution in the source system | 
| Example     | `<dct:identifier>ch.bafu.laerm-bahnlaerm_nacht</dct:identifier>` | 

`dcat:title`

|             |             |             |
|-------------|-------------|-------------|
| Type        | `rdfs:Literal` http://www.w3.org/TR/rdf-schema/#ch_literal |             |
| Mandatory   | no - except if the distribution does not contain all the content of the dataset. |             |
| Cardinality | 0..n (one for each language) |             |
| Attributes  | Name        | `xml:lang`  |
|             | Content     | `en` `de` `fr` `it` |
|             | Description | Language of the element |
|             | Mandatory   | yes         |
| Description | The title of the distribution in the language defined by the `xml:lang? attribute. If this element is left out, the `dct:title` of the dataset is used instead. |             |
| Example     | `<dct:title xml:lang="de">WMS (ch.bafu.laerm-bahnlaerm_nacht)</dct:title>` |             |

`dct:description`

|             |             |             |
|-------------|-------------|-------------|
| Type        | `rdfs:Literal` http://www.w3.org/TR/rdf-schema/#ch_literal |             |
| Mandatory   | no - except if the distribution does not contain all the content of the dataset. |             |
| Cardinality | 0..n (one for each language) |             |
| Attributes  | Name        | `xml:lang`  |
|             | Content     | `en` `de` `fr` `it` |
|             | Description | Language of the element |
|             | Mandatory   | yes         |
| Description | Description of the distribution in the language defined by the `xml:lang` attribute |             |
| Example     | `<dct:title xml:lang="de">WMS (ch.bafu.laerm-bahnlaerm_nacht)</dct:title>` |             |

`dct:issued`

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
| Example     | ```<dct:issued rdf:datatype="http://www.w3.org/2001/XMLSchema#dateTime"> 2013-05-11T00:00:00Z</dct:issued>``` |             |

`dct:modified`

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
| Example     | ```<dct:modified rdf:datatype="http://www.w3.org/2001/XMLSchema#dateTime"> 2015-04-26T00:00:00Z</dct:modified>``` |             |

`dct:language`

|             |             |             |
|-------------|-------------|-------------|
| Type        | `rdfs:Literal` ISO 639-1 two-letter code |             |
| Content     | `en` `de` `fr` `it` |             |
| Mandatory   | no          |             |
| Cardinality | 0..n (for each language) |             |
| Attributes  |             |             |
| Description | Languages in which this distribution is available. If the distribution is language-independant, this can be left out. |             |
| Example     | `<dct:language>de</dct:language>` |             |

`dcat:accessURL`

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
| Example     | ```<dcat:accessURL rdf:datatype="http://www.w3.org/2001/XMLSchema#anyURI"> http://wms.geo.admin.ch/</dcat:accessURL>``` |             |

`dct:downloadURL`

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
| Example     | ```<dcat:downloadURL rdf:datatype="http://www.w3.org/2001/XMLSchema#anyURI"> http://data.geo.admin.ch.s3.amazonaws.com/ch.fill/data.zip</dcat:downloadURL>``` |             |

`dct:rights`

|             |             |             |
|-------------|-------------|-------------|
| Elements    | Name        | `odrs:dataLicense` |
|             | Content     | Possible values: <ul><li>NonCommercialAllowed-CommercialAllowed-ReferenceNotRequired (acceptable for opendata.swiss, Open Definition compliant)</li><li>NonCommercialAllowed-CommercialAllowed-ReferenceRequired (acceptable for opendata.swiss, Open Definition compliant)</li><li>NonCommercialAllowed-CommercialWithPermission-ReferenceNotRequired (acceptable for opendata.swiss)</li><li>NonCommercialAllowed-CommercialWithPermission-ReferenceRequired (acceptable for opendata.swiss)</li><li>NonCommercialAllowed-CommercialNotAllowed-ReferenceNotRequired (not acceptable for opendata.swiss)</li><li>NonCommercialAllowed-CommercialNotAllowed-ReferenceRequired (not acceptable for opendata.swiss)</li><li>NonCommercialNotAllowed-CommercialNotAllowed-ReferenceNotRequired (not acceptable for opendata.swiss)</li><li>NonCommercialNotAllowed-CommercialNotAllowed-ReferenceRequired (not acceptable for opendata.swiss)</li><li>NonCommercialNotAllowed-CommercialAllowed-ReferenceNotRequired (not acceptable for opendata.swiss)</li><li>NonCommercialNotAllowed-CommercialAllowed-ReferenceRequired (not acceptable for opendata.swiss)</li><li>NonCommercialNotAllowed-CommercialWithPermission-ReferenceNotRequired (not acceptable for opendata.swiss)</li><li>NonCommercialNotAllowed-CommercialWithPermission-ReferenceRequired (not acceptable for opendata.swiss)</li></ul> |
| Type        | Open Data Rights Statement Vocabulary (https://theodi.org/guides/publishers-guide-to-the-open-data-rights-statement-vocabulary) |             |
| Mandatory   | yes         |             |
| Cardinality | 1..1        |             |
| Attributes  |             |             |
| Description | Rights statement of this distribution. This is composed of 3 elements that can be summarized in a string literal: - Non-commercial use: allowed or not allowed - Commercial use: allowed, allowed with permission and not allowed - Reference: required or not required |             |
| Example     | 
```
<dct:rights>
  <odrs:dataLicence>
      NonCommercialAllowed-CommercialAllowed-ReferenceNotRequired
  </odrs:dataLicence>
</dct:rights>
``` 
|             |

`dct:license`

|             |             |
|-------------|-------------|
| Type        | `dct:LicenseDocument` |
| Mandatory   | no          |
| Cardinality | 0..1        |
| Attributes  |             |
| Description | Not used, see `dct:rights`. This field ensures compatibility to other metadata standards. |
| Example     | `<dct:license/>` |

`dct:byteSize`

|             |             |
|-------------|-------------|
| Type        | `rdfs:Literal` http://www.w3.org/TR/rdf-schema/#ch_literal |
| Mandatory   | no - except if the distribution is available as a data download (see `downloadURL`). |
| Cardinality | 0..1        |
| Attributes  |             |
| Description | Size of the data in bytes |
| Example     | `<dcat:byteSize>1024</dcat:byteSize>` |

`dct:mediaType`

|             |             |
|-------------|-------------|
| Type        | `dct:MediaTypeOrExtent` http://www.iana.org/assignments/media-types/media-types.xhtml |
| Mandatory   | no - except if the distribution is available as a data download (see `downloadURL`). |
| Cardinality | 0..1        |
| Attributes  |             |
| Description | Only values from the list of IANA MIME types http://www.iana.org/assignments/media-types/media-types.xhtml |
| Example     | `<dcat:mediaType>text/html</dcat:mediaType>` |

`dct:format`

|             |             |
|-------------|-------------|
| Type        | `dct:MediaTypeOrExtent` |
| Mandatory   | no          |
| Cardinality | 0..1        |
| Attributes  |             |
| Description | Available for compatibility reasons. Not used |
| Example     | `<dct:format/>` |

`dct:coverage`

|             |             |
|-------------|-------------|
| Type        | `dct:LocationPeriodOrJurisdiction` http://dublincore.org/documents/2012/06/14/dcmi-terms/?v=terms#LocationPeriodOrJurisdiction |
| Mandatory   | no          |
| Cardinality | 0..n        |
| Attributes  |             |
| Description | Distributions can be classified by their location or time period (for example, one for each canton, one for each year, etc...) |
| Example     | `<dct:coverage/>` |

#### Common fields

`rdf:Description`

|             |             |             |
|-------------|-------------|-------------|
| Type        | `rdfs:label` |             |
| Mandatory   | yes         |             |
| Cardinality | 1..1        |             |
| Attributes  | Name        | `rdf:about` |
|             | Mandatory   | no         |
| Description | The description of the dataset/distribution |             |
