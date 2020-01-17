# macvtap plugin

## Overview

This project modified from [cni macvlan](https://github.com/containernetworking/plugins/tree/master/plugins/main/macvlan)

## Example configuration

```
{
	"name": "mynet",
	"type": "macvtap",
	"master": "eth0",
	"ipam": {
		"type": "dhcp"
	}
}
```

## Network configuration reference

* `name` (string, required): the name of the network
* `type` (string, required): "macvtap"
* `master` (string, optional): name of the host interface to enslave. Defaults to default route interface.
* `mode` (string, optional): one of "bridge", "private", "vepa", "passthru". Defaults to "bridge".
* `mtu` (integer, optional): explicitly set MTU to the specified value. Defaults to the value chosen by the kernel. The value must be \[0, master's MTU\].
* `ipam` (dictionary, required): IPAM configuration to be used for this network. For interface only without ip address, create empty dictionary.
