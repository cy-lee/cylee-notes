## Non-interactive Manipulate Disk Partitions
It might be useful, when you need to automation it in your Ansible playbook or preseed file.

### Prerequiste


Let's suppose you are working on Ubuntu 14.04/16.04
Install tools gdisk with

```shell
 sudo apt-get install -y gdisk
```

### Remove all partitions on specific disk


Change /dev/sdb to your device path.

```shell
 sgdisk --zap-all --clear --mbrtogpt /dev/sdb
```

### Create single disk partiton(Linux filesystem)


You cand list support types with following commands

```shell
 sgdisk -L
```

We take 8300 (Linux filesystem) as example, and create a partition that cover all available sectors on **/dev/sdb**.

```shell
 sgdisk -N 1 -t 1:8300  /dev/sdb
```
Don't forget reboot your system to take effect.
