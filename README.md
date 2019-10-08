# Ansible role to install & configure filebeat
Ansible role that installs filebeat on Linux using the apt package elastic provides.

Also sets up the filebeat.yml from basic vars filebeat_conf

## Requirements
Debian based Linux, tested on Ubuntu. Recent version of Ansible. Only utilized Ansible core modules.

## Role Variables
```yaml
# List of files to read logs from:
filebeat_conf:
  
  output.elasticsearch:
      hosts: ["https://localhost:9200"]
      username: "filebeat_internal"
      password: "YOUR_PASSWORD"
```

You can also define variable `filebeat_extra_prospectors` on a per-host or
per-group basis.  This variable is concatenated with `filebeat_prospectors`
when rendering the configuration template.


## Dependencies
This role has no dependencies to other roles.

## Example Playbook
Copy this role into the roles/mediapeers.filebeat dir in your Ansible project. Preferably add it as a submodule.
You can also install it with `ansible-galaxy install mediapeers.filebeat`.
Then use it like so:

```yaml
- name: My nice play
  hosts: servers
  roles:
    - ansible-filebeat
```

## License
BSD

## Author Information
Stefan Horning <horning[-at-]mediapeers.com>
