# Role Name

Master branch: [![Build Status](https://travis-ci.org/insspb/ansible-role-template.svg?branch=master)](https://travis-ci.org/insspb/ansible-role-template)

This is new template for all future roles. This template include docker molecule tests from the early beginning. This should make role development bugs free in future.

## Requirements

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here.

## Role Variables

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

## Dependencies

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

## Example Playbook

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

## Development information

This role is developed with community help.
Process of development follows this rule:

- You are free to add any pool request to develop branch. All request will be answered in timely manner.
- If you want to made any contribution, but do not know where to start - check issues.
- Master branch updated just after significant changes in develop.
- Please include documentation for new features.
- Please use variables.
- Please do not forget to set defaults.
- Please do your best to keep backward compatibility if possible.
- Please use packet installation as default software installation method. Source installation must be optional anywhere if possible.
- Please use official software developers repositories instead of general Debian/Ubuntu/Centos etc for main application.
- Do you best to keep role independent from any other roles. User must have the way to choose what roles to use.
- Do not forgot to include tests.

## License

MIT

## Author Information

This role is contributed and maintained by [Andrey Shpak](http://www.ashpak.ru). I am always available for [hire](https://www.upwork.com/o/profiles/users/_~01a780866aa29e4429/).
