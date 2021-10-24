---
title: Install Kong Gateway on Amazon Linux
version-index: 1
---

## Download

### Kong Gateway (Enterprise)

<!-- Banner with links to latest downloads -->
<!-- The install-link and install-listing-link classes are used for tracking, do not remove -->

{:.install-banner}
> Download the latest {{site.ee_product_name}} {{page.kong_version}} package for
> [**Amazon Linux**]({{site.links.download }}/gateway-2.x-amazonlinux-2/Packages/k/kong-enterprise-edition-{{page.kong_versions[page.version-index].ee-version}}.amzn2.noarch.rpm){:.install-link} 
>
> (latest {{site.ee_product_name}} {{page.kong_version}} version: {{page.kong_versions[page.version-index].ee-version}})
> <br><br>
> <span class="install-subtitle">View the list of all the {{site.ee_product_name}} 2.x packages for
> [**Amazon Linux**]({{site.links.download }}/gateway-2.x-amazonlinux-2/Packages/k/){:.install-listing-link} </span>

{% navtabs %}
{% navtab Download RPM file %}

To download the RPM file from the command line, use the following command:

```bash
curl -Lo kong-enterprise-edition-{{page.kong_versions[page.version-index].ee-version}}.amzn2.noarch.rpm "{{ site.links.download }}/gateway-2.x-amazonlinux-2/Packages/k/kong-enterprise-edition-{{page.kong_versions[page.version-index].ee-version}}.amzn2.noarch.rpm"
```

{% endnavtab %}
{% navtab Download Yum repo file %}

To download the Yum repo file from the command line, use the following command:

```bash
curl {{site.links.download}}/gateway-2.x-amazonlinux-2/config.repo | sudo tee /etc/yum.repos.d/kong-enterprise-edition.repo
```

{% endnavtab %}
{% endnavtabs %}

### Kong Gateway

<!-- Banner with links to latest downloads -->
<!-- The install-link and install-listing-link classes are used for tracking, do not remove -->

{:.install-banner}
> Download the latest {{site.ce_product_name}} {{page.kong_version}} package for
> [**Amazon Linux**]({{ site.links.download }}/gateway-2.x-amazonlinux-2/Packages/k/kong-{{page.kong_versions[page.version-index].ce-version}}.aws.amd64.rpm){:.install-link}
>
> (latest {{site.ce_product_name}} {{page.kong_version}} version: {{page.kong_versions[page.version-index].ce-version}})
> <br><br>
> <span class="install-subtitle">View the list of all {{site.ce_product_name}} 2.x packages for
> [**Amazon Linux**]({{ site.links.download }}/gateway-2.x-amazonlinux-2/Packages/k/){:.install-listing-link} </span>

{% navtabs %}
{% navtab Download RPM file %}

To download the RPM file from the command line, use the following commands:

```bash
curl -Lo kong-{{page.kong_versions[page.version-index].ce-version}}.aws.amd64.rpm "{{ site.links.download }}/gateway-2.x-amazonlinux-2/Packages/k/kong-{{page.kong_versions[page.version-index].ce-version}}.aws.amd64.rpm"
```
{% endnavtab %}
{% navtab Download Yum repo file %}

To download the Yum repo file from the command line, use the following command:

```bash
curl {{site.links.download}}/gateway-2.x-amazonlinux-2/config.repo | sudo tee /etc/yum.repos.d/kong.repo
```

{% endnavtab %}
{% endnavtabs %}

## Install

### Kong Gateway (Enterprise)

{% navtabs %}
{% navtab Using RPM file %}

To install the RPM file from the command line, use the following command:

```bash
sudo yum install kong-enterprise-edition-{{page.kong_versions[page.version-index].ee-version}}.amzn2.noarch.rpm
```

{% endnavtab %}
{% navtab Using Yum repo %}

To install the Yum repo file from the command line, use the following command:

```bash
sudo yum install -y kong-enterprise-edition
```

{% endnavtab %}
{% endnavtabs %}

### Kong Gateway

{% navtabs %}
{% navtab Using RPM file %}

To install the RPM file from the command line, use the following command:

```bash
sudo yum install kong-{{page.kong_versions[page.version-index].ce-version}}.aws.amd64.rpm
```

{% endnavtab %}
{% navtab Using Yum repo %}

To install the Yum repo file from the command line, use the following command:

```bash
sudo yum install -y kong
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
