---
layout: post
title: How To Setup Naked Domain SSL With Github Pages
categories: [Development, Jekyll]
tags: [dev, jekyll, ssl]
---

Add a free Cloudflare SSL certificate to your GitHub pages custom domain.

Create a free [Cloudflare](https://www.cloudflare.com/) account and login. Add new site and scan the server, Cloudflare will return two name server addresses.

![Add new site](/uploads/2017-04-05_1.png)

Go to your domain registrar admin panel and add Cloudflare nameservers.

Next, on Cloudflare under DNS tab add your CNAME an A records in DNS menu in CloudFlare then click on status.

![Add your CNAME an A records](/uploads/2017-04-05_2.png)

Next, under Crypto tab add set Flexible SSL mode.

![Flexible SSL mode](/uploads/2017-04-05_3.png)

Next, under Page Rules tab add these two regex patterns:

![Flexible SSL mode](/uploads/2017-04-05_4.png)

![Flexible SSL mode](/uploads/2017-04-05_5.png)

![Flexible SSL mode](/uploads/2017-04-05_6.png)

Last step, go to your GitHub pages repository settings and set custom domain name.

![Flexible SSL mode](/uploads/2017-04-05_7.png)
