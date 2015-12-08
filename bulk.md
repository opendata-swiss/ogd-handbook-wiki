Title: When data is downloadable in bulk
Category: Publish
Tags:
Date: 2015-1-1
Slug: bulk
Authors:
Summary: On the benefits and challenges of providing bulk datasets and direct access to databases in an OGD portal.
Lang: en
Draft: yes

In this chapter we talk about some of the benefits and challenges of providing bulk datasets in an OGD portal. This is especially relevant to publishers of larger datasets, where most end-users would use an API endpoint or web application to query a subset of the entire database.

### Why open data in bulk?

> The data should be available as a complete set. If you have a register which is collected under statute, the entire register should be available for download. A web API or similar service may also be very useful, but they are not a substitutes for bulk access.

[Open Data Handbook](http://opendatahandbook.org/guide/en/how-to-open-up-data/#make-data-available-technical-openness)

### Why would this be a problem?

Here are some common problems encountered by data owners:

**The data is too large to be easily transmitted**

For example, files of several gigabytes may be impossible to completely download on an unstable Internet connection. You may suggest the use of a download manager - software that allows resuming downloads - as a workaround. Another option is to provide the large files through streaming download technologies like BitTorrent.

**The data format is too specialized to be easily used**

When sharing database backups, it is necessary to also document how to open the resulting files. In some cases this even requires specialist work, for example when there are industry-specific data formats, or databases with very complex table relationships that are difficult to query. In such cases an export into an intermediary format, such as SQLite, could be advisable.
