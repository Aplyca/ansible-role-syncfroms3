Ansible Role Sync From S3
====================

An Ansible role that sync app content from S3

[![Build Status](https://travis-ci.org/Aplyca/ansible-role-syncfroms3.svg?branch=master)](https://travis-ci.org/Aplyca/ansible-role-syncfroms3)
[![Circle CI](https://circleci.com/gh/Aplyca/ansible-role-syncfroms3.svg?style=svg)](https://circleci.com/gh/Aplyca/ansible-role-syncfroms3)

Ansible Role that sync content from S3 on Debian/Ubuntu.

Requirements
------------

Use hash behavior for variables in ansible.cfg
See example: https://github.com/Aplyca/ansible-role-syncfroms3/blob/master/tests/ansible.cfg
See official docs: http://docs.ansible.com/intro_configuration.html#hash-behaviour

Installation
------------

Using ansible galaxy:

```bash
ansible-galaxy install aplyca.Syncfroms3
```
You can add this role as a dependency for other roles, add the role to the meta/main.yml file of your own role:

```yaml
dependencies:
  - { role: aplyca.Syncfroms3 }
```

# Ask for confirmation
This is a risky tasks so the role ask for a variable `confirmation`, you can add the confirmation in the playbook, like this: 

```yaml
---
- hosts: sync.server.com
  gather_facts: no
  vars_prompt:
    - name: "confirmation"
      prompt: "Are you sure to sync content from S3 [y/n]?"
  roles:
    - { role: aplyca.Syncfroms3, tags: ["froms3"] }
```

Role Variables
--------------
See default variables: https://github.com/Aplyca/ansible-role-syncfroms3/blob/master/defaults/main.yml

Dependencies
------------

- MySQL
- AWS CLI


License
-------

MIT / BSD

Author Information
------------------

Mauricio Sánchez from Aplyca SAS (http://www.aplyca.com)
