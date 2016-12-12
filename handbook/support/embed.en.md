---
Title: Analysis of options for embedding datasets from opendata.swiss
Category: Support
Handbook: yes
Tags:
Date: 2016-12-01
Slug: embed
Authors:
Summary: This working document analyses the Web publishing capabilities of CKAN portals, in order to present and discuss options for sharing rich content on third-party sites.
Lang: en
Draft: yes
toc_run: true
Hidden: yes
---


Opendata.swiss is the central reference catalog for open government data in Switzerland. Some data publishers may like to present published datasets on their own website. For example, several government institutions have their own data portals on which they would like to feature datasets which they maintain - and integrate this with other information on their website.

On this page you can find out how to embed opendata.swiss on your website, with these goals covered:

- The datasets should be well presented, and the information accurate and up-to-date. (In other words, where a copy-and-paste is insufficient)
- Data publishers of the Swiss OGD Project need to have the possibility to show on their own website a selection from the catalogue. (Usually, filtered to the datasets they themselves publish)

We describe several recommended options here going beyond copy-and-paste and plain links to resources from the catalogue.

## Cards

Standards like the [Open Graph protocol](http://ogp.me) and [oEmbed](http://oembed.com) not only improve the way search engines and other "machine users" access the platform, they also make it easy to bring in rich content from different sites through standard interfaces.

Using these standards, sharing links to datasets on opendata.swiss is improved: simply by pasting in the URL to a dataset on a platform with support for the protocol (like Discourse or Wordpress), visitors of your site see a "card" with the title and description and possibly an image of the page. If you see a plain link, then embedding is not supported or working - but visitors can still navigate to the target page.

This option would not allow search and other interactivity, but could be a good basis for them (see next option). Initially it would make it easy for content owners to use their own existing platforms to present the datasets in a nice way just by linking to the datasets.

Basic OpenGraph support is available in more [recent versions](https://github.com/ckan/ckanext-showcase/pull/7) of CKAN. An example deployment with this support is [data.beta.nyc](http://data.beta.nyc/showcase/nyc-marriage-index). The Data Viewer also has an [embedding feature](http://docs.ckan.org/en/ckan-2.2.3/data-viewer.html#embed-previews) since 2.1.

There are various open-source packages and libraries you can use as a developer to add support to your project. Here are some examples: [pelican-open_graph](https://github.com/whiskyechobravo/pelican-open_graph) (Pelican is used in this Handbook), [opengraph by erikriver](https://github.com/erikriver/opengraph), [Drupal](https://www.drupal.org/project/oembed), [JavaScript/Node.js](https://www.npmjs.com/package/open-graph), and a middleware API at [Opengraph.io](https://www.opengraph.io/documentation/).

<a href="http://opendataswiss-lindas-test.datalets.ch/embed-opengraph.html" target="_blank" class="btn btn-default">Embedded Cards example (offsite)</a>

## Frames

Using standard HTML IFRAMEs or EMBEDs, subsets or links from the portal can be placed directly into the page. This is the basic way content gets embedded across sites, supported in all browsers. The main advantage is ease of use, essentially it is just an HTML snippet that needs to be placed somewhere on a web page.

Through the browser's sandboxing of the frames, this has the least impact from a security and performance standpoint. It is actually essentially the same as if the user opens a link in a new tab, except the other web page is shown within a block on the current page, and it scrolls along with the content.

However, from an accessibility and usability perspective this option presents several challenges:

- [opendata.swiss](http://opendata.swiss) has its own branding and navigation which may get in the way - the user may be confused about what is actually being presented.
- It is difficult to navigate with the keyboard into an IFRAME and visitors who rely on text-to-speech will be impeded - this is an option unlikely to meet [accessibility requirements](http://www.accessibility-checklist.ch/).
- Due to the security measures of the browser, no communication can happen between the sites. It is possible to track users of the IFRAME through advanced web analytics, but only on the destination site - the host site will get no data on user behavior.

A possible compromise solution to the first two issues would be create an "embed view" template through a CKAN plugin which renders the requested page with alternative branding that is more conducive to usage in frames. For instance, the logo could be smaller, and the navigation replaced with a link to open the portal in a new window. The content itself would be reformatted and simplified - no footers, simpler structure, and so on.

In the meantime, we would suggest using the IFRAME tag with an anchor (#field-order-by) that makes the view skip directly to content on loading:

Example code:
```
<iframe
width="100%" height="600" frameborder="0"
style="border:0;margin:0;padding:0"
src="https://opendata.swiss/en/dataset?q=RDF&res_format=HTML&sort=score+desc%2C+metadata_modified+desc#field-order-by"></iframe>
```

<a href="http://opendataswiss-lindas-test.datalets.ch/embed-iframe.html" target="_blank" class="btn btn-default">Embedded Frame example (offsite)</a>

## Widgets

Similar to the rich media widgets from Twitter and other websites, a script can be added to pages which loads remote content using JavaScript. It is possible to provide users with a code snippet that could be configured according to their needs.

CKAN's [Data Viewer](http://docs.ckan.org/en/latest/maintaining/data-viewer.html) is a feature that already has resource embedding built in, including the ability to whitelist sites where this may be deployed using a `resource proxy` configuration option.

The [ckan.js](https://github.com/okfn/ckan.js) project is a JavaScript library that could be used to connect to CKAN from within the browser. In order to overcome Cross-origin resource sharing (CORS) restriction, a backend service needs to be hosted on the same machine as the scripts.

OpenGraph or oEmbed support (as discussed in the Cards section) would make it possible to use a compatible client-side library (e.g.: [Oembetter](https://github.com/punkave/oembetter)). Furthermore, soon on the opendata.swiss roadmap there will be support for requesting DCAT-AP compatible RDF for any dataset. While this does not mean that the data itself is linked, it would also allow a more generic solution to displaying the metadata.

This option could be a good solution if wrapped together in a reusable package for third party developers. A 'configurator' similar to [Twitter Publish](https://publish.twitter.com) would make it even easier for non-technical users.

Note that performance issues could potentially be compounded by availability and connectivity of the proxying server, so hosting this widget needs to be done with care.

It would also be wise to limit the API calls of the proxying server to specific calls for security and performance. However, this requires an actual service backend that uses something like the Python [ckanapi client](https://github.com/ckan/ckanapi).

We have put together a demonstration widget which displays the same information about datasets as the standard search. It uses [ckan.js](https://github.com/okfn/ckan.js) to connect to the [CKAN API](http://docs.ckan.org/en/latest/api/) and run search queries, and the [jQuery](http://jquery.com/) and [Underscore](http://underscorejs.org/) libraries to render the result in an HTML5 template:

<a href="http://opendataswiss-lindas-test.datalets.ch/embed-widget.html" target="_blank" class="btn btn-default">Embedded Frame example (offsite)</a>

## Further options

We are also investigating the possibility of supporting publishers of 'static sites', such as this handbook. We could support the deployment of rich content with dynamic crawling and updating of content during the publication process without reliance on cross-site requests in the browser.

Access to regular exports from the portal's underlying database - in other words, federated or raw data access - would enable content providers to run their own mini-sites synchronised to the central port. It is currently not clear how prominently portal federation will feature on CKAN's roadmap, while third party extensions like [ckanext-odn-ic2pc-sync](https://github.com/OpenDataNode/ckanext-odn-ic2pc-sync) promise this kind of functionality.

For a more high level discussion of the advantages of hosting federated platforms for data discovery, see [Zhang Haojie et al., 2015](https://www.researchgate.net/publication/283356205_Data-as-a-Service_A_Cloud-Based_Federated_Platform_to_Facilitate_Discovery_of_Private_Sector_Datasets).
