eNiXHosting.telegraf
=================

A role for deploying and configuring [Telegraf](http://www.influxdata.com) and extensions on unix hosts using [Ansible](http://www.ansible.com/).


Requirements
------------

Supported targets:

- Ubuntu 16.04 "Xenial"
- Debian 7 "Wheezy"
- Debian 8 "Jessie"
- Debian 9 "Stretch"


Role Variables
--------------

This roles comes preloaded with almost every available default. You can override each one in your hosts/group vars, in your inventory, or in your play. See the annotated defaults in `defaults/main.yml` for help in configuration. All provided variables start with `telegraf__`.

- `telegraf__` - desc

Dependencies
------------

- eNiXHosting.influxdata-repo ansible role. Automatically pulled if you use ansible-galaxy.

Usage
-----

Clone this repo into your roles directory:

    $ git clone https://gitlab.enix.org/ansible/ansible-telegraf.git roles/telegraf

Or use Ansible galaxy requirements.yml

    # telegraf from eNiXHosting
    - src: eNiXHosting.telegraf
      name: telegraf

And add it to your play's roles:

    - hosts: all
      roles:
        - role telegraf:
            telegraf__var: true

You can also use the role as a playbook. You will be asked which hosts to provision, and you can further configure the play by using `--extra-vars`.

    $ ansible-playbook -i inventory --extra-vars='{...}' main.yml

Still to do
-----------

- Handle `[global_tags]` configuration
- Handle `[agent]` configuration
- Handle `[[outputs:influxdb]]` configuration
- Handle plugins configuration using generic `/etc/telegraf/telegraf.d/`

Changelog
---------

### 0.1

Prerelease with only installation

License
-------

GPLv2

Author Information
------------------

Laurent Corbes <laurent.corbes@enix.fr> - http://www.enix.fr
