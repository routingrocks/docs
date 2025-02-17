---
title: What's New
author: NVIDIA
weight: 5
toc: 2
---
This document supports the Cumulus Linux 5.3 release, and lists new platforms, features, and enhancements.

- For a list of all the platforms supported in Cumulus Linux 5.3, see the {{<exlink url="www.nvidia.com/en-us/networking/ethernet-switching/hardware-compatibility-list/" text="Hardware Compatibility List (HCL)">}}.
- For a list of open and fixed issues in Cumulus Linux 5.3, see the {{<link title="Cumulus Linux 5.3 Release Notes" text="Cumulus Linux 5.3 Release Notes">}}.
- To upgrade to Cumulus Linux 5.3, follow the steps in {{<link url="Upgrading-Cumulus-Linux">}}.
<!-- vale off -->
## What's New in Cumulus Linux 5.3.0
<!-- vale on -->
Cumulus Linux 5.3.0 supports new platforms, provides bug fixes, and contains several new features and improvements.

### Platforms

- NVIDIA SN3750SX (5G Spectrum-2) available for early access
- All NVIDIA Spectrum-2 and Spectrum-3 switches support 1G

### New Features and Enhancements

- {{<link url="Quality-of-Service/#ptp-shaping" text="PTP shaper for Spectrum-1">}}
- Improve port breakout and speed configuration in the `etc/cumulus/ports.conf ` file
- {{<link title="What Just Happened (WJH)" text="WJH">}} can monitor additional packet drops: Layer 1, ACL, and buffer
- {{<link url="NVUE-Object-Model" text="NVUE">}} enhancements include:
  - Performance improvements
  - {{<link url="Configure-SNMP" text="SNMP Server">}} and {{<link url="Configure-SNMP-Traps" text="SNMP trap">}} commands
  - RoCE commands
  - support for switchd knobs
  - Updated `nv show platform hardware` command output to include memory and CPU utilization information
  - New BGP commands: {{<link url="Optional-BGP-Configuration/#bgp-dynamic-neighbors" text="BGP dynamic neighbor">}}, 
  - New Route map commands:
  - {{<link title="What Just Happened (WJH)" text="WJH commands">}}
  - {{<link url="Prescriptive-Topology-Manager-PTM/#check-link-state" text="PTM enable command">}} to check link state
  - {{<link url="NVUE-CLI/#search-for-a-specific-configuration" text="Search for a specific configuration">}} in the entire object model
  - text obfuscation support
  - You can use hyphens in names for hosts, route maps, ACLs, AS-Path lists, prefix lists, community lists, and VRFs.
  - Change commands from `enable on and enable off` to `set enable` and `unset enable` (`enable on and enable off` commands continue to be supported for backward compatability)
  - New command list:
   {{< tabs "TabID34 ">}}
{{< tab "show commands ">}}

```
ADD HERE
```

{{< /tab >}}
{{< tab "set commands ">}}

```
ADD HERE
```

{{< /tab >}}
{{< tab "unset commands ">}}

```
ADD HERE
```

{{< /tab >}}
{{< /tabs >}}

{{%notice info%}}
Cumulus Linux 5.3 includes the NVUE object model. After you upgrade to Cumulus Linux 5.3, running NVUE configuration commands replaces the configuration in files such as `/etc/network/interfaces` and `/etc/frr/frr.conf` and removes any configuration you add manually or with automation tools like Ansible, Chef, or Puppet. To keep your configuration, you can do one of the following:

- Update your automation tools to use NVUE.
- {{<link url="NVIDIA-User-Experience-NVUE/#configure-nvue-to-ignore-linux-files" text="Configure NVUE to ignore certain underlying Linux files">}} when applying configuration changes.
- Use Linux and FRR (vtysh) commands instead of NVUE for **all** switch configuration.

Cumulus Linux 3.7, 4.3, and 4.4 continue to support NCLU. For more information, contact your NVIDIA Spectrum platform sales representative.
{{%/notice%}}
