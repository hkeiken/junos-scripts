## Table of contents
* [General info](#general-info)
* [Technologies](#technologies)
* [Setup](#setup)
* [How to use](#use)
## General info
This is a small project to use PyEZ to send JunOS set configuration
via netconf to JunOS devices.



This is a quick set of scripts to prove functions, not considered
a production ready script.

## Technologies
The project uses Python 3 with a few standard libraries and PyEZ
(https://www.juniper.net/documentation/product/en_US/junos-pyez))

## Setup

For this to work Netconf has to be enabled on the devices:
```
set system services netconf ssh
```

In addition there is a need for Python3 and PyEZ to be installed.
PyEZ can be installed like this if Python3 is installed:
```
sudo pip3 install junos-eznc
```

Finally, one will have to make the script executable:
```
chmod u+rwx simple-push-set-config.py
```

## How to use

Four variables have to be input:
Hostname - ip-address or hostname of device reachable
Username - on the JunOS device
Password - of the user on the JunOS device
Configfile - A file with a number of set commands to send to the device.

Example of use:

```
% ./simple-push-set-config.py 172.16.75.142 myuser password configfile
```
