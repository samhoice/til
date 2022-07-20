# One Script to Rule Them All

Github has a paradigm of scripts to bootstrap a project, located here: https://github.com/github/scripts-to-rule-them-all

This gives a standard way of setting up project scripts for consistency. For each project all the stuff you need to get started will be available in the same locations under the same names. It should also keep your CI and DevOps cleaner because everything will be run the same way.

The scripts are:
- bootstrap
  - fills dependencies. So, `python -m pip install...`
- setup
  - initial setup
  - calls bootstrap
- update
  - calls bootstrap
  - can call db migrations, or whatever
- server
  - launch locally
  - launch other required stuff, as well
    - docker compose, most likely?
- test
  - run tests
- cibuild
  - run by ci
  - calls test
- console
  - starts a console
  - could launch a django console, for instance

