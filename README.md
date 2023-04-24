[![CI](https://github.com/de-it-krachten/ansible-role-kubectl/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-kubectl/actions?query=workflow%3ACI)


# ansible-role-kubectl

<basic role description>



## Dependencies

#### Roles
None

#### Collections
- community.general

## Platforms

Supported platforms

- Red Hat Enterprise Linux 7<sup>1</sup>
- Red Hat Enterprise Linux 8<sup>1</sup>
- Red Hat Enterprise Linux 9<sup>1</sup>
- CentOS 7
- RockyLinux 8
- RockyLinux 9
- OracleLinux 8
- OracleLinux 9
- AlmaLinux 8
- AlmaLinux 9
- Debian 10 (Buster)
- Debian 11 (Bullseye)
- Ubuntu 18.04 LTS
- Ubuntu 20.04 LTS
- Ubuntu 22.04 LTS
- Fedora 36
- Fedora 37

Note:
<sup>1</sup> : no automated testing is performed on these platforms

## Role Variables
### defaults/main.yml
<pre><code>
# Github CLI - API
kubectl_api: https://api.github.com/repos/kubernetes/kubectl

# Github CLI - repo
kubectl_repo: https://github.com/kubernetes/kubectl

# Kubectl 
kubectl_base_url: https://storage.googleapis.com/kubernetes-release/release

# Lookup table for architecture
kubectl:
  architecture:
    x86_64: amd64
  system:
    Linux: linux
    Darwin: darwin

# Version of the CLI to install
kubectl_version: latest

# Location/ownership/permissions of the binary
kubectl_path: /usr/local/bin/kubectl
kubectl_owner: root
kubectl_group: root
kubectl_mode: '0755'
</pre></code>




## Example Playbook
### molecule/default/converge.yml
<pre><code>
- name: sample playbook for role 'kubectl'
  hosts: all
  become: "yes"
  roles:
    - deitkrachten.showinfo
  tasks:
    - name: Include role 'kubectl'
      ansible.builtin.include_role:
        name: kubectl
</pre></code>
