---
title: Install Kong Gateway on Ubuntu
---

<!-- Banner with links to latest downloads -->
<!-- The install-link and install-listing-link classes are used for tracking, do not remove -->

{:.install-banner}
> Download the latest {{site.ee_product_name}} {{page.kong_version}} package for Ubuntu:
> * **Kong Gateway**:
> [**Xenial**]({{ site.links.download }}/gateway-2.x-ubuntu-xenial/pool/all/k/kong-enterprise-edition/kong-enterprise-edition_{{page.kong_versions[page.version-index].ee-version}}_all.deb){:.install-link},
> [**Focal**]({{ site.links.download }}/gateway-2.x-ubuntu-focal/pool/all/k/kong-enterprise-edition/kong-enterprise-edition_{{page.kong_versions[page.version-index].ee-version}}_all.deb){:.install-link}, or
> [**Bionic**]({{ site.links.download }}/gateway-2.x-ubuntu-bionic/pool/all/k/kong-enterprise-edition/kong-enterprise-edition_{{page.kong_versions[page.version-index].ee-version}}_all.deb){:.install-link}
> (latest version: {{page.kong_versions[page.version-index].ee-version}})
> * **Kong Gateway (OSS)**:
> [**Xenial**]({{ site.links.download }}/gateway-2.x-ubuntu-xenial/pool/all/k/kong/kong_{{page.kong_versions[page.version-index].ce-version}}_amd64.deb){:.install-link},
> [**Focal**]({{ site.links.download }}/gateway-2.x-ubuntu-focal/pool/all/k/kong/kong_{{page.kong_versions[page.version-index].ce-version}}_amd64.deb){:.install-link}, or
> [**Bionic**]({{ site.links.download }}/gateway-2.x-ubuntu-bionic/pool/all/k/kong/kong_{{page.kong_versions[page.version-index].ce-version}}_amd64.deb){:.install-link}
>(latest version: {{page.kong_versions[page.version-index].ee-version}})
>
> <br>
> <span class="install-subtitle">View the list of all 2.x packages for
> [**Xenial**]({{ site.links.download }}/gateway-2.x-ubuntu-xenial/pool/all/k/kong-enterprise-edition/){:.install-listing-link},
> [**Focal**]({{ site.links.download }}/gateway-2.x-ubuntu-focal/pool/all/k/kong-enterprise-edition/){:.install-listing-link}, or
> [**Bionic**]({{ site.links.download }}/gateway-2.x-ubuntu-bionic/pool/all/k/kong-enterprise-edition/){:.install-listing-link}
>  </span>

## Prerequisites

You have a supported system with root or [root-equivalent](/gateway/{{page.kong_version}}/plan-and-deploy/kong-user) access.

## Download

Choose between Debian and apt repo for Xenial, Focal, and Bionic.

### Debian

{% navtabs %}
{% navtab Download Debian file for Xenial %}

To download the `.deb` file for Xenial, use the following command:

```bash
## Kong Gateway
curl -Lo kong-enterprise-edition_{{page.kong_versions[page.version-index].ee-version}}_all.deb"{{ site.links.download }}/gateway-2.x-ubuntu-xenial/Packages/k/kong-enterprise-edition-{{page.kong_versions[page.version-index].ee-version}}_all.deb"
```

```bash
## Kong Gateway (OSS)
curl -Lo kong_{{page.kong_versions[page.version-index].ce-version}}_amd64.deb "{{ site.links.download }}/gateway-2.x-ubuntu-xenial/Packages/k/kong_{{page.kong_versions[page.version-index].ce-version}}_amd64.deb"
```

{% endnavtab %}
{% navtab Download Debian file for Focal %}

To download the `.deb` file for Focal, use the following command:

```bash
## Kong Gateway
curl -Lo kong-enterprise-edition_{{page.kong_versions[page.version-index].ee-version}}_all.deb"{{ site.links.download }}/gateway-2.x-ubuntu-focal/Packages/k/kong-enterprise-edition-{{page.kong_versions[page.version-index].ee-version}}_all.deb"
```

```bash
## Kong Gateway (OSS)
curl -Lo kong_{{page.kong_versions[page.version-index].ce-version}}_amd64.deb "{{ site.links.download }}/gateway-2.x-ubuntu-focal/Packages/k/kong_{{page.kong_versions[page.version-index].ce-version}}_amd64.deb"
```

{% endnavtab %}
{% navtab Download Debian file for Bionic %}

To download the `.deb` file for Bionic, use the following command:

```bash
## Kong Gateway
curl -Lo kong-enterprise-edition_{{page.kong_versions[page.version-index].ee-version}}_all.deb"{{ site.links.download }}/gateway-2.x-ubuntu-bionic/Packages/k/kong-enterprise-edition-{{page.kong_versions[page.version-index].ee-version}}_all.deb"
```

```bash
## Kong Gateway (OSS)
curl -Lo kong_{{page.kong_versions[page.version-index].ce-version}}_amd64.deb "{{ site.links.download }}/gateway-2.x-ubuntu-bionic/Packages/k/kong_{{page.kong_versions[page.version-index].ce-version}}_amd64.deb"
```

{% endnavtab %}
{% endnavtabs %}

### Apt repo

{% navtabs %}
{% navtab Download the apt repo for Xenial %}

To download the apt repo for Xenial, use the following command:

```bash
echo "deb [trusted=yes] download.konghq.com/gateway-2.x-ubuntu-xenial default all" | tee /etc/apt/sources.list.d/kong.list
```

{% endnavtab %}
{% navtab Download the apt repo for Focal %}

To download the apt repo for Focal, use the following command:

```bash
echo "deb [trusted=yes] download.konghq.com/gateway-2.x-ubuntu-focal default all" | tee /etc/apt/sources.list.d/kong.list
```

{% endnavtab %}
{% navtab Download the apt repo for Bionic %}

To download the apt repo for Bionic, use the following command:

```bash
echo "deb [trusted=yes] download.konghq.com/gateway-2.x-ubuntu-bionic default all" | tee /etc/apt/sources.list.d/kong.list
```

{% endnavtab %}
{% endnavtabs %}

## Install

Choose between installing using Debian file or apt repo.

{% navtabs %}
{% navtab Install using Debian file %}

To install the `.deb` file for Ubuntu, use the following command:

```bash
## Kong Gateway
sudo apt-get install -fy ./kong-enterprise-edition_{{page.kong_versions[page.version-index].ee-version}}_all.deb
```

```bash
## Kong Gateway (OSS)
sudo apt-get install -fy ./kong_{{page.kong_versions[page.version-index].ce-version}}_amd64.deb
```

{% endnavtab %}
{% navtab Install using the apt repo %}

To install using the apt repo for Ubuntu, use the following command:

```bash
## Kong Gateway
apt-get install -y kong-enterprise-edition
```

```bash
## Kong Gateway (OSS)
apt-get install -y kong
```
{% endnavtab %}
{% endnavtabs %}

<!-- Setup content shared between all Linux installation topics: Amazon Linux, CentOS, Ubuntu, and RHEL.
Includes the following sections: Setup configs, Using a database, Using a yaml declarative config file,
Using a yaml declarative config file, Verify install, Enable and configure Kong Manager, Enable Dev Portal,
Support, and Next Steps.

Located in the app/_includes/md/gateway folder.

See https://docs.konghq.com/contributing/includes/ for more information about using includes in this project.
-->

{% include_cached /md/gateway/setup.md kong_version=page.kong_version %}
