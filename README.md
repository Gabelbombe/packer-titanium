Bucket ARN:

 wrsroot/Minda00$

Guest Additions and Extensions URL:

  https://download.virtualbox.org/virtualbox/6.0.0_RC1/

SSH Disabled by default, must use the following to set it up

```bash
sudo ifconfig <port> <ip address> netmask <netmask ip> up
sudo route add default gw <gateway ip> <port>
```
ens1f0

sudo ifconfig ens1f0 192.168.1.10 netmask 255.255.255.0 up
sudo route add default gw 192.168.1.10 ens1f0

/etc/sysconfig/network-scripts/ifcfg-eth0


["modifyvm", "{{.Name}}",   "--nic1",           "intnet" ],
["modifyvm", "{{ .Name }}", "--nic1",           "bridged"],
["modifyvm", "{{ .Name }}", "--bridgeadapter1", "eth0"]

packer build -on-error=abort -force titanium.json


#### IP stuff maybe?

https://www.serverlab.ca/tutorials/linux/administration-linux/how-to-configure-centos-7-network-settings/




## Importing to S3
aws-vault exec GEHC-077 --assume-role-ttl=60m -- \
aws ec2 --region us-west-2 import-image --description "Titanium VM" --disk-containers "file://s3-import.json"

vmimport trust policy:
https://www.cloudberrylab.com/resources/blog/how-to-configure-vmimport-role/
