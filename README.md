# Advanced Campaigns Reporting
The Plugin lets you track up to five Campaigns parameters (name, source, medium, keyword, content).

The default Campaign parameters are called: pk_campaign, pk_source, pk_medium, pk_keyword, pk_content and pk_cid.

If you already have URLs tagged with Google Analytics parameters these are supported: utm_campaign, utm_source, utm_medium, utm_term, utm_content and utm_id

An example landing page URL would be:
```
/offer?pk_campaign=Best-Seller&pk_source=Newsletter_7&pk_medium=email
```

## Features
 * Powerful Real time Analytics Reports of all your Campaign Marketing
 * Detects Campaign parameters from the landing page URL, within the query string or in the #hash string
 * The Referrers>Overview report displays a left column "Referrers Overview" with a list of reports that can be loaded on click.
   This report viewer now also lists the new Campaign reports under "View Referrers by Campaign".
 * The content of Referrers> Campaign will be replaced with the new enhanced Campaigns reports.
 * The default Referrers Campaign widget and API are working as before.
 * The campaign reports are available in Piwik Mobile and can be sent as Scheduled reports (by email, as HTML or PDF)
 * Segment editor: a new "Campaigns" category lists the five new segment for each campaign dimension
 * The new Campaign reports can be added as widgets in your personalized Dashboard
 * Access the Campaign Report data by the API
 * Comes with automated tests to ensure the Plugin works as expected
 * Will track up to 250 characters for each of the five Campaign dimension

## Notes
 * To archive all values in the Campaign reports and not truncate rows, set eg.

```
[General]

datatable_archiving_maximum_rows_referrers = 10000

datatable_archiving_maximum_rows_subtable_referrers = 10000
```

## Ideas for improvement
 * To improve data acquisition accuracy, we could extend the piwik.js class to store in first party cookies
 the five campaign dimensions. This would increase the accuracy of Goal conversions and Ecommerce conversions attributions
 for these conversions made at least one day after the first visit with a campaign set.
 * Add friendly Tracking API parameters to collect campaign dimensions.
 campaignName cn, campaignSource cs, campaignMedium cm, campaignContent cc, campaignId ci.
 Currently it is possible if set in the parameters of the actual tracked URL set in parameter &url=
