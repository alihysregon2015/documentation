---
title: Gandi & Pantheon: Pointing your DNS
description: Learn how to point your domain's DNS to your Pantheon Drupal or WordPress site using Gandi.
category:
  - going-live
  - managing
keywords: dns, dns records, point your domain, point domain to pantheon, pointing your domain to your pantheon site, dns host, dns configuration, add domain to a site, gandi, point gandi domain to pantheon, redirect gandi domain to pantheon, gandi domain dns
---
[Gandi](https://www.gandi.net/) provides you with a nice, clean list of your domains. Click on the domain that you are interested in pointing to Pantheon.

## Domain Configuration Page

The domain portal contains all relevant registration information for your domain. Proper resolution for your Pantheon site depends on CNAMEs and A records. To configure these, you'll have to edit the DNS Zone Record. Click **Edit the Zone** to proceed to the configuration page.

## Configure Zone Records on Gandi

Gandi requires you to make a copy of your default Zone Record to ensure that you don't botch your default configuration. Click **Make New Version** to create a new version to edit.

Gandi has two edit modes: Normal and Expert. Select the **Expert** editing mode to edit the Zone Record as a text file, instead of inputting values into the Gandi fields and letting them do the formatting.

You'll need to edit the A record and CNAME. The A record shows something like:
```nohighlight
@ 10800 IN A 217.70.184.38
```
And the www CNAME shows:
```nohighlight
www 10800 IN CNAME webredir.vip.gandi.net.
```

1. Point the A record in the zone file to 192.237.224.60:
```nohighlight
@ 192.237.224.60
```
2. Next, change the www CNAME to match the following:
```nohighlight
www 300 IN CNAME live-example.pantheon.io.
```

<div class="alert alert-warning" role="alert">
<h4>Note</h4>
Be sure to include the trailing "."</div>

## Add Your Domain to Pantheon

In order for your domain to resolve to your Pantheon site, you need to add it to your Pantheon Site Dashboard. See [Domains and DNS](/docs/articles/sites/domains#step-2-add-a-domain-to-a-site-environment) for more details.
