# Configuring Your Firewall

!!! info ""
    You are welcome to ask for help in our [community chat](https://link.photoprism.app/chat).
    [Sponsors](https://photoprism.app/membership) receive direct [technical support](https://photoprism.app/contact) via email.
    Before [submitting a support request](../../user-guide/index.md#getting-support), try to [determine the cause of your problem](index.md).

## Incoming Requests

Unless you have changed the default configuration, PhotoPrism is reachable via port 2342 on all network devices. If you are using a firewall, please ensure that this port can be accessed from other computers on your network, or that your instance can be accessed [through a reverse proxy](../proxies/traefik.md):

![](https://dl.photoprism.app/img/diagrams/proxy-cdn.svg){ class="w100" }

## Outgoing Connections

As explained in our [Privacy Policy](/privacy#section-7), reverse geocoding and interactive world maps depend on retrieving the necessary information [from us](/contact) and [MapTiler AG](https://www.maptiler.com/contacts/), headquartered in Switzerland. Both services are provided with a very high level of privacy and confidentiality.

[View Privacy Policy ›](https://photoprism.app/privacy#section-7){ class="pr-3" } [View Compliance FAQ ›](https://photoprism.app/kb/compliance-faq#privacy)

In order to successfully set up your installation and view location details in PhotoPrism, you must **allow requests to the following hosts** if you have a firewall installed, and make sure that your Internet connection is working:

- [ ] dl.photoprism.app
- [ ] cdn.photoprism.app
- [ ] hub.photoprism.app
- [ ] setup.photoprism.app
- [ ] places.photoprism.app
- [ ] places.photoprism.xyz

In addition, the following API endpoints should be whitelisted so that public Docker images can be pulled from [Docker Hub](https://hub.docker.com/):

- [ ] auth.docker.io
- [ ] registry-1.docker.io
- [ ] index.docker.io
- [ ] dseasb33srnrn.cloudfront.net
- [ ] production.cloudflare.docker.com

## IPTables and Docker

On Linux, Docker manipulates the `iptables` rules to provide network isolation. This does have some implications for what you need to do if you want to have your own policies in addition to the rules Docker manages.

[Learn more ›](https://docs.docker.com/network/iptables/)
