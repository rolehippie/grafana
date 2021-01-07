# grafana

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&logoColor=white)](https://github.com/rolehippie/grafana) [![Build Status](https://img.shields.io/drone/build/rolehippie/grafana/master?logo=drone)](https://cloud.drone.io/rolehippie/grafana) [![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/grafana)](https://github.com/rolehippie/grafana/blob/master/LICENSE) 

Ansible role to install and configure Grafana. 

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
  * [grafana_default_folders](#grafana_default_folders)
  * [grafana_default_labels](#grafana_default_labels)
  * [grafana_default_publish](#grafana_default_publish)
  * [grafana_default_volumes](#grafana_default_volumes)
  * [grafana_disable_signin](#grafana_disable_signin)
  * [grafana_disable_signout](#grafana_disable_signout)
  * [grafana_domain](#grafana_domain)
  * [grafana_enforce_domain](#grafana_enforce_domain)
  * [grafana_extra_folders](#grafana_extra_folders)
  * [grafana_extra_labels](#grafana_extra_labels)
  * [grafana_extra_publish](#grafana_extra_publish)
  * [grafana_extra_volumes](#grafana_extra_volumes)
  * [grafana_github_client](#grafana_github_client)
  * [grafana_github_enabled](#grafana_github_enabled)
  * [grafana_github_secret](#grafana_github_secret)
  * [grafana_github_signup](#grafana_github_signup)
  * [grafana_github_teams](#grafana_github_teams)
  * [grafana_image](#grafana_image)
  * [grafana_install_plugins](#grafana_install_plugins)
  * [grafana_instance](#grafana_instance)
  * [grafana_ldap_attribute_email](#grafana_ldap_attribute_email)
  * [grafana_ldap_attribute_member_of](#grafana_ldap_attribute_member_of)
  * [grafana_ldap_attribute_name](#grafana_ldap_attribute_name)
  * [grafana_ldap_attribute_surname](#grafana_ldap_attribute_surname)
  * [grafana_ldap_attribute_username](#grafana_ldap_attribute_username)
  * [grafana_ldap_bind_dn](#grafana_ldap_bind_dn)
  * [grafana_ldap_bind_password](#grafana_ldap_bind_password)
  * [grafana_ldap_enabled](#grafana_ldap_enabled)
  * [grafana_ldap_group_mappings](#grafana_ldap_group_mappings)
  * [grafana_ldap_group_search](#grafana_ldap_group_search)
  * [grafana_ldap_group_search_base_dns](#grafana_ldap_group_search_base_dns)
  * [grafana_ldap_group_search_filter](#grafana_ldap_group_search_filter)
  * [grafana_ldap_group_search_filter_user_attribute](#grafana_ldap_group_search_filter_user_attribute)
  * [grafana_ldap_host](#grafana_ldap_host)
  * [grafana_ldap_port](#grafana_ldap_port)
  * [grafana_ldap_search_base_dns](#grafana_ldap_search_base_dns)
  * [grafana_ldap_search_filter](#grafana_ldap_search_filter)
  * [grafana_ldap_signup](#grafana_ldap_signup)
  * [grafana_ldap_ssl_skip_verify](#grafana_ldap_ssl_skip_verify)
  * [grafana_ldap_start_tls](#grafana_ldap_start_tls)
  * [grafana_ldap_use_ssl](#grafana_ldap_use_ssl)
  * [grafana_network](#grafana_network)
  * [grafana_org_create](#grafana_org_create)
  * [grafana_organization](#grafana_organization)
  * [grafana_organizations](#grafana_organizations)
  * [grafana_password](#grafana_password)
  * [grafana_providers](#grafana_providers)
  * [grafana_secret](#grafana_secret)
  * [grafana_smtp_address](#grafana_smtp_address)
  * [grafana_smtp_enabled](#grafana_smtp_enabled)
  * [grafana_smtp_host](#grafana_smtp_host)
  * [grafana_smtp_name](#grafana_smtp_name)
  * [grafana_smtp_password](#grafana_smtp_password)
  * [grafana_smtp_user](#grafana_smtp_user)
  * [grafana_username](#grafana_username)
  * [grafana_version](#grafana_version)
* [Dependencies](#dependencies)
* [License](#license)
* [Author](#author)

---

## Default Variables

### grafana_admin_disable

Attributes for revoke admin access post request

#### Default value

```YAML
grafana_admin_disable:
  isGrafanaAdmin: false
```

### grafana_admin_enable

Attributes for promote admin access post request

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

#### Example usage

```YAML
grafana_organizations:
  - tboerger
  - hans
  - octocat
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
grafana_db_path: /var/lib/grafana/database.sqlite3
```

### grafana_db_type

Type of database to use

#### Default value

```YAML
grafana_db_type: sqlite3
```

### grafana_db_username

Username for the database connection

#### Default value

```YAML
grafana_db_username:
```

### grafana_default_folders

List of default folders to create

#### Default value

```YAML
grafana_default_folders:
  - /etc/grafana
  - /etc/grafana/provisioning/dashboards
  - /etc/grafana/provisioning/datasources
  - /etc/grafana/provisioning/notifiers
  - /etc/grafana/provisioning/plugins
  - /var/lib/grafana
  - /var/lib/grafana/plugins
  - /var/lib/grafana/dashboards
```

### grafana_default_labels

List of default labels to assign to docker command

#### Default value

```YAML
grafana_default_labels: []
```

### grafana_default_publish

List of default port publishing

#### Default value

```YAML
grafana_default_publish:
  - 3000:3000
```

#### Example usage

```YAML
grafana_default_publish:
  - 127.0.0.1:9093:9093
```

### grafana_default_volumes

List of default volumes to mount

#### Default value

```YAML
grafana_default_volumes:
  - /etc/grafana:/etc/grafana
  - /var/lib/grafana:/var/lib/grafana
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

### grafana_enforce_domain

Enforce the configured domain

#### Default value

```YAML
grafana_enforce_domain: false
```

### grafana_extra_folders

List of extra folders to create

#### Default value

```YAML
grafana_extra_folders: []
```

#### Example usage

```YAML
grafana_extra_folders:
  - /path/to/host/folder1
  - /path/to/host/folder2
  - /path/to/host/folder3
```

### grafana_extra_labels

List of extra labels to assign to docker command

#### Default value

```YAML
grafana_extra_labels: []
```

### grafana_extra_publish

List of extra port publishing

#### Default value

```YAML
grafana_extra_publish: []
```

#### Example usage

```YAML
grafana_extra_publish:
  - 8080:8080
  - 127.0.0.1:3030:3030
```

### grafana_extra_volumes

List of extra volumes to mount

#### Default value

```YAML
grafana_extra_volumes: []
```

#### Example usage

```YAML
grafana_extra_volumes:
  - /path/to/host/folder1:/path/within/container1
  - /path/to/host/folder2:/path/within/container2
  - /path/to/host/folder3:/path/within/container3
```

### grafana_github_client

Secret id for GitHub oauth2

#### Default value

```YAML
grafana_github_client:
```

### grafana_github_enabled

Enable GitHub authentication and configuration

#### Default value

```YAML
grafana_github_enabled: false
```

### grafana_github_secret

#### Default value

```YAML
grafana_github_secret:
```

### grafana_github_signup

Enable signup via GitHub

#### Default value

```YAML
grafana_github_signup: true
```

### grafana_github_teams

List of GitHub teams allowed to access grafana

#### Default value

```YAML
grafana_github_teams: []
```

### grafana_image

Docker image to use for deployment

#### Default value

```YAML
grafana_image: grafana/grafana:{{ grafana_version }}
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

### grafana_ldap_attribute_email

Email attribute within LDAP

#### Default value

```YAML
grafana_ldap_attribute_email: mail
```

### grafana_ldap_attribute_member_of

Member of attribute within LDAP

#### Default value

```YAML
grafana_ldap_attribute_member_of: memberOf
```

### grafana_ldap_attribute_name

Name attribute within LDAP

#### Default value

```YAML
grafana_ldap_attribute_name: givenName
```

### grafana_ldap_attribute_surname

Surname attribute within LDAP

#### Default value

```YAML
grafana_ldap_attribute_surname: sn
```

### grafana_ldap_attribute_username

Username attribute within LDAP

#### Default value

```YAML
grafana_ldap_attribute_username: cn
```

### grafana_ldap_bind_dn

Bind DN for LDAP server

#### Default value

```YAML
grafana_ldap_bind_dn:
```

### grafana_ldap_bind_password

Password for LDAP server

#### Default value

```YAML
grafana_ldap_bind_password:
```

### grafana_ldap_enabled

Enable LDAP authentication and configuration

#### Default value

```YAML
grafana_ldap_enabled: false
```

### grafana_ldap_group_mappings

Group mappings from LDAP to Grafana

#### Default value

```YAML
grafana_ldap_group_mappings: []
```

#### Example usage

```YAML
grafana_ldap_group_mappings:
  - dn: cn=admins,dc=grafana,dc=org
    role: Admin
    admin: True
  - dn: cn=users,dc=grafana,dc=org
    role: Editor
  - dn: cn=manager,dc=grafana,dc=org
    role: Viewer
    org: 1
  - dn: '*'
    role: Viewer
```

### grafana_ldap_group_search

Enable group searching for LDAP server

#### Default value

```YAML
grafana_ldap_group_search: true
```

### grafana_ldap_group_search_base_dns

Search base DN for LDAP groups

#### Default value

```YAML
grafana_ldap_group_search_base_dns: []
```

### grafana_ldap_group_search_filter

Search filter for groups from LDAP

#### Default value

```YAML
grafana_ldap_group_search_filter: (&(objectClass=posixGroup)(memberUid=%s))
```

### grafana_ldap_group_search_filter_user_attribute

User attribute for group search within LDAP

#### Default value

```YAML
grafana_ldap_group_search_filter_user_attribute: cn
```

### grafana_ldap_host

Host of the LDAP server

#### Default value

```YAML
grafana_ldap_host:
```

### grafana_ldap_port

Port of the LDAP server

#### Default value

```YAML
grafana_ldap_port:
```

### grafana_ldap_search_base_dns

Search base DN for LDAP users

#### Default value

```YAML
grafana_ldap_search_base_dns: []
```

### grafana_ldap_search_filter

Search filter for users from LDAP

#### Default value

```YAML
grafana_ldap_search_filter: (&(objectClass=posixAccount)(uid=%s))
```

### grafana_ldap_signup

Enable signup via LDAP

#### Default value

```YAML
grafana_ldap_signup: true
```

### grafana_ldap_ssl_skip_verify

Skip SSL verification for LDAP connection

#### Default value

```YAML
grafana_ldap_ssl_skip_verify: false
```

### grafana_ldap_start_tls

Use STARTTLS for LDAP connection

#### Default value

```YAML
grafana_ldap_start_tls: false
```

### grafana_ldap_use_ssl

Use SSL for LDAP connection

#### Default value

```YAML
grafana_ldap_use_ssl: false
```

### grafana_network

Optionally assign this Docker network to container

#### Default value

```YAML
grafana_network:
```

### grafana_org_create

Allow users to create organizations

#### Default value

```YAML
grafana_org_create: true
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

Enable sending emails via SMTP

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

### grafana_version

Version of Grafana to use

#### Default value

```YAML
grafana_version: 7.3.6
```

## Dependencies

* [rolehippie.docker](https://github.com/rolehippie/docker)

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)
