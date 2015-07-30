## r
 
[![Build Status](https://travis-ci.org/Oefenweb/ansible-r.svg?branch=master)](https://travis-ci.org/Oefenweb/ansible-r) [![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-r-blue.svg)](https://galaxy.ansible.com/list#/roles/3831)

Set up the latest version of R in Ubuntu systems.

#### Requirements

None

#### Variables

* `r_cran mirror`: [default: `http://cran.rstudio.com/`]: Your favorite [CRAN mirror](http://cran.r-project.org/mirrors.html)
* `r_install_dev`: [default: `false`]: Whether or not install the `r-base-dev` package
* `r_install`: [default: `[]`]: Additional packages to install (e.g. `r-recommended`, `littler`)

## Dependencies

None

#### Example

```yaml
---
- hosts: all
  roles:
    - r
```

#### License

MIT

#### Author Information

Mischa ter Smitten

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Oefenweb/ansible-r/issues)!
