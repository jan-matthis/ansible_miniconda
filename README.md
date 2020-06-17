# Miniconda

Ansible role to install [Miniconda](https://docs.conda.io/en/latest/miniconda.html) on Unix.


## Installation

```commandline
$ ansible-galaxy install jan_matthis.miniconda
```

## Variables

```yaml
# Installer
# Latest versions: https://repo.anaconda.com/miniconda/
miniconda_installer: Miniconda3-py37_4.8.3-Linux-x86_64.sh

# Checksums
# Obtainable via: https://repo.anaconda.com/miniconda/
miniconda_installer_checksums:
  Miniconda3-py37_4.8.3-Linux-x86_64.sh: "md5:751786b92c00b1aeae3f017b781018df"

# Installation directory
miniconda_dir: "/opt/miniconda"

# Symlink
miniconda_symlink: false
miniconda_symlink_dir: "/usr/local"

# Append to PATH
miniconda_path_append: true
miniconda_path_append_file: "{{ansible_env.HOME}}/.profile"

# Append conda.sh execution
miniconda_conda_sh_append: true
miniconda_conda_sh_append_file: "{{ansible_env.HOME}}/.profile"

# Mirror
miniconda_mirror: "https://repo.anaconda.com/miniconda/"

# Temporary directory for downloading installer
miniconda_download_dir: "/tmp"

# Timeout for download
miniconda_download_timeout: 600
```


## Example

```yaml
- hosts: servers
  include_role:
    name: jan_matthis.miniconda
  vars:
    miniconda_dir: "{{ ansible_env.HOME }}/miniconda"
```


## Testing

Tests can be run using [`molecule`](https://molecule.readthedocs.io/en/latest/) and `docker`.


## License

MIT
