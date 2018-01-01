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

License
-------

BSD-3

Author Information
------------------

Author: Dennis Enderink <d.enderink@gmail.com>
Website: http://www.dennisenderink.nl/