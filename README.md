## mon

[![Travis CI](http://img.shields.io/travis/AlbanAndrieu/ansible-mon.svg?style=flat)](http://travis-ci.org/AlbanAndrieu/ansible-mon) [![Branch](http://img.shields.io/github/tag/AlbanAndrieu/ansible-mon.svg?style=flat-square)](https://github.com/AlbanAndrieu/ansible-mon/tree/master) [![Donate](https://img.shields.io/gratipay/AlbanAndrieu.svg?style=flat)](https://www.gratipay.com/AlbanAndrieu)  [![Ansible Galaxy](http://img.shields.io/badge/galaxy-alban.andrieu.mon-blue.svg?style=flat)](https://galaxy.ansible.com/list#/roles/2130) [![Platforms](http://img.shields.io/badge/platforms-debian%20/%20ubuntu-lightgrey.svg?style=flat)](#)

``alban.andrieu.monit`` role allows you to install and configure [Mon](http://linux-ha.org/mon) monitoring service
which can be used to monitor services on hosts.

Alerts can be sent to an e-mail address (by default
``monitoring@<your-domain>``.

### Installation

This role requires at least Ansible `v1.7.0`. 

To install it, run:

    ansible-galaxy install alban.andrieu.mon



### Role variables

List of default variables available in the inventory:

```yaml
    ---
    mon_enabled: yes                       # Enable module
    # Repository states: present or absent
    mon_repository_state: present
    
    #user: 'albandri' #please override me
    user: "{{ lookup('env','USER') }}"
    mon_owner: "{{ user }}"
    mon_group: "{{ mon_owner }}"
    #home: '~' #please override me
    home: "{{ lookup('env','HOME') }}"
    mon_owner_home: "{{ home }}"
    mon_home: "{{ mon_owner_home }}/.mon"
    
    mon_base_dir: "/etc/mon"
    mon_pkg_state: present
    
    mon_config_directory: "/etc/mon"
    mon_admin_email: "alban.andrieu@google.com"
    mon_weekly_email: "team@google.com"
    mon_weekend_email: "{{ mon_admin_email }}"
    mon_user_enabled: no
    mon_user: ""
    
    mon_localhost : "albandri"
    mon_custom_group: "test"   
    
    #mon_hostgroup_custom_group : "server1 server2"
    mon_hostgroup_custom_group : "{{ mon_localhost }}"
    mon_hostgroup_localhost : "{{ mon_localhost }}"
    mon_hostgroup_www : "{{ mon_localhost }}"
    mon_hostgroup_fs : "{{ mon_localhost }}"
    mon_hostgroup_gw : "{{ mon_localhost }}"
    mon_hostgroup_shell : "{{ mon_localhost }}"
    mon_hostgroup_ntp : "{{ mon_localhost }}"
    mon_hostgroup_dns : "{{ mon_localhost }}"
    
    docker_files_generated_directory: "./"
    docker_files_enable: no
    docker_volume_directory: "{{ mon_base_dir }}"
    docker_working_directory: "/home/vagrant"
    docker_image_name: "nabla/ansible-mon"
```




### Authors and license

`mon` role was written by:
- [Alban Andrieu](fr.linkedin.com/in/nabla/) | [e-mail](mailto:alban.andrieu@free.fr) | [Twitter](https://twitter.com/AlbanAndrieu) | [GitHub](https://github.com/AlbanAndrieu)
- License: [GPLv3](https://tldrlegal.com/license/gnu-general-public-license-v3-%28gpl-3%29)

### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/AlbanAndrieu/ansible-mon/issues)!

***

README generated by [Ansigenome](https://github.com/nickjj/ansigenome/).
