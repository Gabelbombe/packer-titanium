Bucket ARN:

 wrsroot/Minda00$

SSH Disabled by default, must use the following to set it up

```bash
sudo ifconfig <port> <ip address> netmask <netmask ip> up
sudo route add default gw <gateway ip> <port>
```

sudo ifconfig 22 127.0.0.1 netmask 255.255.255.0 up




["modifyvm", "{{.Name}}",   "--nic1",           "intnet" ],
["modifyvm", "{{ .Name }}", "--nic1",           "bridged"],
["modifyvm", "{{ .Name }}", "--bridgeadapter1", "eth0"]

packer build -on-error=abort -force titanium.json
