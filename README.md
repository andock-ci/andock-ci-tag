andock-ci.tag (Andock-ci tag role.)
=========

**andock-ci.tag** is a Ansible role which:
* Checks out repository (e.g. from github)
* Add a tag (default: git_tag: "{{branch}}--{{ansible_date_time.date}}--{{ansible_date_time.hour}}-{{ansible_date_time.minute}}") 
* Push the tag  
  

Requirements
------------

In order to build your apps with Andock CI, you will need:

* Ansible in your deploy machine
* git on both machines


Role Variables
--------------


```yaml
vars:
    git_repository_path: git@github.com:andock-ci/drupal-8-demo-build.git
    branch: "master-build"
    build_path: ~/ansible/tag
    git_tag: "{{branch}}--{{ansible_date_time.date}}--{{ansible_date_time.hour}}-{{ansible_date_time.minute}}
```

Installation
------------

Andock-CI is an Ansible role distributed globally using [Ansible Galaxy](https://galaxy.ansible.com/). In order to install Andock-CI role you can use the following command.

```
$ ansible-galaxy install andock-ci.tag
```

Update
------

If you want to update the role, you need to pass **--force** parameter when installing. Please, check the following command:

```
$ ansible-galaxy install --force andock-ci.tag
```

Dependencies
------------

@TODO

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

---
    - name: Tag repository
      hosts: localhost
      roles:
        - role: andock-ci.tag
        git_repository_path: git@github.com:andock-ci/drupal-8-demo-build.git
        branch: "master-build"
        build_path: ~/ansible/tag


License
-------

BSD

Author Information
------------------

Christian Wiedemann (christian.wiedemann@key-tec.de)
