Title: Auf opendata.swiss veröffentlichen
Category: Publish
Handbook: yes
Tags:
Date: 2016-01-01
Slug: opendata-swiss
Summary: Behörden der Eidgenossenschaft, der Kantone und der Gemeinden ebenso wie Dritte, die im Auftrag des Staates Aufgaben ausführen, können ihre Daten auf dem Portal opendata.swiss veröffentlichen. Erfahren Sie, wie Sie Ihre Open Data auf opendata.swiss bringen.
Lang: de
Draft: yes


> *Dieses Thema ist noch nicht übersetzt - melden Sie sich, falls Sie diesen Inhalt in Ihrer Sprache benötigen.*

If you would like to add data to opendata.swiss and your agency or organisation is not yet [publishing on opendata.swiss](https://opendata.swiss/de/organization), please continue reading and [contact us for assistance](/en/pages/contribute).

[opendata.swiss](https://opendata.swiss) is the production portal, which replaced the pilot portal ‹opendata.admin.ch› by February 2, 2016, implementing the decisions taken by the ‹Open Government Data› project organisation under the leadership of the [Swiss Federal Archives SFA](http://www.bar.admin.ch/themen/01648/01968/index.html?lang=en) in the pilot phase.

opendata.swiss does not host data directly, but rather aggregates metadata about open data resources in one centralised location.

## How can I publish my data on opendata.swiss?
You need to publish standardised information about your data, so-called metadata. When we say ‹data›, we mean [‹datasets› and ‹resources›](http://docs.ckan.org/en/ckan-1.8/domain-model.html#overview).

For publishers, opendata.swiss offers the following ways to add their data to the metadata catalogue:

| Use case          | Solution          | Get ready        |
|-------------------|-------------------|------------------|
| _I want to publish certain datasets, which are updated at rare intervals._ | I manually submit my metadata through a web page on opendata.swiss. | For assistance, please [contact us](/en/pages/contribute) |
| _I want to publish several data and/or data which are updated regularly._ | I manually import my metadata by uploading an XML file – in the DCAT-AP for Switzerland format (documentation see below) – on opendata.swiss. | For assistance, please [contact us](/en/pages/contribute) |
| _I want to publish a large number of datasets and/or datasets which are updated frequently._ | I automatically import my metadata running a metadata harvester. | For assistance, please [contact us](/en/pages/contribute) |
| _I have open geodata, already published or intended to be published via [geo.admin.ch / Federal Spatial Data Infrastructure FSDI](http://www.geo.admin.ch/internet/geoportal/en/home/geoadmin/mission/bgdi.html)_ | I configure corresponding metadata entries in [www.geocat.ch](http://www.geocat.ch/geonetwork/srv/ger/geocat), so it will be published automatically on opendata.swiss. | For www.geocat.ch support, please contact <geocat@swisstopo.ch> |

## How can I test if I am ready?

1. Get the [example XML file](/samples/ogdch_dcatap_import.rdf).
2. Fill the XML file for your metadata following the documentation of the [DCAT-AP for Switzerland format](#dcat-ap-reference-documentation).
3. Send your XML-file for validation to the portal team: [contact us](/en/pages/contribute)
4. The portal team gets back to you with feedback.

## What is the DCAT-AP for Switzerland format?

<a href="/de/library/ch-dcat-ap" class="btn btn-default" role="button">DCAT-AP for Switzerland</a>

The ‹Open Government Data› project organisation have worked out a joint solution for standardising on metadata publishing. See [documentation in the library](/de/library/ch-dcat-ap) for full details.
