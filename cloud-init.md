# CLoud Init Config

User Config:
```yaml
#cloud-config
users:
- name: ubuntu
  plain_text_passwd: 'ubuntu'
  sudo: ALL=(ALL) NOPASSWD:ALL
  groups: sudo
  shell: /bin/bash
  lock_passwd: false
ssh_pwauth: True
package_update: true
packages:
  - qemu-guest-agent
runcmd:
  - - systemctl
    - enable
    - --now
    - qemu-guest-agent.service

```

Ubuntu Network Config
```yaml
#network
  version: 2
  ethernets:
    eth0:
      addresses:
      - 192.168.4.51/24
      gateway4: 192.168.4.1
      nameservers:
        addresses:
        - 8.8.8.8
        - 8.8.4.4
```

