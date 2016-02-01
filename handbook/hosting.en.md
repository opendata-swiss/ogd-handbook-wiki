Title: Host data on the World Wide Web
Category: Publish
Handbook: yes
Tags:
Date: 2016-01-22
Slug: hosting
Authors:
Summary: First steps and guidelines in opening data on the Web and ensuring high availability.
Lang: en
Draft: yes


This topic covers a few pointers to help with publishing data on the web. To reference data on a web-based open data portal, it should be available online. Additional barriers, such as having to access protected networks or order CD-ROMs, reduce the accessibility of data. Are web publications harder to support? We contend that, given the alternatives, it is not. If the appropriate infrastructure is in place, web hosted data can be inexpensive and easy to support.

> Data should be priced at no more than a reasonable cost of reproduction, preferably as a free download from the Internet. This pricing model is achieved because your agency should not undertake any cost when it provides data for use.

> [Open Data Handbook](http://opendatahandbook.org/guide/en/how-to-open-up-data/#make-data-available-technical-openness)

### Checklist for hosting web data

Here are some aspects to consider when setting up web hosting for your data:

**<checkbox> Cloud vs. data center?**

Here we refer to the way your content is serviced on the Internet. In a data center, your organization would typically be responsible for running a "full stack", or entire collection, of applications required for web hosting. This means providing support for [DNS](https://en.wikipedia.org/wiki/DNS), [HTTP](https://en.wikipedia.org/wiki/HTTP), [SMTP](https://en.wikipedia.org/wiki/SMTP) and other critical protocols using specialized "server" programs. You often have the ability to decide on each of these components and pick the best combination. In a cloud environment, there is sometimes considerably less flexibility, however by centralizing administration and maintenance, the overall costs per site can be much lower.

**<checkbox> How accessible are backups?**

Preparing for disasters, and ensuring that data does not get lost during updates or changes, are extremely important tasks in setting up for long-term hosting. Ensure that you know how to get duplicates of your data, which are ideally being [versioned](https://en.wikipedia.org/wiki/Version_control) for selective restoration, find out how much time and effort this process takes - and test it in advance, to be calm and prepared for any eventuality.

**<checkbox> Are there bandwidth restrictions?**

As every smartphone user knows, access to data comes at a cost. Whether it is uploading large datasets, or potentially being restricted from sharing your data to a large number of users, check with your hosting provider on what are the financial and technical aspects of this question. For instance, some providers can put special measures in place to "scale up" the rate at which your content is being distributed ahead of a marketing campaign or publicity - ensuring that none of your visitors get to see error messages or outages.

**<checkbox> Is there a redundancy measure in place?**

[Redundancy](https://en.wikipedia.org/wiki/Redundancy_(engineering)) is the concept of having alternative copies of the same information. In the case of web hosting, this often means having multiple servers in multiple locations provisioning the exact same content. This is useful for maximing performance across the world, or having a "safe failover" - in case one of the copies (for example, of an e-commerce web site) is for some reason inaccessible, one of the others immediately/automatically take over, and no business is lost.
