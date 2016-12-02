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

Opendata.swiss is the central reference catalog for open data in Switzerland. Naturally, organisations from across the country are interested in publishing and consuming OGD in diverse ways. It should be possible for every data publisher to present datasets on their own website. For example, several cantons and communes have their own data portals, on which they would like to feature or integrate Opendata.swiss datasets, some which they even maintain themselves.

## Goals of embedding content

- The datasets should be well presented, and the information accurate and up-to-date. In other words a copy-and-paste solution is in many cases insufficient.
- Data publishers of the Swiss OGD Project need to have the possibility to show on their own website a selection from the catalogue.
- These could also be entire categories / search filters combining multiple datasets.

For this project we are considering all options beyond plain linking of the resources from the catalogue. Integration with the [LINDAS project](http://egovernment.ch/lindas) is the initial test platform and target for this analysis.

### Option 1: Frames

Using standard HTML IFRAMEs or EMBEDs, subsets or links from the portal can be placed directly into the page. This is the basic way content gets embedded across sites, supported in all browsers. The main advantage is ease of use, essentially it is just an HTML snippet that needs to be placed somewhere on a web page.

Through the browser's sandboxing of the frames, this has the least impact from a security and performance standpoint. It is actually essentially the same as if the user opens a link in a new tab, except the other web page is shown within a block on the current page, and it scrolls along with the content.

However, from an accessibility and usability perspective this is an undesirable option. First of all, [opendata.swiss](http://opendata.swiss) has its own branding and navigation which may get in the way - the user may be confused about what is actually being presented. It is difficult to navigate with the keyboard into an IFRAME, and most text readers will be impeded - not a solution that is likely to meet [accessibility requirements].

Furthermore, due to the security measures of the browser, no communication can happen between the sites. It is possible to track users of the IFRAME through advanced web analytics, but only on the destination site - the host site will get no data on the users behavior.

A possible compromise solution here would be create an "embed view" template in CKAN which renders the requested page with alternative branding that is more conducive to usage in frames. For instance, the logo could be smaller, and the navigation replaced with a link to open the portal in a new window. The content itself would be reformatted and simplified - no footers, etc.

### Option 2: Open Graph protocol and/or oEmbed

Standards like the [Open Graph protocol](http://ogp.me) and [oEmbed](http://oembed.com) not only improve the way search engines and other "machine users" access the platform, they make it easy to brig in rich content from different sites through standard interfaces.

Using these standards, sharing links to datasets on this site is improved - simply by pasting in the URL to a dataset on a platform like Discourse or Wordpress, you should see a "card" with the title and description and possibly an image of the page. If you see a plain link, then embedding is not supported or working.

This would not allow search and other inline options, but could be a good basis for them (see option 3). Initially it would make it easy for content owners to use their own existing platforms to present the datasets in a nice way just by linking to the datasets.

There is no support for oEmbed in CKAN yet, but there is basic OpenGraph support as of [recent versions](https://github.com/ckan/ckanext-showcase/pull/7). An example deployment with this support is [data.beta.nyc](http://data.beta.nyc/showcase/nyc-marriage-index). Data viewer has an [embedding feature](http://docs.ckan.org/en/ckan-2.2.3/data-viewer.html#embed-previews) since 2.1.

There are various open-source packages/libraries you can use as a developer to add support to your project. Here are some examples: [pelican_oembed](https://github.com/bcaller/pelican_oembed) (Pelican is used in this Handbook), which is based on [PyEmbed](https://github.com/pyembed/), [python-oembed](https://pypi.python.org/pypi/python-oembed), [pelican-open_graph](https://github.com/whiskyechobravo/pelican-open_graph), [opengraph by erikriver](https://github.com/erikriver/opengraph), [Drupal](https://www.drupal.org/project/oembed), [JavaScript/Node.js](https://www.npmjs.com/package/open-graph)

Outcomes of our testing with opendata.swiss:

- Host connectivity issues put the publication process at risk. Safeguards like caching and loading of previous results will need to be implemented.
- Furthermore no real way around the issue of how to keep the information synchronised - it will depend on the publication cycles, and potentially put more load on the backend.
- No way to automatically pull in a list of links (e.g. search results) limits the usefullness of this approach.
- Recommendation is nevertheless to support OpenGraph or oEmbed on a per-dataset level, for instance so that bloggers can easily republish CKAN links.

### Option 3: Scripted widget and/or SaaS

Similar to the rich media widgets from Twitter and other websites can be added to third-party pages through loading remote JavaScript, it should be possible to provide users with a code snippet that could be configured according to their needs.

CKAN's [Data Viewer](http://docs.ckan.org/en/latest/maintaining/data-viewer.html) is a feature that already has resource embedding built in, including the ability to whitelist sites where this may be deployed using a `resource proxy` configuration option.

The [ckan.js](https://github.com/okfn/ckan.js) project is a JavaScript library that could be used to connect to CKAN from within the browser. In order to overcome Cross-origin resource sharing (CORS) restriction, a backend service needs to be hosted on the same machine as the scripts.

We have put together a demonstration widget which displays the same information about datasets as the standard search. It uses [ckan.js](https://github.com/okfn/ckan.js) to connect to the [CKAN API](http://docs.ckan.org/en/latest/api/) and run search queries, and the [jQuery](http://jquery.com/) and [Underscore](http://underscorejs.org/) libraries to render the result in an HTML5 template.

Outcomes of our testing with opendata.swiss:

- This could be a good solution if wrapped together in a reusable package for third party developers.
- A 'configurator' similar to [Twitter Publish](https://publish.twitter.com) would make it even easier for non-technical users.
- Performance issues could potentially be compounded by availability and connectivity of the proxying server, so hosting this widget needs to be done with care.
- It would be wise to limit the API calls of the proxying server to specific calls for security and performance. However, this requires an actual service backend that uses something like the Python [ckanapi client](https://github.com/ckan/ckanapi).
