Title: Role of open data portals
Category: Support
Handbook: yes
Tags:
Date: 2016-01-22
Slug: ogd-portals
Authors:
Summary: An overview of how data portals work, how to publish data to them, and where to find them.
Lang: en
Draft: yes


A *data portal* (see examples below in [Links](#links)) is an online collection of links to resources, in some ways similar to a Document Management System, which often provides the ability to directly download and/or query structured data. These datasets are often collected with involvement of the maintainers of the data portal - though not always, as in the case of crowd-sourced portals like [Datahub.io](http://datahub.io), or linked data portals like [Wikidata](https://www.wikidata.org/).

### What are data portals for?

Data portals are designed to put together datasets from across many sources in one place, presenting information about them consistently, and including features that assist end users in *discovering* the datasets they need. They also play an important role in connecting the data publisher and end user, for instance allowing people to more easily keep track of *updates and changes* to datasets they are using.

Most data portals combine datasets which are directly distributed on site, and remote datasets which are linked from the portal. Sometimes larger sized files and special requirements like geodata services are *hosted* externally, but in the the best case the user does not have to be aware of such details - and just use the data.

As data portals proliferate (there are several thousand portal projects worldwide), the question arises of what happens when datasets are published in multiple locations. *Federation* between portals is a kind of software contract that allows content to be shared between them.

An *open data portal* is one that has a focus on providing datasets which are licensed under open conditions. See [criteria for OGD](/identify/criteria) for more background. Open data portals provide access to data mainly from government offices ([opendata.swiss](/publish/opendata-swiss)), science and academia ([openresearchdata.ch](http://openresearchdata.ch)), maps and Geographic Information Systems ([geo.admin.ch](http://geo.admin.ch)), and so on.

In summary, data portals are for:

> - Providing an avenue to allow the private and community sectors to add their data. It may be worthwhile to think of the catalog as the region’s catalog, rather than the regional government’s.
- Facilitating improvement of the data by allowing derivatives of datasets to be cataloged. For example, someone may geocode addresses and may wish to share those results with everybody. If you only allow single versions of datasets, these improvements remain hidden.
- Be tolerant of your data appearing elsewhere. That is, content is likely to be duplicated to communities of interest. If you have river level monitoring data available, then your data may appear in a catalog for hydrologists.
- Ensure that access is equitable. Try to avoid creating a privileged level of access for officials or tenured researchers as this will undermine community participation and engagement.

> [Open Data Handbook](http://opendatahandbook.org/guide/en/how-to-open-up-data/#for-government)

### Publishing to portals

Important steps in the process of uploading and managing a dataset include:

- ensuring the latest versions of content is available
- appropriate taxonometry and categorisation
- correct and complete labels and tagging (see [applying metadata](/publish/metadata))
- validating license details and contact information
- testing the ability to preview the data (if possible)

For larger organizations with their own infrastructure, it often becomes inconvenient and costly to upload datasets one at a time, so software programs called **harvesters** are used to collect details on each dataset and publish a selection of metadata to the data portal. These programs can also be run automatically to ensure that updates are propagated. For more information, see [publishing on opendata.swiss](/publish/opendata-swiss).

<a name="links"></a>
### Links to open government data portals

**[opendata.swiss](http://opendata.swiss)** is the official Open Government Data portal of the Swiss Confederation.

Several Swiss Cantons and Communes have already started federating their collections with **opendata.swiss**, some also run their own data portals:

- [Canton of Zürich](http://opendata.zh.ch/) (opendata.zh.ch)
- [City of Zürich](http://data.stadt-zuerich.ch/) (data.stadt-zuerich.ch)
- [Canton of Geneva](http://ge.ch/sitg/donnees) (ge.ch)

**Worldwide - directories**

- [Dataportals.org](http://dataportals.org/) is a comprehensive directory of data portals.
- [OpenDataSoft](https://www.opendatasoft.com/a-comprehensive-list-of-all-open-data-portals-around-the-world/) maintains a list of open data portals and sites around the world.
- [Datahub.io](http://datahub.io) is a crowdsourced data portal run by Open Knowledge.

**Worldwide - examples**

- European Union: [open-data.europa.eu](http://open-data.europa.eu/en/data/)
- France: [data.gouv.fr](http://www.data.gouv.fr/fr/)
- Italy: [dati.gov.it](http://www.dati.gov.it/)
- Germany: [govdata.de](https://www.govdata.de/)
- Austria: [data.gv.at](https://www.data.gv.at/)
- The Netherlands: [data.overheid.nl](https://data.overheid.nl/)
- UK: [data.gov.uk](https://data.gov.uk/)
- USA: [Data.gov](https://www.data.gov/open-gov/)
