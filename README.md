Test Environment
================

This repository includes a setup used in testing Reclass, with Vagrant, Salt and
Ansible.


How to get started
------------------

Spin up the sandbox:

    git clone https://github.com/reclass/test-sandbox
    cd test-sandbox
    vagrant up
    vagrant ssh


You can apply the reclass salt formula with either of the following:

    salt-call --local state.highstate
    salt-call --local state.sls reclass


With Reclass installed and setup, you ought to be able to see the inventory
and node info:

    vagrant@precise64:~$ reclass --inventory
    __reclass__:
      timestamp: Mon Nov 17 18:37:32 2014
    applications: {}
    classes: {}
    nodes:
      precise64:
        __reclass__:
          environment: base
          name: precise64
          node: ./precise64
          timestamp: Mon Nov 17 18:37:32 2014
          uri: yaml_fs:///etc/reclass/nodes/./precise64.yml
        applications: []
        classes: []
        environment: base
        parameters: {}

    vagrant@precise64:~$ reclass --nodeinfo precise64
    __reclass__:
      environment: base
      name: precise64
      node: ./precise64
      timestamp: Mon Nov 17 18:37:42 2014
      uri: yaml_fs:///etc/reclass/nodes/./precise64.yml
    applications: []
    classes: []
    environment: base
    parameters: {}


If you need to install vagrant, please see
http://docs.vagrantup.com/v2/installation/index.html.
