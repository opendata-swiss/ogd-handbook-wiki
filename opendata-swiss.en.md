Title: Publish on opendata.swiss
Category: Publish
Handbook: yes
Tags:
Date: 2016-01-21
Slug: opendata-swiss
Summary: Authorities from the Confederation, cantons and communes as well as third parties that perform tasks on behalf of the state can publish their Open Data on the opendata.swiss portal. Learn how to get your Open Data on opendata.swiss.
Lang: en
Draft: yes


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

## What is DCAT-AP for Switzerland format?
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
- French (fr)
- German (de)
- Italian (it)
- English (en)

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

| Attributes  |            |
|-------------|------------| 
| Type        | `rdfs:Literal` http://www.w3.org/TR/rdf-schema/#ch_literal | 
| Mandatory   |  yes | 
| Cardinality |  1..1 | 
| Description |  Unique identifier of the dataset across all publishers. A good way to make sure this identifier is unique is to link the source system ID with the ID of the publisher: `<Source-Dataset-ID>@<Source-Organisation-ID>` | 
| Example     | `<dct:identifier>325@swisstopo</dct:identifier>` | 
| Open point  | Who gives out the publisher ID ? | 

`dct:title`

|             |                                                                              |                         |
|-------------|------------------------------------------------------------------------------|-------------------------|
| Type        | `rdfs:Literal` http://www.w3.org/TR/rdf-schema/#ch_literal                   |                         |
| Mandatory   | yes                                                                          |                         |
| Cardinality | 1..n (one for each language)                                                 |                         |
| Attributes  | Name                                                                         | `xml:lang`              |
|             | Content                                                                      | `en` `de` `fr` `it`     |
|             | Description                                                                  | Language of the element |
|             | Mandatory                                                                    | yes                     |
| Description | Title of the dataset in the language defined by the `xml:lang` attribute     |                         |
| Example     | `<dct:title xml:lang="de">Eisenbahnlärm Nacht</dct:title>`                   |                         |

`dct:description`

|             |                                                                              |                         |
|-------------|------------------------------------------------------------------------------|-------------------------|
| Type        | `rdfs:Literal` http://www.w3.org/TR/rdf-schema/#ch_literal                   |                         |
| Mandatory   | yes - in all the languages in which distributions are available TODO link to distribution |            |
| Cardinality | 1..n (one for each language)                                                 |                         |
| Attributes  | Name                                                                         | `xml:lang`              |
|             | Content                                                                      | `en` `de` `fr` `it`     |
|             | Description                                                                  | Language of the element |
|             | Mandatory                                                                    | yes                     |
| Description | Description of the dataset in the language defined by the `xml:lang` attribute |                       |
| Example     | `<dct:description xml:lang="de">Die Karte zeigt, welcher Lärmbelastung die Bevölkerung durch den Schienenverkehr ausgesetzt ist.</dct:description>` |            |

`dct:issued`

|             |                                                                          |                         |
|-------------|--------------------------------------------------------------------------|-------------------------|
| Type        | Date and time in ISO-8601 format                                         |                         |
| Mandatory   | Can be left out if there is no distribution TODO link to distribution    |                         |                 
| Cardinality | 0..1                                                                     |                         |
| Attributes  | Name                                                                     | `rdf:datatype`          |
|             | Content                                                                  | http://www.w3.org/2001/XMLSchema#dateTime | 
|             | Description                                                              | Type of the field       |
|             | Mandatory                                                                | yes                     |
| Description | Date of the first publication of this dataset. If this date is unknown, the date of the first publication in this catalog can be used. If that date is in the future, the dataset is not displayed. |              |
| Example     | `<dct:issued rdf:datatype="http://www.w3.org/2001/XMLSchema#dateTime"> 2013-04-26T01:00:00Z</dct:issued>` |              |
