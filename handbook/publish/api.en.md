---
Title: Usage of the API
Category: Publish
Handbook: yes
Tags:
Date: 2016-01-01
Slug: api
Authors:
Summary: A description of the CKAN API
Lang: en
Draft: no
Hidden: no
Untranslated: yes
---

<a name="introduction"></a>
# Introduction

The open data portal opendata.swiss is based on the [open source project CKAN](http://ckan.org).
CKAN provides an extensive API for the metadata of the open data catalogue.

The API is HTTP based and uses GET and POST requests.
All responses are provided as JSON.

Please use the [CKAN documentation for detailed information about the API](http://docs.ckan.org/en/latest/api/).

Important note about metadata: opendata.swiss uses the [metadata standard DCAT-AP Switzerland](/en/library/ch-dcat-ap). Therefore all metadata is returned using this standard. Where possible, a mapping to CKAN standard fields is provided by the API.

<a name="concepts"></a>
# Concepts

CKAN uses internally a number of concepts, that are important to understand in order to use the API properly.

<a name="entities"></a>
## Entities

First of all, the following entities are used:

* **Packages** (also known as datasets): a container for metadata containing multiple resources
* **Resource**: a file or API, actual data you can use (NOTE: opendata.swiss does currently not host files, only URLs to files and APIs)
* **Group** (aslo known as categories or themes): a categorization of the datasets. A dataset may have multiple groups
* **Organization**: is a special kind of group, one dataset has exactly one owning organization

<a name="action-api"></a>
## Action API

All API requests use the so called [Action API](http://docs.ckan.org/en/latest/api/#action-api-reference).
The URL of these requests is composed like that:

https://opendata.swiss/api/{api_version}/action/{action_name}

The currently used API version is 3, and a list of actions is [available in the CKAN documentation](http://docs.ckan.org/en/latest/api/#action-api-reference).

Example: https://opendata.swiss/api/3/action/group_list

<a name="authentication"></a>
## Authentication

Most GET-able API function do not need authentication (i.e. everybody is allowed to read metadata).
For all other actions POST requests are used (e.g. create new packages, update groups or delete resources), that require authentication.
Please [contact us](mailto:opendata@bar.admin.ch) if you have further questions regarding the advanced usage of the API.


<a name="examples"></a>
# Examples

Here are a couple of examples, how to use the API.
Note the API always returns a JSON response.

## Find metadata of a specific dataset

Datasets are called "packages" in the API, to list all packages, we use `package_list`:

```bash
curl 'https://opendata.swiss/api/3/action/package_list'
```

Here we get a list of all available datasets slugs, we can pick one, and get all metadata from it, e.g. `studierende-fachhochschule-anz`:

```bash
curl 'https://opendata.swiss/api/3/action/package_show?id=studierende-fachhochschule-anz'
```

## Search for datasets

The search functionality is provided by the [API function `package_search`](http://docs.ckan.org/en/latest/api/#ckan.logic.action.get.package_search).
A simple search for `switzerland` looks like this:

```bash
curl 'https://opendata.swiss/api/3/action/package_search?q=switzerland'
```

The search is based on [Solr](http://lucene.apache.org/solr/), and therefore provides a number of advanced parameters.

To filter the search to only return results with a specific keyword (`geology`), `fq` (filter query) could be used:

```bash
curl 'https://opendata.swiss/api/3/action/package_search?q=switzerland&fq=+keywords_en:geology'
```
