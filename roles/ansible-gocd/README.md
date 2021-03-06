Ansible GoCD Server
===================

This role will help setup GoCD server for Debian and RedHat based systems. GoCD is an Open source continuous delivery server to model and visualize complex workflows.

Requirements
------------

GoCD uses a server/agent model. This role deploys the GoCD server component, and assumes a host defined in /etc/ansible/hosts in groups called [gosrv]. You can adjust these per your level of CDO (OCD in alphabetical order). Adjust the become_user to match your system and organizational requirements.

Additionally, GoCD requires Java, this role will install Java accordingly. Additional documentation is available [here](https://docs.go.cd/current/installation/install/server/linux.html).

Role Variables
--------------

jdkver: Version of Java used by the install documentation
gocdyumrepo: yum repo config as defined in official GoCD documentation
gocdaptreo: apt repo config as defined in official GoCD documentation
gocdkeyurl: gpg key as defined in official GoCD documentation


Example Playbook
----------------

An example of how to use the role:

- hosts: gosrv
  become: yes
  become_user: root
  roles:
     - ansible-gocd
	 
License
-------

BSD

Author Information
------------------

This role is for testing purposes, and offers no warranty. Use at your own risk. Forks and PRs welcome.
