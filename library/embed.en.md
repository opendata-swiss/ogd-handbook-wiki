---
Title: Analysis of options for embedding datasets from opendata.swiss
Category: Library
Template: document
Tags: support
Date: 2016-12-01
Slug: embed
Authors: Oleg Lavrovsky
Summary: This working document analyses the Web publishing capabilities of CKAN portals, in order to present and discuss options for sharing rich content on third-party sites.
Lang: en
Draft: yes
toc_run: true
---


Opendata.swiss is the central reference catalog for open government data in Switzerland, and some people may like to present published datasets on their own website. Several government institutions even have their own data portals, on which they would like to feature any datasets which they maintain on *opendata.swiss* - and integrate this with other information on their website.

This document discusses a range of technical options for embedding content from the CKAN open data platform on other websites website, with these goals covered:

- The datasets should be well presented, the information accurate and up-to-date - in other words, where a copy-and-paste of the information is insufficient.
- Data publishers need to be able to show on their own website a dynamic selection from the central catalogue. Usually, this selection is filtered to the datasets they themselves publish.

We describe several recommended options here - from linking to resources from the catalogue, to embedding parts of the functionality from the portal on other websites.

## Cards

Standards like the [Open Graph protocol](http://ogp.me) and [oEmbed](http://oembed.com) not only improve the way search engines and other machine 'users' access the platform, they also make it easy to bring in rich content from different sites through standard interfaces.

Using these standards, sharing links to datasets on *opendata.swiss* is vastly improved: simply by pasting in the URL to a dataset on a platform with support for the protocol (like Discourse or Wordpress), visitors of your site see a "card" with the title and description and possibly an image of the page. If you see a plain link, then embedding is not supported or working - but visitors can still navigate to the target page.

Here is an example of how a dataset renders at time of writing in the [Slack](https://slack.com/) web application using basic HTML5 metadata:

![](../../images/embed/ckan-default.png)

Compare this to a dataset rendered using Open Graph from the CKAN instance at [data.beta.nyc](http://data.beta.nyc/showcase/nyc-marriage-index), which appears like this in the same client:

![](../../images/embed/ckan-opengraph.png)

This option would not allow search and other interactivity, but could provide a basis for it (further discussion in the next option). Initially it would make it easy for content owners to use their own existing platforms to present the datasets in a nice way just by linking to the datasets.

Open Graph support is available in more [recent versions](https://github.com/ckan/ckanext-showcase/pull/7) of CKAN. Another example deployment with support is the open data portal of the [City of Zurich](https://data.stadt-zuerich.ch/).

There are various open-source packages and libraries you can use as a developer to add support for reading Open Graph metadata in your Web project. Here are some examples: [pelican-open_graph](https://github.com/whiskyechobravo/pelican-open_graph) (Pelican is used in this Handbook), [opengraph by erikriver](https://github.com/erikriver/opengraph), [Drupal](https://www.drupal.org/project/oembed), [JavaScript/Node.js](https://www.npmjs.com/package/open-graph), and a middleware API at [Opengraph.io](https://www.opengraph.io/documentation/).

Furthermore, category and search result pages could also be tagged using the same mechanisms. This way third party websites could have a summary view into the datasets simply by linking to the appropriate URL. As far as we can tell, this is currently not supported or planned in CKAN. For more in-depth discussion of metadata support see: [Make consistent all forms of RDF output from CKAN #1890](https://github.com/ckan/ckan/issues/1890).

In summary, starting with newer releases of CKAN, pasting links from the open data portal into a Web platform that supports the Web metadata protocols enables a richer sharing experience.

## Widget

Similar to the rich media widgets from Twitter and other websites, a script can be added to pages which loads remote content using JavaScript. It is possible to provide users with a code snippet that could be configured according to their needs.

The portal's [Data Viewer](http://docs.ckan.org/en/latest/maintaining/data-viewer.html) is a feature that already has resource embedding built in, including the ability to whitelist sites where this may be deployed using a `resource proxy` configuration option. This capability has been available since CKAN 2.1.

The [ckan.js](https://github.com/okfn/ckan.js) project is a JavaScript library that could be used to connect to CKAN from within the browser. In order to overcome Cross-origin resource sharing (CORS) restrictions, a backend service would ideally be hosted on the same machine as the scripts. This could just be a proxy to the data portal.

We have put together a JavaScript widget based on `ckan.js` which displays the same information about datasets as the standard search. It uses the [CKAN API](http://docs.ckan.org/en/latest/api/) to run search queries, and the [jQuery](http://jquery.com/) and [LoDash](https://lodash.com/) libraries to render the result into the Web page.

Note that due to lack of CORS support, we used JSONP to mitigate cross-site scripting restrictions. This approach is not aligned with current best practices, and therefore we recommend if possible that developers put in place a *proxy service* as recommended in the next section.

Example of rendering a search from *opendata.swiss* in this widget:

![](../../images/embed/ckan-widget.png)

This is made by adding the following code to the page, querying the portal for "RDF" as a search term:

```
<script src="ckan-embed.min.js"></script>
<div id="opendata-swiss"></div>
<script>
ck.embed('#opendata-swiss', 'https://opendata.swiss/', 'RDF');
</script>
```

Full source code and deployment instructions are [available here](https://github.com/Datalets/ckan-embed).

## Middleware

It would be wise to monitor the API calls of the proxying server to specific calls for security and performance. An intermediate service backend that uses something like the Python [ckanapi client](https://github.com/ckan/ckanapi) could be used to facilitate this, or a load balancing server.

Open Graph support (as discussed in the Cards section) would make it possible to use a compatible client-side library (e.g.: [Oembetter](https://github.com/punkave/oembetter)). Furthermore, soon on the *opendata.swiss* roadmap there will be support for requesting DCAT-AP compatible RDF for any dataset. While this does not mean that the data itself is linked, it would also allow a more generic solution to displaying the metadata.

This option could especially be a widely accessible solution if wrapped together in a reusable package for third party developers. A 'configurator' similar to [Twitter Publish](https://publish.twitter.com) would make it even easier for non-technical users.

Note that performance issues could potentially be compounded by availability and connectivity of the proxying server, so hosting this widget needs to be done with care. One straightforward option would be to add this functionality to CKAN itself, however there may be reasons why platform owners may wish to separate the 'sharing' service from core functionality.

## Frames

Using standard HTML IFRAMEs or EMBEDs, subsets or links from the portal can be placed directly into the page. This is the basic way content gets embedded across sites, supported in all browsers. The main advantage is ease of use, essentially it is just an HTML snippet that needs to be placed somewhere on a web page.

Through the browser's sandboxing of the frames, this has the least impact from a security and performance standpoint. It is actually essentially the same as if the user opens a link in a new tab, except the other web page is shown within a block on the current page, and it scrolls along with the content.

However, from an accessibility and usability perspective this option presents several challenges and is **NOT RECOMMENDED**:

- *opendata.swiss* has its own branding and navigation which may get in the way - the user may be confused about what is actually being presented.
- It is difficult to navigate with the keyboard into an IFRAME and visitors who rely on text-to-speech will be impeded - this is an option unlikely to meet [accessibility requirements](http://www.accessibility-checklist.ch/).
- Due to the security measures of the browser, no communication can happen between the sites. It is possible to track users of the IFRAME through advanced web analytics, but only on the destination site - the host site will get no data on user behavior.

A possible compromise solution to the first two issues would be create an "embed view" template through a CKAN plugin which renders the requested page with alternative branding that is more conducive to usage in frames. For instance, the logo could be smaller, and the navigation replaced with a link to open the portal in a new window. The content itself would be reformatted and simplified - no footers, simpler structure, and so on.

In the meantime, we would suggest using the IFRAME tag with an anchor (#field-order-by) that makes the view skip directly to content on loading:

Example code for search result (with `#field-order-by` anchor):
```
<iframe
width="100%" height="600" frameborder="0"
style="border:0;margin:0;padding:0"
src="https://opendata.swiss/en/dataset?q=RDF&res_format=HTML&sort=score+desc%2C+metadata_modified+desc#field-order-by"></iframe>
```

Example code for a dataset (with `#content` anchor):
```
<iframe
width="100%" height="600" frameborder="0"
style="border:0;margin:0;padding:0"
src="https://opendata.swiss/de/dataset/jahresrechnungen-der-korperschaften-des-kantons-zurich#content"></iframe>
```

## Further options

We investigated the possibility of supporting publishers of 'static sites', such as this handbook. The deployment of rich content could be extended with dynamic crawling and updating of content during the publication process without reliance on cross-site requests in the browser. This would however require technical effort for the specific publishing platforms, and come with the synchronicitiy issues of the Cards option - i.e. the embedded information will only be as recent as the latest publication. Such an approach is described in the [govpack package](https://www.npmjs.com/package/govpack).

Access to regular exports from the portal's underlying database - in other words, federated or raw data access - would enable content providers to run their own mini-sites synchronised to the central port. It is currently not clear how prominently portal federation will feature on CKAN's roadmap, while third party extensions like [ckanext-odn-ic2pc-sync](https://github.com/OpenDataNode/ckanext-odn-ic2pc-sync) promise this kind of functionality. For a more high level discussion of the advantages of hosting federated platforms for data discovery, see [Zhang Haojie et al., 2015](https://www.researchgate.net/publication/283356205_Data-as-a-Service_A_Cloud-Based_Federated_Platform_to_Facilitate_Discovery_of_Private_Sector_Datasets).

Access to the metadata of the portal itself would be a sound option for the most technical users of the open data platform. They would however most likely need to host CKAN, or at least be familiar with its schema, to make use of such data. A compromise option, such as static snapshots of the API, could be another strategy to pursue in the future.

In the meantime, we recommend the Cards option with Open Graph support for non-technical users, and the Widget that uses JavaScript for rendering content for technical users.
