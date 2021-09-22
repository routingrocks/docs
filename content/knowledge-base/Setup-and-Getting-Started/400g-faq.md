---
title: 400G Switches, NICs, Tranceivers and Cables - FAQ
author: NVIDIA
weight: 20
toc: 4
---

This FAQ should help you adopt and use our 400G trancievers and cables.

## What is the the differance between NRZ and PAM4 encodings?

Non-Return to Zero (NRZ) modulation scheme has two voltage levels to represent logic 0 and 1. NRZ is based on 1-bit/clock and used for 100GbE and below speeds.</br>
Pulse Amplitude Modulation 4-levels (PAM4) modulation scheme, as its name, uses four voltage levels to represent a logic combinations of 2-bits/clock - 00, 01, 10 and 11. PAM4 is used for 200GbE and above speeds to transmit traffic. PAM4 doubles the NRZ rates while keeping the same 25GHz clock and low cost connectors. 

{{<figure src="images/knowledge-base/400G-faq/pam_nrz.png">}} 

The NRZ and PAM4 signaling are not compatible with each other as they have different bit/clock ratio. To connect two sides with different modulation types, a special converter is needed. This converter is called “gearbox” and it is placed inside a transceiver or a switch system. NVIDIA offers optical transceivers which include the gearbox inside and allows these types of connection (e.g. 8x50G PAM4 to 4x100G NRZ).

**NRZ Modulation Speeds** use clockings that are multiples of 1,10 or 25G - 1GbE (1x1G), 10GbE (1x10G), 25GbE (1x25G), 40GbE (4x10G), 50GbE (2x25G), 100GbE (4x25G).
**PAM4 Modulation Speeds** - use clockings that are multiples of 50 or 100G - 200GbE (4x50G), 400GbE (8x50G or 4x100G), 800GbE (8x100G).

How to break out a 400G port  

What are the SN4000 family supported pluggables?

<table>
    <tr>
        <th>
        Transceivers, Optical Fiber and Copper Cables
        </th>
        <th>
        Interface Type
        </th>
        <th>
        Description
        </th>
        <th>
        SKU
        </th>
    </tr>
    <tr>
        <td rowspan="4" style="vertical-align : middle;text-align:center;">
        400GbE PAM4 QSFP-DD
        </td>
        <td style="vertical-align : middle">
        400BASE-CR8 copper
        </td>
        <td style="vertical-align : middle">
        0.5m-2m DAC
        </td>
        <td style="vertical-align : middle">
        MCP1660-W0xxxxx
        </td>
    </tr>
    <tr>
        <td style="vertical-align : middle">
        400BASE-SR8
        </td>
        <td style="vertical-align : middle">
        850nm, MPO16, up to 100m
        </td>
        <td style="vertical-align : middle">
        MMA1U50-WS
        </td>
    </tr>
    <tr>
        <td style="vertical-align : middle">
        400BASE-DR4
        </td>
        <td style="vertical-align : middle">
        1310nm, MPO, up to 500m
        </td>
        <td style="vertical-align : middle">
        MMS1V00-WM
        </td>
    </tr>
    <tr>
        <td style="vertical-align : middle">
        400BASE-AOC
        </td>
        <td style="vertical-align : middle">
        3m-100m
        </td>
        <td style="vertical-align : middle">
        MFA1U60-Wxxx
        </td>
    </tr>
</table>

What are the SN4000 family breakout options?
What are the possible breakout options?

<table>
    <tr>
        <th>
        Transceivers, Optical Fiber and Copper Cables
        </th>
        <th>
        Interface Type
        </th>
        <th>
        Description
        </th>
        <th>
        SKU
        </th>
    </tr>
    <tr>
        <td rowspan="4" style="vertical-align : middle;text-align:center;">
        400GbE PAM4 QSFP-DD
        </td>
        <td style="vertical-align : middle">
        400GbE to 2 x 200GbE QSFP56
        </td>
        <td style="vertical-align : middle">
        1m-2m DAC
        </td>
        <td style="vertical-align : middle">
        MCP7H60-W0xxxxx
        </td>
    </tr>
    <tr>
        <td style="vertical-align : middle">
        400GbE to 4 x 100GbE QSFP56
        </td>
        <td style="vertical-align : middle">
        1m-2m DAC
        </td>
        <td style="vertical-align : middle">
        MCP7F60-W0xxxxx
        </td>
    </tr>
    <tr>
        <td style="vertical-align : middle">
        400GbE to 4 x 100GbE SFP-DD
        </td>
        <td style="vertical-align : middle">
        1m-2m DAC
        </td>
        <td style="vertical-align : middle">
        MCP7F65-W0xxxxxx
        </td>
    </tr>
    <tr>
        <td style="vertical-align : middle">
        400GbE to 8 x 50GbE SFP56
        </td>
        <td style="vertical-align : middle">
        1m-2m DAC
        </td>
        <td style="vertical-align : middle">
        MCP7F80-W0xxxxx
        </td>
    </tr>
</table>
