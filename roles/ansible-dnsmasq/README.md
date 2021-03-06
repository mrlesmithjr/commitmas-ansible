Role Name
=========

An [Ansible] role to install/configure [DNSMasq]

Requirements
------------

None

Role Variables
--------------

```
---
# defaults file for ansible-dnsmasq
dnsmasq_add_custom_domain: false  #defines if dnsmasq should be configured for internal
dnsmasq_config: false  #defines if DNSMASQ should be configured
dnsmasq_dhcp_boot: 'pxelinux.0,{{ inventory_hostname }},{{ dnsmasq_pri_bind_address }}'
dnsmasq_dhcp_scopes:  #define dhcp scopes to be used if dhcp is enabled
  - start: '192.168.1.128'
    end: '192.168.1.224'
    netmask: '255.255.255.0'
  - start: '192.168.2.128'
    end: '192.168.2.224'
    netmask: '255.255.255.0'
dnsmasq_dns_search: '{{ dnsmasq_pri_domain_name }}'  #define your dns search
dnsmasq_enable_dhcp: false  #defines if DHCP services are provided by DNSMASQ
dnsmasq_enable_dhcp_tftp: false  #defines if DHCP and TFTP services are provided by DNSMASQ
dnsmasq_enable_forwarders: false  #defines if forwarders should be used
dnsmasq_enable_tftp: false  #defines if TFTP services are provided by DNSMASQ
dnsmasq_nameservers:  #define your dns servers
  - '8.8.4.4'
  - '8.8.8.8'
dnsmasq_ntp_servers:  #defines ntp servers for clients to poll
  - '131.107.13.100'
  - '216.228.192.69'
dnsmasq_pri_bind_address: '{{ ansible_default_ipv4.address }}'
dnsmasq_pri_bind_interface: '{{ ansible_default_ipv4.interface }}'
dnsmasq_pri_domain_name: 'example.org'
dnsmasq_pri_netmask_cidr: '24'  #defines netmask cidr value 255.255.255.0 == 24
dnsmasq_pri_network: '{{ ansible_default_ipv4.network }}'
dnsmasq_tftpboot_dir: '/var/lib/tftpboot'  #Define tftpboot directory
```

Dependencies
------------

None

Example Playbook
----------------

````
---
- hosts: all
  become: true
  vars:
  roles:
    - role: ansible-dnsmasq
  tasks:
````

License
-------

BSD

Author Information
------------------

Larry Smith Jr.
- @mrlesmithjr
- http://everythingshouldbevirtual.com
- mrlesmithjr [at] gmail.com

[Ansible]: <https://ansible.com>
[DNSMasq]: <http://www.thekelleys.org.uk/dnsmasq/doc.html>
