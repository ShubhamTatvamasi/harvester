# Cloud Init Config

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
ssh_authorized_keys:
  - ssh-ed25519
    AAAAC3NzaC1lZDI1NTE5AAAAIOxN5VcvopmXS7fAA7ESjGYHNuAIWE7d0Fyj9Lh8lVZu
    shubhamtatvamasi@gmail.com
```

Network Config:
```yaml
#network
  version: 2
  ethernets:
    enp1s0:
      addresses:
      - 192.168.4.51/24
      gateway4: 192.168.4.1
      nameservers:
        addresses:
        - 8.8.8.8
        - 8.8.4.4
```

