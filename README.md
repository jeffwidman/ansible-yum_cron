yum-cron
=========

Installs and manages `yum-cron`.

By default this role installs security updates every hour, and checks for but
does not install normal updates daily. For updates that aren't security flaws, I
prefer to delay upgrading until I'm available to fix anything that might go wrong.

Since the daily update level only checks but doesn't download, the notification
message will say "empty transaction", meaning it found an update, but didn't do
anything about it.

Requirements
------------

Tested on CentOS 7.
Untested but will likely work on CentOS 6 and equivalent RHEL versions.

Role Variables
--------------

You'll likely want to change the default `email_to` variable to an email address
that you actually monitor.


Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: yum-cron, email_to: support@rockclimbing.com, tags: ['yum_cron'] }

License
-------

BSD

Author Information
------------------

Jeff Widman jeff@jeffwidman.com
