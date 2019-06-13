# Ansible role development template

[![Build Status](https://travis-ci.org/insspb/ansible-role-template.svg?branch=master)](https://travis-ci.org/insspb/ansible-role-template) ![GitHub](https://img.shields.io/github/license/insspb/ansible-role-template.svg)

This is new template for all future ansible roles. This template include molecule tests based on docker images from the early beginning. This should make role development bugs free in the future.

The idea of this project is to receive template with configured tests for ansible role development initialization.

The second idea to bring all tests to local. That's why `tox` and docker used. This make local testing as simple as running `tox` command. Unfortunately this makes travis matrix a little simpler and `travis` builds by default takes a long time to execute even with trivial roles.

All docker container tests are repeated for every python environment selected in `tox`. This can be unnecessarily in local testing and developemnt stage, so it is recommended to limit `tox` with `-e py36` attributes (example for python 3.6). This will run only one environment.

Please keep in mind that after template installation you will not use core `tox.ini` file. This file required only for template deep testing.

## Usage

Init new role with [molecule](https://github.com/ansible/molecule) tool:

```bash
pip install molecule
molecule init template --url https://github.com/insspb/ansible-role-template
```

Init new role with [cookiecutter](https://github.com/audreyr/cookiecutter) tool:

```bash
pip install cookiecutter
cookiecutter https://github.com/insspb/ansible-role-template
```

## Over-testing note

You may notice that in `tox` configuration we are using a lot of python versions and do the same. Basically this needed just to ensure that local testing will not fail on wrong python version installed. All tests do the same.  

From the other side this approach can make fail-positive `travis` or `tox` fails if some dependency package cannot be launched in some python version. For example that's why python 3.8 support was [dropped](https://github.com/insspb/ansible-role-template/commit/f9785bb017236260182e7e02e80bb368a08707f0), while this version still in development mode.

You may also notice that we run `tox` from `tox` in the core template. This behavior is needed to ensure that template configuration is correct and installed template will work from scratch without any issues. As we mentioned before you will not see two `tox.ini` files after template installation.

## yamllint note

`yamllint` check is one of requirements to get high `ansible-galaxy` role score. This project has strict `yamllint` configuration. You can make work easier be adding this set of rules:

```yaml
rules:
  new-line-at-end-of-file: disable
  trailing-spaces: disable
  document-start: disable
```

Current `ansible-galaxy` `yamllint` requirements can be found in [documentation](https://galaxy.ansible.com/docs/contributing/content_scoring.html) or [directly](https://github.com/ansible/galaxy/blob/devel/galaxy/importer/linters/yamllint.yaml).

## Docker images note

By default this template uses well-known and well-tested docker images by [Jeff Geerling](https://github.com/geerlingguy). You can specify you own images on installation stage. Please do not forget to review `molecule/molecule.yml` if your change this behavior.

Default available images are:

- CentOS 6
- CentOS 7
- Debian 8
- Debian 9
- Debian 10
- Ubuntu 16.04
- Ubuntu 18.04

This template does not include Fedora images. At all.

## License

MIT

## Author Information

This role is contributed and maintained by [Andrey Shpak](mailto:github@ashpak.ru). I am always available for [hire](https://www.upwork.com/o/profiles/users/_~01a780866aa29e4429/).
