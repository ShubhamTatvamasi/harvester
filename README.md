# harvester

SSH into system:
```bash
ssh rancher@192.168.4.40
```

Update mounted disk to read and write:
```bash
sudo mount -o remount,rw /dev/sdb3 /run/initramfs/cos-state
```

Check the change:
```bash
mount | grep /dev/sda3
```

Install qemu guest agent:
```bash
sudo zypper install qemu-guest-agent
```

update fstab:
```bash
sudo vim /etc/fstab
```

Change `ro` -> `rw`
```
/dev/loop0 / auto rw 0 0
```

Chnage manually:
```bash
sudo mount -o remount,rw /dev/loop0 /
```

