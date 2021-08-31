---
title: NVUE - NVIDIA User Expeience Cheat Sheet
author: NVIDIA
weight: 20
toc: 4
---

## Overview

The NVIDIA User Experience — NVUE — is a complete Linux management framework built for modern, programmable networks. It provides an API-first, structured object model with a declarative CLI which provides *commit/confirm*, *diff*, *rollback*, and *branch* capabilities. Not only does NVUE provide configuration options, but it also provides *show* commands. 

NVUE is the default CLI starting Cumulus Linux 5.0. 

## Tabbed Autocompletion and Contextual Help

NVUE is a user-friendly, command-line interface. Once you type *`nv`*, press *TAB* for a prompt for your next step. Then continue typing the next part of the command.

```
cumulus@leaf01:mgmt:~$ nv <<press Tab>>
config  set     show    unset
cumulus@leaf01:mgmt:~$ nv set <<press Tab>>
acl        evpn       mlag       platform   router     system
bridge     interface  nve        qos        service    vrf
```

If you need a reminder about how to utilize a command option, use *`-h`* or *`--help`*. For example, if you want to know how to configure a VXLAN, run:

```
cumulus@leaf01:mgmt~$ nv set nve vxlan -h
Usage:
  nv set nve vxlan [options] [<attribute> ...]

Description:
  VxLAN

Attributes:
  mlag             VxLAN specific MLAG address
  source           Source address
  flooding         Configuration to specify how BUM traffic in the overlay is
                   handled. This applies to all overlays (VNIs), but can be
                   overridden by VNI-specific configuration.
  enable           Turn the feature 'on' or 'off'. The default is 'off'.
  arp-nd-suppress  Controls dynamic MAC learning over VXLAN tunnels based on
                   received packets. This applies to all overlays (VNIs).
  mac-learning     Controls dynamic MAC learning over VXLAN tunnels based on
                   received packets. This applies to all overlays (VNIs), but
                   can be overridden by VNI-specific configuration.
  mtu              interface mtu
  port             UDP port for VXLAN frames

General Options:
  -h, --help       Show help.
```
{{%notice note%}}
One of the great NVUE aspects is that It “figures out” command order at apply time so no specific configuration order is required.
{{%/notice%}}

## Getting Started

Use *`nv set`* to create a new or modify an existing configuration. For example, to set switch port interface configuration, run *`nv set interface [OPTIONS]`* command:

```
cumulus@leaf01:mgmt:~$ nv set interface swp1 bridge domain br_default
cumulus@leaf01:mgmt:~$ nv set interface vlan100 type svi
```

To remove an existing configuration, use *`nv unset [OPTIONS]`* command:

```
cumulus@leaf01:mgmt:~$ nv unset bridge domain br_default vlan 10
```

NVUE stages all your updates before updating the configuration. Check your changes with *`nv config diff [config] [config]`*:

```
cumulus@leaf01:mgmt:~$ nv config diff empty pending
- set:
    bridge:
      domain:
        br_default:
          vlan:
            '100': {}
    router:
      bgp:
        autonomous-system: leaf
        enable: on
        router-id: 192.168.100.1
    interface:
      swp20:
        bridge:
          domain:
            br_default:
              access: 100
      swp20-21:
        type: swp
      swp21:
        bridge:
          domain:
            br_default: {}
      vlan100:
        ip:
          address:
            192.168.100.254/24: {}
        type: svi
        vlan: 100

ADD UNDEST ???

```

When you're satisfied with your changes, commit them:

```
cumulus@leaf01:mgmt:~$ nv config apply
```

OLD FROM HERE

To check the current state of your switch's configuration: 
cumulus@leaf01:~$ net show configuration 
hostname leaf01

interface lo
  address 10.0.0.11/32

interface eth0

interface swp1
…

When viewing the whole configuration, you can also review the commands used to create it:
cumulus@leaf01:~$ net show configuration commands

Or you can review the content of the files where the configuration is stored, such as /etc/network/interfaces or /etc/quagga/Quagga.conf:
cumulus@leaf01:~$ net show configuration files
