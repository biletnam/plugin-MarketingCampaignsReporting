# Marketing Campaigns Reporting

## Description

Measure the effectiveness of your marketing campaigns. 
Measure up to five of your marketing campaigns channels: name, source, medium, keyword, content. 
Access all your campaign analytics reports into a unified interface and track the effectiveness of all your channels.
Supports any kind of campaign and channel: Adwords, Facebook, Twitter, Youtube, Display advertising, Custom Marketing campaigns, Email newsletters. 

### The Marketing URL Builder

[Generate your trackable marketing URLs with our URL Builder tool.](https://piwik.org/docs/tracking-campaigns-url-builder/)

### Tracking campaigns

To track a campaign, you add special URL parameters to your URLs.

The URL parameters are:

* `pk_campaign` (campaign name such as mailing_2017_03 or Easter_Sale), 
* `pk_source` (campaign source such as google or facebook), 
* `pk_medium` (campaign medium such as email or cpc), 
* `pk_keyword` (campaign keyword), 
* `pk_content` (campaign content),
* `pk_cid` (campaign ID code).

If you already have URLs tagged with Google Analytics parameters these are also supported: 

* `utm_campaign`, 
* `utm_source`, 
* `utm_medium`, 
* `utm_term`, 
* `utm_conten`t,
* `utm_id`.

For example if your Ad URL or landing page URL is `example.com/offer`, you would track all clicks on this URL by 
adding one or more of the parameters above: 
```
example.com/offer?pk_campaign=Best-Seller&pk_source=Newsletter_7&pk_medium=email
```

### Features
 * Real time Analytics Reports of all your Campaign Marketing.
 * Detects Campaign parameters from the landing page URL, within the query string or in the #hash string.
 * The Referrers>Overview report displays a left column "Referrers Overview" with a list of reports that can be loaded on click.
   This report viewer now also lists the new Campaign reports under "View Referrers by Campaign".
 * The content of Referrers> Campaign will be replaced with the new enhanced Campaigns reports.
 * The default Referrers Campaign widget and API are working as before.
 * The campaign reports are available in Piwik Mobile and can be sent as Scheduled reports (by email, as HTML or PDF).
 * Segment editor: a new "Campaigns" category lists the five new segment for each campaign dimension (campaign name, campaign keyword, campaign source, campaign medium, campaign content).
 * Add Marketing campaign reports to your personalized Dashboard.
 * Access the Campaign Report data with the Marketing Campaigns Reporting API.
 * Will track up to 250 characters for each of the five Campaign dimension.
 * Get automatic [email and sms reports](https://piwik.org/docs/email-reports/) for your campaigns, or send them to your colleagues or customers. 

### Reports for more than 1,000 campaigns

In the Campaign reports by default Piwik will only archive the first 1000 rows (your 1000 most popular campaigns). 
To report on all your campaigns you can configure Piwik so it does not truncate your data. 
For example to keep the top 10,000 campaigns edit your `config/config.ini.php` and add the following:

```
[General]
datatable_archiving_maximum_rows_referrers = 10000
datatable_archiving_maximum_rows_subtable_referrers = 10000
```

### Customising your campaign parameters 

It is possible to configure custom names for campaign parameters. In order to do so you have add config to config.ini.php file.
If you configure any campaign parameter this configuration will overwrite default config for this parameter.

```
[AdvancedCampaignReporting]
campaign_name = "pk_campaign,piwik_campaign,pk_cpn,utm_campaign"
campaign_keyword = "pk_keyword,piwik_kwd,pk_kwd,utm_term"
campaign_source = "pk_source,utm_source"
campaign_medium = "pk_medium,utm_medium"
campaign_content = "pk_content,utm_content"
campaign_id = "pk_cid,utm_id"
```

For example, by default parameter `campaign_name` track following parameters if they are found in URL: `'pk_campaign', 'piwik_campaign', 'pk_cpn', 'utm_campaign'`. If you configure `campaign_name` like this `campaign_name="pk_campaign,custom_name_parameter"`, then parameter `campaign_name` will detect only presence of `pk_campaign` and `custom_name_parameter` in URL. `piwik_campaign`, `pk_cpn`, `utm_campaign` will be ignored until they are present in config.  


## Changelog

 * 3.0.0 (March 2017) Plugin forked by Piwik team + Renamed + Compatibility with Piwik 3
 * 1.4.0 Added possibility to configure custom campaign parameters names
 * 1.3.1 Better support for campaign parameters behind hash tag (#)
 * 1.3.0 Compatibility with Piwik 2.16.0
 * 1.2.0 (Nov 10th 2015) - Plugin comaptibility with Piwik 2.15.0
 * 1.1.1 (Sept 3rd 2015) - Campaign reports now display your campaign report data even for campaign data before you activated AdvancedCampaignReporting
 * 1.1.0 (July 28th 2015)
 * 1.0.8 (Apr 1st 2015) - Exclude Google Analytics campaign parameters from the Page URLs
 * 1.0.6 (Nov 17th 2014) - Documentation
 * 1.0.5 (Nov 14th 2014) - Detect new URL parameters: piwik_campaign, pk_cpn and for Keywords: pk_kwd, piwik_keyword
 * 1.0.4 (Nov 4th 2014) - View Goals by Campaign Dimension in the Goals & Ecommerce reports
 * 1.0.3 (Oct 1st 2014) - Released for free on the [Piwik Marketplace](http://plugins.piwik.org/)

