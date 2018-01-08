Profit Trailer
=========

Installs and manages (multiple) Profit Trailer bot(s).

Requirements
------------

* Ansible: 2.2
* Hosts:
  * Python 2 or 3 installed
  * unzip installed

Role Variables
--------------

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `pt_config_only` | `false` | Whether or not to only update bot' config|
| `pt_default_version` | latest release | Which Profit Trailer version to use, you may overwrite this per bot|
| `pt_bot_user` | ptbot | Which user to install bots under |
| `pt_bots`| `[]` | List of your bots |
| `pt_bots[n].name`| `null` | Name of your bot|
| `pt_bots[n].version`| `null` | Used to override default version|

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: dennisenderink.profit-trailer }

Configuration
-------------

1. Add pt_bots list to your vars containing at least the name of the bot. 
2. It will look for the following templates:
  * templates/{ botname }/applications.properties.j2
  * templates/{ botname }/configuration.properties.j2
  * templates/{ botname }/trading/DCA.properties.j2
  * templates/{ botname }/trading/INDICATORS.properties.j2
  * templates/{ botname }/trading/PAIRS.properties.j2

When committing to version control don't forget to ignore a vars file with your API keys/server password or add them to an Ansible vault.

Running the bot
---------------

After initial setup you can run the update-config.yml playbook to skip everything but updating the bots config.

License
-------

BSD-3

Author Information
------------------

Author: Dennis Enderink <d.enderink@gmail.com>
Website: http://www.dennisenderink.nl/