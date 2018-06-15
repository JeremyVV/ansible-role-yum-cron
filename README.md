# Ansible Role: yum-cron

[![Build Status](https://api.travis-ci.org/JeremyVV/ansible-role-yum-cron.svg?branch=master)](https://travis-ci.org/JeremyVV/ansible-role-yum-cron)

Yum-cron provides a convenient way to check for, download and apply updates automatically.

## Requirements

Ansible 2+


## Operating Systems
- RHEL 7+
- CentOS 7+


## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
# default                            = yum upgrade
# security                           = yum --security upgrade
# security-severity:Critical         = yum --sec-severity=Critical upgrade
# minimal                            = yum --bugfix update-minimal
# minimal-security                   = yum --security update-minimal
# minimal-security-severity:Critical =  --sec-severity=Critical update-minimal
yumcron_update_cmd: "default"

# Whether a message should be emitted when updates are available,
# were downloaded, or applied.
yumcron_update_messages: "yes"

# Whether updates should be downloaded when they are available.
yumcron_download_updates: "yes"

# Whether updates should be applied when they are available.  Note
# that download_updates must also be yes for the update to be applied.
yumcron_apply_updates: no

# How to send messages.  Valid options are stdio and email.  If
# emit_via includes stdio, messages will be sent to stdout; this is useful
# to have cron send the messages.  If emit_via includes email, this
# program will send email itself according to the configured options.
# If emit_via is None or left blank, no messages will be sent.
yumcron_emit_via: stdio

# List of addresses to send messages to.
yumcron_email_to: root

```

## Dependencies

  - none

## Example Playbook

    - hosts: servers
      roles:
        - yum-cron

## License

MIT

## Author Information

This role was created in 2018 by [Jeremy Van Veelen](https://www.techgooroo.net/).

