# Ansible role development template

[![Build Status](https://travis-ci.org/insspb/ansible-role-template.svg?branch=master)](https://travis-ci.org/insspb/ansible-role-template) ![GitHub](https://img.shields.io/github/license/insspb/ansible-role-template.svg)

This is new template for all future roles. This template include docker molecule tests from the early beginning. This should make role development bugs free in future.

The idea of this project is to receive template with configured tests from ansible role development initialization. 

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

## yamllint note

yamllint check is one of requirements to get high ansible galaxy role score. This project has strict yamllint configuration. You can make work easier be adding this set of rules:

```yaml
rules:
  new-line-at-end-of-file: disable
  trailing-spaces: disable
  document-start: disable
```

Current ansible-galaxy yamllint requirements can be found in [documentation](https://galaxy.ansible.com/docs/contributing/content_scoring.html) or [directly](https://github.com/ansible/galaxy/blob/devel/galaxy/importer/linters/yamllint.yaml).

## License

MIT

## Author Information

This role is contributed and maintained by [Andrey Shpak](mailto:github@ashpak.ru). I am always available for [hire](https://www.upwork.com/o/profiles/users/_~01a780866aa29e4429/).
