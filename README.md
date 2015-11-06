# Ansible Role Mumble MyMumb panel
[![Build Status](https://travis-ci.org/reminec/ansible-role-mumble-mymumb-panel.svg?branch=master)](https://travis-ci.org/reminec/ansible-role-mumble-mymumb-panel)

Install latest release of [MyMumb panel](https://github.com/dieonar/MyMumb-Panel).

Can install Apache2 and php5 if `mymumb_install_apache2` is set to `true` (default false)

# Requirements

None

# Role Variables

## Simple configuration
```yaml
mymumb_path: /var/www
mymumb_chmod_user: www-data
mymumb_chmod_group: www-data

mymumb_default_host: 127.0.0.1 # Ip of your Mumble Server. If it's the same Server no need to change it.
mymumb_default_port: 6502 # The Port of your Mumble Server
mymumb_ice_password: 'icesecret' # The Password used in the mumble-server.ini
```

## Install (and configure) Apache2 and PHP5
```yaml
mymumble_install_php5: true
```

## Use username/password to login instead of ice_password
```yaml
mymumb_use_login_protection: true # Change to true if using the below and not the ICE Secret
mymumb_username: 'Username'
mymumb_password: 'MD5 Encrypted Password'
```

## Default variables
```yaml
################
# Install vars
################
mymumb_path: /var/www
mymumb_release_url: https://github.com/dieonar/MyMumb-Panel/archive/master.zip
mymumb_chmod_user: www-data
mymumb_chmod_group: www-data
mymumb_dependencies:
  - php-zeroc-ice
  - unzip


mymumb_install_apache2: false
mymumb_apache2_packages:
 - apache2
 - libapache2-mod-php5
mymumb_manage_config: true

mymumb_php5_icemodule_include_path: /usr/share/Ice-3.4.2/php/lib

mymumb_default_host: 127.0.0.1 # Ip of your Mumble Server. If its the same Server no need to change it.
mymumb_default_port: 6502 # The Port of your Mumble Server
mymumb_ice_password: 'icesecret' # The Password used in the mumble-server.ini
mymumb_default_language: 'en_EN' # Change the Language currently supported en_EN fr_FR de_DE
mymumb_use_login_protection: false # Change to true if using the below and not the ICE Secret
mymumb_username: 'Username'
mymumb_password: 'MD5 Encrypted Password' # ...
mymum_metaconnection: 'Meta:tcp'
```

Dependencies
------------

None

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: reminec.mymumb }

License
-------

MIT

Author Information
------------------

Ansible Role created by [Reminec](https://github.com/reminec)
