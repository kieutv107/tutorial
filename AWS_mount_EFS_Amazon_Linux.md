# AWS: Mount EFS volume with Amazon Linux

(!) NOTE: `fs-8e7bee26` is the ID of the EFS.

## Install efs utils

```
cd ~
sudo yum install -y amazon-efs-utils
sudo mkdir efs
sudo mount -t efs fs-8e7bee26:/ efs
```

## Auto mount when instance start

Edit file `/etc/fstab` and append this line
```
sudo nano /etc/fstab
```
```
fs-8e7bee26:/ /home/ec2-user/efs efs defaults,_netdev 0 0
```
