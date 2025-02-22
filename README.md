# Ansible Role: NTP

[![Build Status](https://travis-ci.org/yfix/ansible-role-ntp.svg?branch=master)](https://travis-ci.org/yfix/ansible-role-ntp)

Installs NTP on RedHat/CentOS and Debian/Ubuntu Linux servers.

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    ntp_enabled: true

Whether to start the ntpd service and enable it at system boot. On many virtual machines that run inside a container (like OpenVZ or VirtualBox), it's recommended you don't run the NTP daemon, since the host itself should be set to synchronize time for all it's child VMs.

    ntp_timezone: Europe/Kiev

Set the timezone for your server.


## Dependencies

None.

## Example Playbook

    - hosts: db-servers
      vars_files:
        - vars/main.yml
      roles:
        - { role: yfix.ntp }

*Inside `vars/main.yml`*:

    ntp_timezone: Europe/KIev
