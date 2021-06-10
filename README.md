# grafana

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&logoColor=white)](https://github.com/rolehippie/grafana) [![Testing Build](https://github.com/rolehippie/grafana/workflows/testing/badge.svg)](https://github.com/rolehippie/grafana/actions?query=workflow%3Atesting) [![Readme Build](https://github.com/rolehippie/grafana/workflows/readme/badge.svg)](https://github.com/rolehippie/grafana/actions?query=workflow%3Areadme) [![Galaxy Build](https://github.com/rolehippie/grafana/workflows/galaxy/badge.svg)](https://github.com/rolehippie/grafana/actions?query=workflow%3Agalaxy) [![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/grafana)](https://github.com/rolehippie/grafana/blob/master/LICENSE) 

Ansible role to install and configure Grafana observability platform. 

## Sponsor 

[![Proact Deutschland GmbH](https://proact.eu/wp-content/uploads/2020/03/proact-logo.png)](https://proact.eu) 

Building and improving this Ansible role have been sponsored by my employer **Proact Deutschland GmbH**.

## Table of content

* [Default Variables](#default-variables)
  * [grafana_admin_disable](#grafana_admin_disable)
  * [grafana_admin_enable](#grafana_admin_enable)
  * [grafana_admins](#grafana_admins)
  * [grafana_allow_signup](#grafana_allow_signup)
  * [grafana_anonymous_auth](#grafana_anonymous_auth)
  * [grafana_assign_auto](#grafana_assign_auto)
  * [grafana_assign_org](#grafana_assign_org)
  * [grafana_assign_role](#grafana_assign_role)
  * [grafana_datasources](#grafana_datasources)
  * [grafana_db_host](#grafana_db_host)
  * [grafana_db_name](#grafana_db_name)
  * [grafana_db_password](#grafana_db_password)
  * [grafana_db_path](#grafana_db_path)
  * [grafana_db_type](#grafana_db_type)
  * [grafana_db_username](#grafana_db_username)
  * [grafana_disable_signin](#grafana_disable_signin)
  * [grafana_disable_signout](#grafana_disable_signout)
  * [grafana_domain](#grafana_domain)
  * [grafana_install_plugins](#grafana_install_plugins)
  * [grafana_instance](#grafana_instance)
  * [grafana_keycloak_client](#grafana_keycloak_client)
  * [grafana_keycloak_roles](#grafana_keycloak_roles)
  * [grafana_keycloak_secret](#grafana_keycloak_secret)
  * [grafana_keycloak_url](#grafana_keycloak_url)
  * [grafana_org_create](#grafana_org_create)
  * [grafana_organization](#grafana_organization)
  * [grafana_organizations](#grafana_organizations)
  * [grafana_password](#grafana_password)
  * [grafana_providers](#grafana_providers)
  * [grafana_repo_release](#grafana_repo_release)
  * [grafana_secret](#grafana_secret)
  * [grafana_smtp_address](#grafana_smtp_address)
  * [grafana_smtp_enabled](#grafana_smtp_enabled)
  * [grafana_smtp_host](#grafana_smtp_host)
  * [grafana_smtp_name](#grafana_smtp_name)
  * [grafana_smtp_password](#grafana_smtp_password)
  * [grafana_smtp_user](#grafana_smtp_user)
  * [grafana_username](#grafana_username)
* [Dependencies](#dependencies)
* [License](#license)
* [Author](#author)

---

## Default Variables

### grafana_admin_disable

Roles mapping for Keycloak authentication

#### Default value

```YAML
grafana_admin_disable:
  isGrafanaAdmin: false
```

### grafana_admin_enable

Payload used to promote admins

#### Default value

```YAML
grafana_admin_enable:
  isGrafanaAdmin: true
```

### grafana_admins

List of admin users

#### Default value

```YAML
grafana_admins: []
```

### grafana_allow_signup

Allow signup of new users

#### Default value

```YAML
grafana_allow_signup: false
```

### grafana_anonymous_auth

Allow anonymous users access

#### Default value

```YAML
grafana_anonymous_auth: false
```

### grafana_assign_auto

Automatically assign an organization to users

#### Default value

```YAML
grafana_assign_auto: true
```

### grafana_assign_org

OD of the organization to automatically assign

#### Default value

```YAML
grafana_assign_org: 1
```

### grafana_assign_role

Standard role which gets automatically assigned

#### Default value

```YAML
grafana_assign_role: Viewer
```

### grafana_datasources

List of datasources to integrate

#### Default value

```YAML
grafana_datasources: []
```

#### Example usage

```YAML
grafana_datasources:
  - name: prometheus
    type: prometheus
    access: proxy
    url: http://localhost:9090
    orgId: 1
    isDefault: True
    editable: False
```

### grafana_db_host

Host for the database connection

#### Default value

```YAML
grafana_db_host:
```

### grafana_db_name

Database used for the database connection

#### Default value

```YAML
grafana_db_name:
```

### grafana_db_password

Password for the database connection

#### Default value

```YAML
grafana_db_password:
```

### grafana_db_path

Path to SQLite3 database

#### Default value

```YAML
grafana_db_path:
```

### grafana_db_type

Type of database to use

#### Default value

```YAML
grafana_db_type: mysql
```

### grafana_db_username

Username for the database connection

#### Default value

```YAML
grafana_db_username:
```

### grafana_disable_signin

Disable the regular signin of users

#### Default value

```YAML
grafana_disable_signin: false
```

### grafana_disable_signout

Disable the regular signout of users

#### Default value

```YAML
grafana_disable_signout: false
```

### grafana_domain

Domain for external access

#### Default value

```YAML
grafana_domain:
```

#### Example usage

```YAML
grafana_domain: grafana.example.com
```

### grafana_install_plugins

List of plugins to install

#### Default value

```YAML
grafana_install_plugins:
  - grafana-piechart-panel
```

### grafana_instance

Name of the Grafana instance

#### Default value

```YAML
grafana_instance:
```

#### Example usage

```YAML
grafana_instance: Example
```

### grafana_keycloak_client

Client id for Keycloak authentication

#### Default value

```YAML
grafana_keycloak_client:
```

### grafana_keycloak_roles

#### Default value

```YAML
grafana_keycloak_roles:
```

### grafana_keycloak_secret

Client secret for Keycloak authentication

#### Default value

```YAML
grafana_keycloak_secret:
```

### grafana_keycloak_url

Keycloak URL for OAuth2 authentication

#### Default value

```YAML
grafana_keycloak_url:
```

### grafana_org_create

Allow users to create organizations

#### Default value

```YAML
grafana_org_create: false
```

### grafana_organization

Name of the primary organization

#### Default value

```YAML
grafana_organization:
```

#### Example usage

```YAML
grafana_organization: Example
```

### grafana_organizations

List of organizations

#### Default value

```YAML
grafana_organizations: []
```

#### Example usage

```YAML
grafana_organizations:
  - Org1
  - Org2
  - Org3
```

### grafana_password

Password for initial admin

#### Default value

```YAML
grafana_password:
```

#### Example usage

```YAML
grafana_password: p455w0rd
```

### grafana_providers

List of providers to integrate

#### Default value

```YAML
grafana_providers:
  - name: default
    orgId: 1
    folder: ''
    folderUid: ''
    type: file
    disableDeletion: false
    updateIntervalSeconds: 10
    options:
      path: /var/lib/grafana/dashboards
```

### grafana_repo_release

Enforce another release for the repo

#### Default value

```YAML
grafana_repo_release: stable
```

### grafana_secret

Secret for initial admin

#### Default value

```YAML
grafana_secret:
```

#### Example usage

```YAML
grafana_secret: s3cr37
```

### grafana_smtp_address

Address for sending mails via SMTP

#### Default value

```YAML
grafana_smtp_address:
```

### grafana_smtp_enabled

Enable sending mails via SMTP

#### Default value

```YAML
grafana_smtp_enabled: true
```

### grafana_smtp_host

Host for sending mails via SMTP

#### Default value

```YAML
grafana_smtp_host:
```

### grafana_smtp_name

Name for sending mails via SMTP

#### Default value

```YAML
grafana_smtp_name: Grafana
```

### grafana_smtp_password

Password for sending mails via SMTP

#### Default value

```YAML
grafana_smtp_password:
```

### grafana_smtp_user

Username for sending mails via SMTP

#### Default value

```YAML
grafana_smtp_user:
```

### grafana_username

Username for initial admin

#### Default value

```YAML
grafana_username:
```

#### Example usage

```YAML
grafana_username: admin
```

## Dependencies

* None

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)
