---
Title: Advanced Search
Category: Library
Template: document
Tags: support
Date: 2017-07-20
Slug: advanced-search
Summary:
Lang: en
toc_run: true
Untranslated: yes
---

<a name="advanced-search"></a>
# Advanced search

<a name="technical-background"></a>
## Technical background

opendata.swiss has a very powerful search engine, that can help you to find exactly the datasets you want.
The search is provided by the open source component [Apache Lucene/Solr](http://lucene.apache.org/solr/).
Every dataset is indexed by Solr when it gets updated, and if you perform a search on the portal, this index is queried to efficiently deliver results.

The search index is basically the "database" where all the information for the search is saved.
It uses a custom schema with all the dataset fields that should be indexed.
The schema is flat, i.e. nested elements like resources must be saved differently, in order for Solr to index them.
The same applies to the multilingual fields, which are all stored with the language suffix, e.g. `keywords_en` contains the English keywords.

By default, all the fields that belong to a dataset are copied in one field (called _"text"_), so that the search process only has to check one field to find a match.
So if a user submits a search with the query "weather", Solr runs this query against the _"text"_ field of all datasets.

<a name="search-index"></a>
## Search Index
The search index contains the following fields:

URLs:
* `url`
* `ckan_url`
* `download_url`
* `res_url`

Text-fields:
* `extras_*`
* `res_extras_*`
* `urls`
* `name`
* `title`
* `title_string`
* `text`
* `license`
* `notes`
* `tags`
* `groups`
* `organization`
* `res_name`
* `res_format`
* `res_description`
* `identifier`
* `see_alsos`
* `maintainer`
* `author`
* `publishers`
* `contact_points`

Translated fields:
* `title`
* `keywords`
* `groups`
* `organization`
* `res_name`
* `res_description`

Find more detailed information about the Solr configuration in the [official Solr documentation](https://lucene.apache.org/solr/guide/6_6/index.html). The config and schema of opendata.swiss is available on GitHub:
* [solrconfig.xml](https://github.com/opendata-swiss/ckanext-switzerland/blob/master/solr/solrconfig.xml)
* [schema.xml](https://github.com/opendata-swiss/ckanext-switzerland/blob/master/solr/schema.xml)

The source of the referenced files in the `solr.xml` (e.g. `italian_stop.txt`, `fr_elision.txt`, etc.) can be found in the official CKAN-Repository of the current [CKAN-Version on Github](https://github.com/ckan/ckan/tree/master/ckanext/multilingual/solr). All other files (e.g. `stopwords.txt`) are provided by Solr.

<a name="query-syntax"></a>
## Query syntax

Solr has its own [query syntax](http://lucene.apache.org/core/3_6_0/queryparsersyntax.html) to write complex queries.
Depending on the query, Solr uses a different query parser to determine what to do.

<a name="search-operators"></a>
## Search operators

* Use +_{field}_:_{value}_ to include a search term, e.g. [`+title_en:power`](https://opendata.swiss/en/dataset?q=title_en%3Apower) to find all datasets, whose English title contains the word "power"
* Use -_{field}_:_{value}_ to exclude a search term, e.g. [`+title_en:power -title_en:hydraulic`](https://opendata.swiss/en/dataset?q=%2Btitle_en%3Apower+-title_en%3Ahydraulic) to find all datasets, whose English title contains the word "power", but not "hydraulic"
* Use `AND` to combine several search terms that all must match, e.g. [`keywords_en:(geology AND geophysics)`](https://opendata.swiss/en/dataset?q=keywords_en%3A%28geology+AND+geophysics%29) tp find all datasets that have both tags `geology` and `geophysics`
* Use `OR` to combine several search terms, where one of them must match, e.g. [`organization:(kanton-thurgau OR stadt-zurich)`](https://opendata.swiss/en/dataset?q=organization%3A%28kanton-thurgau+OR+stadt-zurich%29)

All of these options can be further combined together, e.g. [`organization:(kanton-thurgau OR stadt-zurich) karte`](https://opendata.swiss/en/dataset?q=organization%3A%28kanton-thurgau+OR+stadt-zurich%29+karte)

<a name="searchterm-suggestions"></a>
## Searchterm suggestions
The search-field of opendata.swiss provides searchterm-suggestions when a user types into it. For each language a self-contained Solr index is built multiple times throughout the day. That means that changes to datasets or new data won't be reflected in the suggestions immediately. 

The index is based on the following fields:

* `dataset-title` (translated)
* `keywords` (translated)
* `groups` (translated)
* `organization` (translated)
* `distribution-name` (translated)
* `author`
* `maintainer`
* `contact_points`
* `publishers`
* `identifier`
* `distribution-format`
