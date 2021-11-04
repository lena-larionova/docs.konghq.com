---
title: Install Kong Gateway on macOS
badge: oss
---
<!-- Banner with links to latest downloads -->
<!-- The install-link and install-listing-link classes are used for tracking, do not remove -->

{:.install-banner}
> See the MacOS
> [**Homebrew formula**]({{ site.repos.homebrew }}){:.install-listing-link}
>
> (latest {{site.base_gateway}} version: {{site.data.kong_latest_ce.version}})
## Prerequisites

You have a supported system with root or [root-equivalent](/gateway/{{page.kong_version}}/plan-and-deploy/kong-user) access.

## Download and install

1. Install {{site.base_gateway}}:

    Use the [Homebrew](https://brew.sh/) package manager to add Kong as a tap and install it:

    ```bash
    brew tap kong/kong
    brew install kong
    ```

2. Prepare your database or declarative configuration file:

    Kong can run either with or without a database.

    When using a database, you will use the `kong.conf` configuration file for setting Kong's
    configuration properties at start-up and the database as storage of all configured entities,
    such as the Routes and Services to which Kong proxies.

    When not using a database, you will use `kong.conf`'s configuration properties and a `kong.yml`
    file for specifying the entities as a declarative configuration.

    **Using a database**

    [Configure][configuration] Kong so it can connect to your database. Kong supports
    [PostgreSQL {{site.data.kong_latest.dependencies.postgres}}](http://www.postgresql.org/) and
    [Cassandra {{site.data.kong_latest.dependencies.cassandra}}](http://cassandra.apache.org/) as datastores, and
    can also run in [DB-less mode](/gateway-oss/latest/db-less-and-declarative-config/)

    If you are using Postgres, provision a database and a user before starting Kong:

    ```sql
    CREATE USER kong; CREATE DATABASE kong OWNER kong;
    ```

    Next, run the Kong migrations:

    ```bash
    kong migrations bootstrap [-c /path/to/kong.conf]
    ```
    By default, Kong is configured to communicate with a local Postgres instance.
    If you are using Cassandra, or need to modify any settings, download the [`kong.conf.default`](https://raw.githubusercontent.com/Kong/kong/master/kong.conf.default) file and [adjust][configuration] it as necessary.
    Then, as root, add `kong.conf.default` to `/etc`:

    ```bash
    sudo mkdir -p /etc/kong
    sudo cp kong.conf.default /etc/kong/kong.conf
    ```

    **Note for Kong < 0.15**: with Kong versions below 0.15 (up to 0.14), use
    the `up` sub-command instead of `bootstrap`. Also note that with Kong <
    0.15, migrations should never be run concurrently; only one Kong node
    should be performing migrations at a time. This limitation is lifted for
    Kong 0.15, 1.0, and above.

    **Without a database**

    If you are going to run Kong in [DB-less mode](/gateway-oss/latest/db-less-and-declarative-config/),
    you should start by generating a declarative config file. The following command will generate a `kong.yml`
    file in your current folder. It contains instructions about how to populate it.

    ``` bash
    kong config init
    ```

    After populating the `kong.yml` file, edit your `kong.conf` file. Set the `database` option
    to `off` and the `declarative_config` option to the path of your `kong.yml` file:

    ``` conf
    database = off
    declarative_config = /path/to/kong.yml
    ```

3. Start {{site.base_gateway}}:

    ```bash
    kong start [-c /path/to/kong.conf]
    ```

4.  Verify that {{site.base_gateway}} is running:

    ```bash
    curl -i http://localhost:8001/
    ```

Learn how to use Kong with our [Quickstart guide](/gateway/latest/get-started/quickstart/).

[configuration]: /gateway-oss/latest/configuration#database
