Role Name
=========

motd - Populate content of /etc/motd file

Requirements
------------

None

Role Variables
--------------

This role requires a variable {{ owner }} to be set. This variable should contain the email address of the administrator of this system.

Dependencies
------------

None

Example Playbook
----------------

    - hosts: servers
      roles:
         - motd
	   vars:
	     owner: your_email_address

License
-------

BSD

Author Information
------------------

Jacques Philipp
	japhilip@redhat.com

