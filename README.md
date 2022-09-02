# Ansible strategy collection check

```shell
(base) > ansible-doc -t strategy -l
debug                Executes tasks in interactive debug session
free                 Executes tasks without waiting for all hosts
host_pinned          Executes tasks on each host without interruption
itd27m01.example.poc Executes tasks in a linear fashion
linear               Executes tasks in a linear fashion
```

```shell
(base) > ansible-playbook site.yml

PLAY [Check strategy plugin] ******************************************************************************
ERROR! Unexpected Exception, this is probably a bug: inside my strategy plugin
to see the full traceback, use -vvv

(base) > ansible-playbook site.yml

PLAY [Check strategy plugin] ******************************************************************************

TASK [Gathering Facts] ************************************************************************************
ok: [localhost]

TASK [ping] ***********************************************************************************************
ok: [localhost]

PLAY RECAP ************************************************************************************************
localhost             : ok=2    changed=0    unreachable=0    failed=0    skipped=0    rescued=0  ignored=0
```

```shell
(base) > ansible --version
ansible [core 2.12.6]
  config file = /Users/me/src/ansible-strategy-collection/ansible.cfg
  configured module search path = ['/Users/me/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']
  ansible python module location = /Users/me/opt/anaconda3/lib/python3.8/site-packages/ansible
  ansible collection location = /Users/me/src/ansible-strategy-collection
  executable location = /Users/me/opt/anaconda3/bin/ansible
  python version = 3.8.13 (default, Mar 28 2022, 06:13:39) [Clang 12.0.0 ]
  jinja version = 2.11.3
  libyaml = True
```