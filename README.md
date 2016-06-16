## r
 
[![Build Status](https://travis-ci.org/Oefenweb/ansible-r.svg?branch=master)](https://travis-ci.org/Oefenweb/ansible-r) [![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-r-blue.svg)](https://galaxy.ansible.com/list#/roles/3831)

Set up the latest version of R in Ubuntu systems.

#### Requirements

* `littler` (will be installed)

#### Variables

* `r_cran mirror`: [default: `http://cran.rstudio.com/`]: Your favorite [CRAN mirror](http://cran.r-project.org/mirrors.html)
* `r_bioclite_url`: [default: `https://bioconductor.org/biocLite.R`]: The `biocLite.R` script URL for [Bioconductor](http://bioconductor.org/) installs

* `r_install_dev`: [default: `false`]: Whether or not install the `r-base-dev` package
* `r_install`: [default: `['littler']`]: Additional (apt) packages to install (e.g. `r-recommended`)

* `r_packages_lib`: [default: `/usr/local/lib/R/site-library`]: The (default) library directory to install packages to
* `r_packages_repos`: [default: `"{{ r_cran_mirror }}"`]: The (default) URL to install packages from

* `r_packages`: [default: `[]`]: (CRAN) Packages to install or remove
* `r_packages.{n}.name`: [required]: The name of the package
* `r_packages.{n}.state`: [optional, default: `present`]: The state of the package
* `r_packages.{n}.type`: [optional, default: `cran`]: The type of the package (e.g. `bioconductor`)
* `r_packages.{n}.lib`: [optional, default: `r_packages_lib`]: The library directory to install the package to
* `r_packages.{n}.repos`: [optional, default: `r_packages_repos`]: The URL to install the package from

## Dependencies

None

#### Example(s)

##### Simple

```yaml
---
- hosts: all
  roles:
    - r
```

##### Advanced

```yaml
---
- hosts: all
  roles:
    - r
  vars:
    r_install_dev: true
    # apt packages
    r_install:
      - r-recommended
    # cran or bioconductor (R) packages
    r_packages:
      - name: dplyr
      - name: Biobase
        type: bioconductor
```

#### License

MIT

#### Author Information

Mischa ter Smitten

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Oefenweb/ansible-r/issues)!
