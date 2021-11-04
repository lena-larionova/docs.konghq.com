---
title: Install Kong Gateway on Debian
badge: oss
---
{:.install-banner}
> Download the latest {{site.ce_product_name}} {{page.kong_version}} package for Debian:
> * [8 Jessie]({{ site.links.download }}/gateway-2.x-debian-jessie/pool/all/k/kong/kong_{{page.kong_versions[page.version-index].ce-version}}_amd64.deb){:.install-link}
> * [9 Stretch]({{ site.links.download }}/gateway-2.x-debian-stretch/pool/all/k/kong/kong_{{page.kong_versions[page.version-index].ce-version}}_amd64.deb){:.install-link}
> * [10 Buster]({{ site.links.download }}/gateway-2.x-debian-buster/pool/all/k/kong/kong_{{page.kong_versions[page.version-index].ce-version}}_amd64.deb){:.install-link}
> * [11 Bullseye]({{ site.links.download }}/gateway-2.x-debian-bullseye/pool/all/k/kong/kong_{{page.kong_versions[page.version-index].ce-version}}_amd64.deb){:.install-link}
> (latest version: {{page.kong_versions[page.version-index].ce-version}})
>
> <br>
> <span class="install-subtitle">View the list of all 2.x packages for
> [8 Jessie]({{ site.links.download }}/gateway-2.x-debian-jessie/pool/all/k/kong/kong_{{page.kong_versions[page.version-index].ce-version}}_amd64.deb){:.install-listing-link}, 
> [9 Stretch]({{ site.links.download }}/gateway-2.x-debian-stretch/pool/all/k/kong/kong_{{page.kong_versions[page.version-index].ce-version}}_amd64.deb){:.install-listing-link}, 
> [10 Buster]({{ site.links.download }}/gateway-2.x-debian-buster/pool/all/k/kong/kong_{{page.kong_versions[page.version-index].ce-version}}_amd64.deb){:.install-listing-link}, or 
> [11 Bullseye]({{ site.links.download }}/gateway-2.x-debian-bullseye/pool/all/k/kong/kong_{{page.kong_versions[page.version-index].ce-version}}_amd64.deb){:.install-listing-link}
>  </span>
## Prerequisites

You have a supported system with root or [root-equivalent](/gateway/{{page.kong_version}}/plan-and-deploy/kong-user) access.

## Install

You can install Gateway by downloading an installation package or using our APT repository.

{% navtabs %}
{% navtab Install with packages %}

    {% if include.distribution == "ubuntu" %}

- [Xenial]({{ site.links.download }}/gateway-2.x-ubuntu-xenial/pool/all/k/kong/kong_{{site.data.kong_latest.version}}_amd64.deb)
- [Bionic]({{ site.links.download }}/gateway-2.x-ubuntu-bionic/pool/all/k/kong/kong_{{site.data.kong_latest.version}}_amd64.deb)
- [Focal]({{ site.links.download }}/gateway-2.x-ubuntu-focal/pool/all/k/kong/kong_{{site.data.kong_latest.version}}_amd64.deb)

    {% endif %}

    {% if include.distribution == "debian" %}

- [8 Jessie]({{ site.links.download }}/gateway-2.x-debian-jessie/pool/all/k/kong/kong_{{site.data.kong_latest.version}}_amd64.deb)
- [9 Stretch]({{ site.links.download }}/gateway-2.x-debian-stretch/pool/all/k/kong/kong_{{site.data.kong_latest.version}}_amd64.deb)
- [10 Buster]({{ site.links.download }}/gateway-2.x-debian-buster/pool/all/k/kong/kong_{{site.data.kong_latest.version}}_amd64.deb)
- [11 Bullseye]({{ site.links.download }}/gateway-2.x-debian-bullseye/pool/all/k/kong/kong_{{site.data.kong_latest.version}}_amd64.deb)

    {% endif %}

Install Debian from the command line.

```bash
curl -Lo kong.{{site.data.kong_latest.version}}.amd64.deb "{{ site.links.download }}/gateway-2.x-{{ include.distribution }}-$(lsb_release -cs)/pool/all/k/kong/kong_{{site.data.kong_latest.version}}_amd64.deb"
```

```bash
sudo dpkg -i kong.{{site.data.kong_latest.version}}.amd64.deb
```

{% endnavtab %}
{% navtab Install with apt repository %}

Install the `apt` repository from the command line.

```bash
echo "deb [trusted=yes] {{ site.links.download }}/gateway-2.x-{{ include.distribution }}-$(lsb_release -sc)/ default all" | sudo tee /etc/apt/sources.list.d/kong.list 
sudo apt-get update
sudo apt install -y kong
```

{% endnavtab %}
{% endnavtabs %}

{% include /md/installation.md %}
