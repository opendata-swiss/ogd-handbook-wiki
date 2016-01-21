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
If you would like to add data to opendata.swiss and your agency or organisation is not yet publishing on opendata.swiss, please continue reading and contact opendata@bar.admin.ch for assistance.

opendata.swiss is the production portal, which replaced the pilot portal [opendata.admin.ch](http://opendata.admin.ch) by February 2, 2016, implementing the decisions taken by the ‹Open Government Data› project organisation under the leadership of the [Swiss Federal Archives SFA](http://www.bar.admin.ch/themen/01648/01968/index.html?lang=en) in the pilot phase.

opendata.swiss does not host data directly, but rather aggregates metadata about open data resources in one centralised location. 

## How can I publish my data on opendata.swiss?
You need to publish standardised information about your data, so-called metadata. When we say ‹data›, we mean [‹datasets› and ‹resources›](http://docs.ckan.org/en/ckan-1.8/domain-model.html#overview).
For publishers, opendata.swiss offers the following ways to add their data to the metadata catalogue:

| Use case                            | Solution          |
|-------------------------------------|-------------------| 
| _I want to publish certain datasets, which are updated at rare intervals._  | I manually submit my metadata through a web page on opendata.swiss. | 
| _I want to publish several data and/or data which are updated regularly._ | I manually import my metadata by uploading an [XML file](http://dcat-ap-switzerland.readthedocs.org/en/latest/upload.html) on opendata.swiss.  | 
| _I want to publish a large number of datasets and/or datasets which are updated frequently._  | I automatically import my metadata running a metadata harvester. I can use a [standard harvester](http://dcat-ap-switzerland.readthedocs.org/en/latest/harvester.html) on opendata.swiss or custom-develop my own.  | 
| _I have open geodata, already published or intended to be published via [geo.admin.ch / Federal Spatial Data Infrastructure FSDI](http://www.geo.admin.ch/internet/geoportal/en/home/geoadmin/mission/bgdi.html)_  | I configure corresponding metadata entries in [www.geocat.ch](http://www.geocat.ch/geonetwork/srv/ger/geocat), so it will be published automatically on opendata.swiss. For www.geocat.ch support, please contact geocat@swisstopo.ch | 

## What metadata schema do I have to follow?
The ‹Open Government Data› project organisation have worked out a joint solution; see all documents [M8 - Selection and definition of the OGD standards](http://www.egovernment.ch/umsetzung/00881/00883/01112/index.html?lang=en). The portal opendata.swiss implements these standards [as follows](http://dcat-ap-switzerland.readthedocs.org/en/latest/). 

## How can I test if I am ready?

1. Get the [example XML file](https://github.com/ogdch/dcat-ap-docs/blob/master/ogdch_dcatap_import.rdf).
2. Fill the XML file for your metadata following the [documentation](http://dcat-ap-switzerland.readthedocs.org/en/latest/dcat-ap-format.html).
3. Send your XML-file for validation to the portal team: opendata@bar.admin.ch 
4. The portal team gets back to you with feedback.

## I have got an issue. How can I get support?
Please create an issue [here](https://github.com/ogdch/dcat-ap-docs/issues).
