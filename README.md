Repo Information
================
This repo will be used for the annual [Commitmas] presented by [vBrownBag] which
will be used for Team [Ansible]. Team [Ansible] will be ran by myself [mrlesmithjr]
so let's hope this goes well.

Team [Ansible] Objective
------------------------
We will be creating a series of [Ansible] roles. The roles can be any based on
the list provided below or any role that you would like to contribute. Make the
roles as simple or elaborate as you would like to. Our goal should be to release
at least 20 different roles by the end of [Commitmas] to the public for
consumption.

Activity Ideas
--------------
Creating [Ansible] roles
- Create [Ansible] role in `roles/`
  - Create Git branch to create new role
    ```
    git checkout master
    git checkout -b ansible-yourRoleName
    ```
  - Ensure that you have [Ansible] installed
    - Init a skeleton [Ansible] role
    ```
    cd roles
    ansible-galaxy init ansible-yourRoleName
    ```
- [Ansible] role ideas (Installed/configured)
  - Update Ubuntu/Debian apt-cache
  - Manage user accounts
  - Apache2
  - NGINX
  - MySQL
  - Docker Engine (Included but feel free to modify)
  - Hashicorp Tools
  - Virtualbox
  - NFS Server
  - DNS Server (Bind, DNSMasq, PowerDNS, Unbound)
  - DHCP Server (DNSMasq, ISC-DHCP, KEA)
  - GoCD
  - Rsyslog
  - Git
  - Logstash
  - Elasticsearch
  - SupervisorD
  - Cron Jobs
  - Jenkins
  - Redis
  - RabbitMQ
  - Rundeck
  - Docker Images/Containers
- Add additional [Ansible] requirements in `requirements.yml`
  - `- src: https://github.com/mrlesmithjr/ansible-users.git`
  - Update your [Ansible] `roles` using `requirements.yml`
    - `ansible-galaxy install -r requirements.yml -p ./roles`
- Testing [Ansible] roles using [Vagrant]
  Within this repo I have included the skeleton configurations to easily spin-up
  and test the role(s) using [Vagrant].
  - Requirements
    - [Ansible]
    - [Vagrant]
    - [Virtualbox]
  - Modify `playbook.yml` to include the role(s) to test under the following play:
  ```
  - hosts: test-nodes
    become: true
    vars:
      - pri_domain_name: 'test.vagrant.local'
    roles:
    tasks:
  ```
  - Spin-up [Vagrant] testing nodes (If you would like to spin-up more than one
    node you can change `N = 1` to `N = x` replacing `x` with the number of nodes
    you would like to spin-up in `Vagrantfile`)
  ```
  vagrant up
  ```
  - When you are done testing your [Vagrant] nodes you can easily tear-down the
  environment by:
  ```
  ./cleanup.sh
  ```
- At the end of [Commitmas] open a [PR] to have all of your changes added to
  the main repo. Ensure to learn how to [git rebase]

Additional Resources
--------------------
Below are some links to some additional reading resources if you have the time
or are just generally interested. Feel free to also add some additional resources
and commit those to the repo if you have any or know of any.
- https://github.com/mrlesmithjr/Ansible
- http://everythingshouldbevirtual.com/ansible-clean-formatted-playbooks
- http://everythingshouldbevirtual.com/ansible-setting-up-an-ansible-control-machine-part-1

License
-------

BSD

Author Information
------------------

Larry Smith Jr.
- [@mrlesmithjr]
- http://everythingshouldbevirtual.com
- mrlesmithjr [at] gmail.com

[@mrlesmithjr]: <https://twitter.com/mrlesmithjr>
[Ansible]: <https://ansible.com>
[Commitmas]: <https://github.com/commitmas>
[Git]: <https://git-scm.com/downloads>
[git rebase]: <http://rnelson0.com/2014/12/23/using-git-rebase-to-rewrite-history/>
[mrlesmithjr]: <https://twitter.com/mrlesmithjr>
[PR]: <https://help.github.com/articles/about-pull-requests/>
[Vagrant]: <https://www.vagrantup.com/>
[vBrownBag]: <http://vbrownbag.com/>
[Virtualbox]: <https://www.virtualbox.org/wiki/Downloads>
