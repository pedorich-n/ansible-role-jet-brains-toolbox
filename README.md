Ansible Role: JetBrains Toolbox
===============================
[![License](https://img.shields.io/github/license/pedorich-n/ansible-role-jet-brains-toolbox)](LICENSE.md)

Installs JetBrains [Toolbox App](https://www.jetbrains.com/toolbox/app/). 

It downloads and unpacks the tar archive from JetBrains. After the installation is complete,
user should run `jetbrains-toolbox` executable manually. 

Forked from [webarchitect609/ansible-role-jet-brains-toolbox](https://github.com/webarchitect609/ansible-role-jet-brains-toolbox).
The difference from the original role is that it doesn't require a specific version of Toolbox to be specified. The task fetches this information from the JSON API.

Requirements
------------

Please, check [Toolbox System requirements](https://toolbox-support.jetbrains.com/hc/en-us/articles/115000978824-What-are-the-system-requirements-for-Toolbox-App-). 


Role Variables
--------------

Available variables are listed below, along with default values (see `defaults/main.yml`):

    toolbox_install_dir: "/opt"

Directory to install to.

    toolbox_install_for_user: ""

User, who will use the application.

    inotify_max_user_watches: "524288"
    
Value for [Inotify Watches Limit](https://youtrack.jetbrains.com/articles/IDEA-A-2/Inotify-Watches-Limit?_ga=2.156569083.1588360972.1630133506-996241065.1624703636)
to be set via `sysctl`. 

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: servers
      roles:
        - { role: jet_brains_toolbox }
      vars:
        toolbox_install_dir: "/opt"
        toolbox_install_for_user: "yourusername"

License & Author Information
-------
[BSD-3-Clause](LICENSE.md)
