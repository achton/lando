MariaDB
=======

[MariaDB](https://mariadb.org/) is a very common database server which is *EXTREMELY* similar to MySQL and has a guarantee of being open source. You can easily add it to your Lando app by adding an entry to the `services` key in your app's `.lando.yml`.

Supported versions
------------------

*   [10.3](https://hub.docker.com/r/_/mariadb/)
*   [10.2](https://hub.docker.com/r/_/mariadb/)
*   [10.1](https://hub.docker.com/r/_/mariadb/)
*   [10.0](https://hub.docker.com/r/_/mariadb/)
*   [5.5](https://hub.docker.com/r/_/mariadb/)
*   [latest](https://hub.docker.com/r/_/mariadb/)
*   custom

Example
-------

{% codesnippet "./../examples/mariadb/.lando.yml" %}{% endcodesnippet %}

You will need to rebuild your app with `lando rebuild` to apply the changes to this file. You can check out the full code for this example [over here](https://github.com/lando/lando/tree/master/examples/mariadb).

Getting information
-------------------

You can get connection and credential information about your database by running `lando info` from inside your app.

```bash
# Navigate to the app
cd /path/to/app

# Get info (app needs to be running to get this)
lando info

{
  "html": {
    "type": "nginx",
    "version": "latest",
    "urls": [
      "https://localhost:32802",
      "http://localhost:32803",
      "http://mariadb.lndo.site",
      "https://mariadb.lndo.site"
    ]
  },
  "database": {
    "type": "mariadb",
    "version": "10.1",
    "creds": {
      "user": "mariadb",
      "password": "mariadb",
      "database": "mariadb"
    },
    "internal_connection": {
      "host": "database",
      "port": 3306
    },
    "external_connection": {
      "host": "localhost",
      "port": 3307
    }
  }
}
```
