---
title: Enable HTTPS for Sites Using Customized Base Domains
description: Learn how to enable HTTPS for all sites using your Organization's customized base domain.
keywords: https development domain, base domain, change dev url, change development domain, change base domain, dev url, wildcard, cname, edge, dns, https
---
Enable HTTPS on all sites utilizing your organization's customized base domain by adding a [Wildcard SSL Certificate](/docs/articles/sites/domains/adding-a-ssl-certificate-for-secure-https-communication#wildcard) to your main site.

Customized base domains on Pantheon replace `pantheon.io` as the base domain for all sites associated with your organization. This feature is available to Pantheon Partners, Strategic Partners, Enterprise accounts, Resellers, and OEM Partners. For more information, see [Customizing Your Base Domain](/docs/articles/organizations/base-domains)
## Before You Begin
Be sure that you have:

- A customized base domain, otherwise  [request one](/docs/articles/organizations/base-domains/#request-the-base-domain) and [consider the effects](/docs/articles/organizations/base-domains/#effects-and-considerations) before proceeding
- A Wildcard SSL Certificate from an [SSL Provider](/docs/articles/sites/domains/adding-a-ssl-certificate-for-secure-https-communication#ssl-providers)

## Create an HTTPS endpoint
[Add a Wildcard SSL Certificate](/docs/articles/sites/domains/adding-a-ssl-certificate-for-secure-https-communication#steps-to-enable-ssl) to your main site's Live environment. This will create an HTTPS endpoint for all sites utilizing your base domain. Sites associated with the organization (e.g. `projectsite-env.pantheonpartner.com`) and the main site (e.g. `www.pantheonpartner.com`) will be served using the same Wildcard certificate.
### Pantheon Partners
Running your agency's homepage on Pantheon is **free**, as is the option to add an SSL. This means you can use your main site as an HTTPS endpoint at no cost. This offer is only available to Partner level organizations.
## Configure DNS
Direct all DNS to the IP address found within the **Domains/SSL** tab of the Live environment, like so:
```
*.pantheonpartner.com A [IP for TLS/SSL endoint]
```
## Development Domains
Development domains are customized base domains that differ from your agency's main domain (e.g. `partnerprojects.com` for development and `pantheonpartner.com` for the homepage).

Enable HTTPS on all sites using your customized development domain by adding one certificate to the Live environment and another to the Test environment. Configure the different DNS records accordingly using the IP address found within the **Domains/SSL** tab of the respective environments.
