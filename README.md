# [rabbitmq](#rabbitmq)

RabbitMQ installation for Linux.

|GitHub|GitLab|Downloads|Version|Issues|Pull Requests|
|------|------|-------|-------|------|-------------|
|[![github](https://github.com/buluma/ansible-role-rabbitmq/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-rabbitmq/actions)|[![gitlab](https://gitlab.com/shadowwalker/ansible-role-rabbitmq/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-rabbitmq)|[![downloads](https://img.shields.io/ansible/role/d/4812)](https://galaxy.ansible.com/buluma/rabbitmq)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-rabbitmq.svg)](https://github.com/buluma/ansible-role-rabbitmq/releases/)|[![Issues](https://img.shields.io/github/issues/buluma/ansible-role-rabbitmq.svg)](https://github.com/buluma/ansible-role-rabbitmq/issues/)|[![PullRequests](https://img.shields.io/github/issues-pr-closed-raw/buluma/ansible-role-rabbitmq.svg)](https://github.com/buluma/ansible-role-rabbitmq/pulls/)|

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/buluma/ansible-role-rabbitmq/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- name: Converge
  hosts: all
  become: true

  pre_tasks:
    - name: Update apt cache.
      apt: update_cache=true cache_valid_time=600
      when: ansible_os_family == 'Debian'

  roles:
    - role: buluma.rabbitmq
```

The machine needs to be prepared. In CI this is done using [`molecule/default/prepare.yml`](https://github.com/buluma/ansible-role-rabbitmq/blob/master/molecule/default/prepare.yml):

```yaml
---
- name: Prepare
  hosts: all
  gather_facts: no
  become: yes

  roles:
  # - role: buluma.bootstrap
  # - role: buluma.epel
  # - role: buluma.buildtools
```

Also see a [full explanation and example](https://buluma.github.io/how-to-use-these-roles.html) on how to use these roles.

## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/buluma/ansible-role-rabbitmq/blob/master/defaults/main.yml):

```yaml
---
rabbitmq_daemon: rabbitmq-server
rabbitmq_state: started
rabbitmq_enabled: true

rabbitmq_version: "3.8.15"

rabbitmq_rpm: "rabbitmq-server-{{ rabbitmq_version }}-1.el{{ ansible_distribution_major_version }}.noarch.rpm"
rabbitmq_rpm_url: "https://packagecloud.io/rabbitmq/rabbitmq-server/packages/el/{{ ansible_distribution_major_version }}/{{ rabbitmq_rpm }}/download"

rabbitmq_deb: "rabbitmq-server_{{ rabbitmq_version }}-1_all.deb"
rabbitmq_deb_url: "https://packagecloud.io/rabbitmq/rabbitmq-server/packages/{{ ansible_distribution | lower }}/{{ ansible_distribution_release }}/{{ rabbitmq_deb }}/download"
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-rabbitmq/blob/master/requirements.txt).

## [State of used roles](#state-of-used-roles)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | GitLab |
|-------------|--------|--------|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Build Status GitHub](https://github.com/buluma/ansible-role-bootstrap/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions)|[![Build Status GitLab](https://gitlab.com/shadowwalker/ansible-role-bootstrap/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-bootstrap)|
|[buluma.buildtools](https://galaxy.ansible.com/buluma/buildtools)|[![Build Status GitHub](https://github.com/buluma/ansible-role-buildtools/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-buildtools/actions)|[![Build Status GitLab](https://gitlab.com/shadowwalker/ansible-role-buildtools/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-buildtools)|
|[buluma.epel](https://galaxy.ansible.com/buluma/epel)|[![Build Status GitHub](https://github.com/buluma/ansible-role-epel/workflows/Ansible%20Molecule/badge.svg)](https://github.com/buluma/ansible-role-epel/actions)|[![Build Status GitLab](https://gitlab.com/shadowwalker/ansible-role-epel/badges/master/pipeline.svg)](https://gitlab.com/shadowwalker/ansible-role-epel)|

## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:

![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-rabbitmq/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|[EL](https://hub.docker.com/repository/docker/buluma/enterpriselinux/general)|all|
|[Fedora](https://hub.docker.com/repository/docker/buluma/fedora/general)|all|
|[Debian](https://hub.docker.com/repository/docker/buluma/debian/general)|all|
|[Ubuntu](https://hub.docker.com/repository/docker/buluma/ubuntu/general)|all|

The minimum version of Ansible required is 2.4, tests have been done to:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them in [GitHub](https://github.com/buluma/ansible-role-rabbitmq/issues)

## [Changelog](#changelog)

[Role History](https://github.com/buluma/ansible-role-rabbitmq/blob/master/CHANGELOG.md)

## [License](#license)

[Apache-2.0](https://github.com/buluma/ansible-role-rabbitmq/blob/master/LICENSE).

## [Author Information](#author-information)

[Michael Buluma](https://buluma.github.io/)

Please consider [sponsoring me](https://github.com/sponsors/buluma).

### [Special Thanks](#special-thanks)

Template inspired by [Robert de Bock](https://github.com/robertdebock)
