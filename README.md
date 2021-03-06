# ansible-role-mongo-logrotate :ferris_wheel: #

An Ansible role for installing and configuring
[`logrotate`](https://github.com/logrotate/logrotate) for MongoDB hosts.

## Requirements ##

This role uses the `package` Ansible module, so [its
requirements](https://docs.ansible.com/ansible/latest/modules/package_module.html#requirements)
apply.

**IMPORTANT:** In order for this log rotation to work correctly, your
mongod configuration file (typically found in `/etc/mongod.conf`)
must contain the following settings:
```
systemLog:
    logRotate: reopen
processManagement:
    pidFilePath: /var/run/mongodb/mongod.pid
```

## Role Variables ##

None.

## Dependencies ##

None.

## Example Playbook ##

Here's how to use it in a playbook:

    - hosts: all
      become: yes
      become_method: sudo
      roles:
         - mongo_logrotate

## License ##

This project is in the worldwide [public domain](LICENSE.md).

This project is in the public domain within the United States, and
copyright and related rights in the work worldwide are waived through
the [CC0 1.0 Universal public domain
dedication](https://creativecommons.org/publicdomain/zero/1.0/).

All contributions to this project will be released under the CC0
dedication. By submitting a pull request, you are agreeing to comply
with this waiver of copyright interest.

## Author Information ##

David Redmin <david.redmin@trio.dhs.gov>
