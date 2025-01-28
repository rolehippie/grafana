# grafana

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&logoColor=white)](https://github.com/rolehippie/grafana)
[![General Workflow](https://github.com/rolehippie/grafana/actions/workflows/general.yml/badge.svg)](https://github.com/rolehippie/grafana/actions/workflows/general.yml)
[![Readme Workflow](https://github.com/rolehippie/grafana/actions/workflows/docs.yml/badge.svg)](https://github.com/rolehippie/grafana/actions/workflows/docs.yml)
[![Galaxy Workflow](https://github.com/rolehippie/grafana/actions/workflows/galaxy.yml/badge.svg)](https://github.com/rolehippie/grafana/actions/workflows/galaxy.yml)
[![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/grafana)](https://github.com/rolehippie/grafana/blob/master/LICENSE)
[![Ansible Role](https://img.shields.io/badge/role-rolehippie.grafana-blue)](https://galaxy.ansible.com/rolehippie/grafana)

Ansible role to install and configure Grafana observability platform.

## Sponsor

Building and improving this Ansible role have been sponsored by my current and previous employers like **[Cloudpunks GmbH](https://cloudpunks.de)** and **[Proact Deutschland GmbH](https://www.proact.eu)**.

## Table of content

- [Requirements](#requirements)
- [Default Variables](#default-variables)
  - [grafana_admin_disable](#grafana_admin_disable)
  - [grafana_admin_enable](#grafana_admin_enable)
  - [grafana_admins](#grafana_admins)
  - [grafana_allow_insecure_email_lookup](#grafana_allow_insecure_email_lookup)
  - [grafana_allow_signup](#grafana_allow_signup)
  - [grafana_anonymous_auth](#grafana_anonymous_auth)
  - [grafana_assign_auto](#grafana_assign_auto)
  - [grafana_assign_org](#grafana_assign_org)
  - [grafana_assign_role](#grafana_assign_role)
  - [grafana_cpu_shares](#grafana_cpu_shares)
  - [grafana_datasources](#grafana_datasources)
  - [grafana_db_host](#grafana_db_host)
  - [grafana_db_name](#grafana_db_name)
  - [grafana_db_password](#grafana_db_password)
  - [grafana_db_path](#grafana_db_path)
  - [grafana_db_type](#grafana_db_type)
  - [grafana_db_username](#grafana_db_username)
  - [grafana_default_folders](#grafana_default_folders)
  - [grafana_default_labels](#grafana_default_labels)
  - [grafana_default_publish](#grafana_default_publish)
  - [grafana_default_volumes](#grafana_default_volumes)
  - [grafana_disable_signin](#grafana_disable_signin)
  - [grafana_disable_signout](#grafana_disable_signout)
  - [grafana_domain](#grafana_domain)
  - [grafana_email](#grafana_email)
  - [grafana_extra_folders](#grafana_extra_folders)
  - [grafana_extra_labels](#grafana_extra_labels)
  - [grafana_extra_publish](#grafana_extra_publish)
  - [grafana_extra_volumes](#grafana_extra_volumes)
  - [grafana_image](#grafana_image)
  - [grafana_install_plugins](#grafana_install_plugins)
  - [grafana_installation](#grafana_installation)
  - [grafana_instance](#grafana_instance)
  - [grafana_keycloak_client](#grafana_keycloak_client)
  - [grafana_keycloak_roles](#grafana_keycloak_roles)
  - [grafana_keycloak_scopes](#grafana_keycloak_scopes)
  - [grafana_keycloak_secret](#grafana_keycloak_secret)
  - [grafana_keycloak_url](#grafana_keycloak_url)
  - [grafana_keyring](#grafana_keyring)
  - [grafana_manage_admins](#grafana_manage_admins)
  - [grafana_manage_orgs](#grafana_manage_orgs)
  - [grafana_memory_limit](#grafana_memory_limit)
  - [grafana_memory_soft_limit](#grafana_memory_soft_limit)
  - [grafana_memory_swap](#grafana_memory_swap)
  - [grafana_network](#grafana_network)
  - [grafana_number_of_cpus](#grafana_number_of_cpus)
  - [grafana_oauth2_allow_assign_admin](#grafana_oauth2_allow_assign_admin)
  - [grafana_oauth2_allow_signup](#grafana_oauth2_allow_signup)
  - [grafana_oauth2_api_url](#grafana_oauth2_api_url)
  - [grafana_oauth2_auth_url](#grafana_oauth2_auth_url)
  - [grafana_oauth2_client](#grafana_oauth2_client)
  - [grafana_oauth2_email_attribute](#grafana_oauth2_email_attribute)
  - [grafana_oauth2_enable](#grafana_oauth2_enable)
  - [grafana_oauth2_login_attribute](#grafana_oauth2_login_attribute)
  - [grafana_oauth2_name](#grafana_oauth2_name)
  - [grafana_oauth2_name_attribute](#grafana_oauth2_name_attribute)
  - [grafana_oauth2_redirect_url](#grafana_oauth2_redirect_url)
  - [grafana_oauth2_roles](#grafana_oauth2_roles)
  - [grafana_oauth2_scopes](#grafana_oauth2_scopes)
  - [grafana_oauth2_secret](#grafana_oauth2_secret)
  - [grafana_oauth2_token_url](#grafana_oauth2_token_url)
  - [grafana_org_create](#grafana_org_create)
  - [grafana_organization](#grafana_organization)
  - [grafana_organizations](#grafana_organizations)
  - [grafana_password](#grafana_password)
  - [grafana_providers](#grafana_providers)
  - [grafana_pull_image](#grafana_pull_image)
  - [grafana_repo_release](#grafana_repo_release)
  - [grafana_secret](#grafana_secret)
  - [grafana_smtp_address](#grafana_smtp_address)
  - [grafana_smtp_enabled](#grafana_smtp_enabled)
  - [grafana_smtp_host](#grafana_smtp_host)
  - [grafana_smtp_name](#grafana_smtp_name)
  - [grafana_smtp_password](#grafana_smtp_password)
  - [grafana_smtp_user](#grafana_smtp_user)
  - [grafana_username](#grafana_username)
  - [grafana_version](#grafana_version)
- [Discovered Tags](#discovered-tags)
- [Dependencies](#dependencies)
- [License](#license)
- [Author](#author)

---

## Requirements

- Minimum Ansible version: `2.10`

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

### grafana_allow_insecure_email_lookup

Allow insecure email lookup for OAuth2 authentication

#### Default value

```YAML
grafana_allow_insecure_email_lookup: false
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

### grafana_cpu_shares

CPU shares with Docker deployment

#### Default value

```YAML
grafana_cpu_shares:
```

#### Example usage

```YAML
grafana_cpu_shares: '512'
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

### grafana_default_folders

List of default folders to create

#### Default value

```YAML
grafana_default_folders:
  - /etc/grafana
  - /etc/grafana/provisioning
  - /etc/grafana/provisioning/dashboards
  - /etc/grafana/provisioning/datasources
  - /etc/grafana/provisioning/plugins
  - /etc/grafana/provisioning/alerting
  - /etc/grafana/provisioning/notifiers
  - /var/lib/grafana
  - /var/lib/grafana/plugins
  - /var/lib/grafana/dashboards
```

### grafana_default_labels

List of default labels to assign to docker

#### Default value

```YAML
grafana_default_labels: []
```

### grafana_default_publish

List of default port publishing for docker

#### Default value

```YAML
grafana_default_publish: []
```

#### Example usage

```YAML
grafana_default_publish:
  - 127.0.0.1:3000:3000
```

### grafana_default_volumes

List of default volumes to mount for docker

#### Default value

```YAML
grafana_default_volumes:
  - /var/lib/grafana:/var/lib/grafana
  - /etc/grafana:/etc/grafana
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

### grafana_email

Email for initial admin

#### Default value

```YAML
grafana_email:
```

#### Example usage

```YAML
grafana_email: admin@example.com
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

List of extra labels to assign to docker

#### Default value

```YAML
grafana_extra_labels: []
```

### grafana_extra_publish

List of extra port publishing for docker

#### Default value

```YAML
grafana_extra_publish: []
```

#### Example usage

```YAML
grafana_extra_publish:
  - 127.0.0.1:3000:3000
```

### grafana_extra_volumes

List of extra volumes to mount for docker

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

### grafana_installation

Select installation method, could be native or docker

#### Default value

```YAML
grafana_installation: native
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

### grafana_keycloak_scopes

Scope used by Keycloak authentication

#### Default value

```YAML
grafana_keycloak_scopes: openid profile email
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

### grafana_keyring

Path for the repository keyring

#### Default value

```YAML
grafana_keyring: /usr/share/keyrings/grafana-archive-keyring.gpg
```

### grafana_manage_admins

Enable management of admins

#### Default value

```YAML
grafana_manage_admins: false
```

### grafana_manage_orgs

Enable management of organizations

#### Default value

```YAML
grafana_manage_orgs: false
```

### grafana_memory_limit

Memory limit with Docker deployment

#### Default value

```YAML
grafana_memory_limit:
```

#### Example usage

```YAML
grafana_memory_limit: 1024m
```

### grafana_memory_soft_limit

Soft memory limit with Docker deployment

#### Default value

```YAML
grafana_memory_soft_limit:
```

#### Example usage

```YAML
grafana_memory_soft_limit: 512m
```

### grafana_memory_swap

Swap usage with Docker deployment

#### Default value

```YAML
grafana_memory_swap:
```

#### Example usage

```YAML
grafana_memory_swap: 2048m
```

### grafana_network

Optional docker network to attach

#### Default value

```YAML
grafana_network:
```

### grafana_number_of_cpus

Number of CPUs with Docker deployment

#### Default value

```YAML
grafana_number_of_cpus:
```

#### Example usage

```YAML
grafana_number_of_cpus: '1.0'
```

### grafana_oauth2_allow_assign_admin

Allow to assign Grafana admin via OAuth2 authentication

#### Default value

```YAML
grafana_oauth2_allow_assign_admin: true
```

### grafana_oauth2_allow_signup

Allow signup via OAuth2 authentication

#### Default value

```YAML
grafana_oauth2_allow_signup: true
```

### grafana_oauth2_api_url

API URL for OAuth2 authentication

#### Default value

```YAML
grafana_oauth2_api_url:
```

### grafana_oauth2_auth_url

Auth URL for OAuth2 authentication

#### Default value

```YAML
grafana_oauth2_auth_url:
```

### grafana_oauth2_client

Client for OAuth2 authentication

#### Default value

```YAML
grafana_oauth2_client:
```

### grafana_oauth2_email_attribute

Email attribute for OAuth2 authentication

#### Default value

```YAML
grafana_oauth2_email_attribute: email
```

### grafana_oauth2_enable

Enable generic OAuth2 authentication

#### Default value

```YAML
grafana_oauth2_enable: false
```

### grafana_oauth2_login_attribute

Login attribute for OAuth2 authentication

#### Default value

```YAML
grafana_oauth2_login_attribute: preferred_username
```

### grafana_oauth2_name

Name for OAuth2 authentication

#### Default value

```YAML
grafana_oauth2_name:
```

### grafana_oauth2_name_attribute

Name attribute for OAuth2 authentication

#### Default value

```YAML
grafana_oauth2_name_attribute: name
```

### grafana_oauth2_redirect_url

Redirect URL for OAuth2 authentication

#### Default value

```YAML
grafana_oauth2_redirect_url:
```

### grafana_oauth2_roles

Roles mapping for OAuth2 authentication

#### Default value

```YAML
grafana_oauth2_roles:
```

### grafana_oauth2_scopes

Scopes used by OAuth2 authentication

#### Default value

```YAML
grafana_oauth2_scopes: openid profile email
```

### grafana_oauth2_secret

Secret for OAuth2 authentication

#### Default value

```YAML
grafana_oauth2_secret:
```

### grafana_oauth2_token_url

Token URL for OAuth2 authentication

#### Default value

```YAML
grafana_oauth2_token_url:
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

### grafana_pull_image

Pull image as part of the tasks

#### Default value

```YAML
grafana_pull_image: true
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

### grafana_version

Version of docker release to use

#### Default value

```YAML
grafana_version: 11.4.1
```

## Discovered Tags

**_grafana_**


## Dependencies

- [rolehippie.docker](https://github.com/rolehippie/docker)
- [community.docker](https://github.com/ansible-collections/community.docker)

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)
