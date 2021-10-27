---
title: Install Kong Gateway on Ubuntu
---

## Prerequisites

You have a supported system with root or [root-equivalent](/gateway/{{page.kong_version}}/plan-and-deploy/kong-user) access.

## Download

### Kong Gateway (Enterprise)

<!-- Banner with links to latest downloads -->
<!-- The install-link and install-listing-link classes are used for tracking, do not remove -->

{:.install-banner}
> Download the latest {{site.ee_product_name}} {{page.kong_version}} package for Ubuntu
> [**Xenial**]({{ site.links.download }}/gateway-2.x-ubuntu-xenial/pool/all/k/kong-enterprise-edition/kong-enterprise-edition_{{page.kong_versions[page.version-index].ee-version}}_all.deb){:.install-link},
> [**Focal**]({{ site.links.download }}/gateway-2.x-ubuntu-focal/pool/all/k/kong-enterprise-edition/kong-enterprise-edition_{{page.kong_versions[page.version-index].ee-version}}_all.deb){:.install-link}, or
> [**Bionic**]({{ site.links.download }}/gateway-2.x-ubuntu-bionic/pool/all/k/kong-enterprise-edition/kong-enterprise-edition_{{page.kong_versions[page.version-index].ee-version}}_all.deb){:.install-link}
>
>(latest {{site.ee_product_name}} {{page.kong_version}} version: {{page.kong_versions[page.version-index].ee-version}})
> <br><br>
> <span class="install-subtitle">View the list of all {{site.ee_product_name}} 2.x packages for
> [**Xenial**]({{ site.links.download }}/gateway-2.x-ubuntu-xenial/pool/all/k/kong-enterprise-edition/){:.install-listing-link},
> [**Focal**]({{ site.links.download }}/gateway-2.x-ubuntu-focal/pool/all/k/kong-enterprise-edition/){:.install-listing-link}, or
> [**Bionic**]({{ site.links.download }}/gateway-2.x-ubuntu-bionic/pool/all/k/kong-enterprise-edition/){:.install-listing-link}
>  </span>

{% navtabs %}
{% navtab Download Debian file for Xenial %}

To download the .deb file for Xenial from the command line, use the following command:

```bash
curl -Lo kong-enterprise-edition_{{page.kong_versions[page.version-index].ee-version}}_all.deb"{{ site.links.download }}/gateway-2.x-ubuntu-xenial/Packages/k/kong-enterprise-edition-{{page.kong_versions[page.version-index].ee-version}}_all.deb"
```

{% endnavtab %}
{% navtab Download Debian file for Focal %}

To download the .deb file for Focal from the command line, use the following command:

```bash
curl -Lo kong-enterprise-edition_{{page.kong_versions[page.version-index].ee-version}}_all.deb"{{ site.links.download }}/gateway-2.x-ubuntu-focal/Packages/k/kong-enterprise-edition-{{page.kong_versions[page.version-index].ee-version}}_all.deb"
```

{% endnavtab %}
{% navtab Download Debian file for Bionic %}

To download the .deb file for Bionic from the command line, use the following command:

```bash
curl -Lo kong-enterprise-edition_{{page.kong_versions[page.version-index].ee-version}}_all.deb"{{ site.links.download }}/gateway-2.x-ubuntu-bionic/Packages/k/kong-enterprise-edition-{{page.kong_versions[page.version-index].ee-version}}_all.deb"
```

{% endnavtab %}
{% endnavtabs %}

### Kong Gateway

<!-- Banner with links to latest downloads -->
<!-- The install-link and install-listing-link classes are used for tracking, do not remove -->

{:.install-banner}
> Download the latest {{site.ce_product_name}} {{page.kong_version}} package for Ubuntu
> [**Xenial**]({{ site.links.download }}/gateway-2.x-ubuntu-xenial/pool/all/k/kong/kong_{{page.kong_versions[page.version-index].ce-version}}_amd64.deb){:.install-link},
> [**Focal**]({{ site.links.download }}/gateway-2.x-ubuntu-focal/pool/all/k/kong/kong_{{page.kong_versions[page.version-index].ce-version}}_amd64.deb){:.install-link}, or
> [**Bionic**]({{ site.links.download }}/gateway-2.x-ubuntu-bionic/pool/all/k/kong/kong_{{page.kong_versions[page.version-index].ce-version}}_amd64.deb){:.install-link}
>
>(latest {{site.ce_product_name}} {{page.kong_version}} version: {{page.kong_versions[page.version-index].ce-version}})
> <br><br>
> <span class="install-subtitle">View the list of all {{site.ee_product_name}} 2.x packages for
> [**Xenial**]({{ site.links.download }}/gateway-2.x-ubuntu-xenial/pool/all/k/kong-enterprise-edition/){:.install-listing-link},
> [**Focal**]({{ site.links.download }}/gateway-2.x-ubuntu-focal/pool/all/k/kong-enterprise-edition/){:.install-listing-link}, or
> [**Bionic**]({{ site.links.download }}/gateway-2.x-ubuntu-bionic/pool/all/k/kong-enterprise-edition/){:.install-listing-link}
>  </span>

{% navtabs %}
{% navtab Download Debian file for Xenial %}

To download the .deb file for Xenial from the command line, use the following commands:

```bash
curl -Lo kong_{{page.kong_versions[page.version-index].ce-version}}_amd64.deb "{{ site.links.download }}/gateway-2.x-ubuntu-xenial/Packages/k/kong_{{page.kong_versions[page.version-index].ce-version}}_amd64.deb"
```

{% endnavtab %}
{% navtab Download Debian file for Focal %}

To download the .deb file for Focal from the command line, use the following commands:

```bash
curl -Lo kong_{{page.kong_versions[page.version-index].ce-version}}_amd64.deb "{{ site.links.download }}/gateway-2.x-ubuntu-focal/Packages/k/kong_{{page.kong_versions[page.version-index].ce-version}}_amd64.deb"
```

{% endnavtab %}
{% navtab Download Debian file for Bionic %}

To download the .deb file for Focal from the command line, use the following commands:

```bash
curl -Lo kong_{{page.kong_versions[page.version-index].ce-version}}_amd64.deb "{{ site.links.download }}/gateway-2.x-ubuntu-bionic/Packages/k/kong_{{page.kong_versions[page.version-index].ce-version}}_amd64.deb"
```

{% endnavtab %}
{% endnavtabs %}

## Install

### Kong Gateway (Enterprise)

To install the .deb file for Ubuntu from the command line, use the following command:

```bash
sudo apt-get install -fy ./kong-enterprise-edition_{{page.kong_versions[page.version-index].ee-version}}_all.deb
```

### Kong Gateway

To install the Debian file for Ubuntu from the command line, use the following command:

```bash
sudo apt-get install -fy ./kong_{{page.kong_versions[page.version-index].ce-version}}_amd64.deb
```

<!-- Setup content shared between all Linux installation topics: Amazon Linux, CentOS, Ubuntu, and RHEL.
Includes the following sections: Setup configs, Using a database, Using a yaml declarative config file,
Using a yaml declarative config file, Verify install, Enable and configure Kong Manager, Enable Dev Portal,
Support, and Next Steps.

Located in the app/_includes/md/gateway folder.

See https://docs.konghq.com/contributing/includes/ for more information about using includes in this project.
-->

{% include_cached /md/gateway/setup.md kong_version=page.kong_version %}
