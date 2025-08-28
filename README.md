# OSD62-PM DDR Configuration
DDR configuration files for OSD62-PM. 

## Package versions
| Package | Version | 
| ------- | ------- | 
| TI SDK version | 10.10.10.04 |
| TF-A | v2.11.0 |
| U-Boot | 2024.04 | 
| Linux Kernel | v6.6.58-ti | 

# Usage
This file needs to be included in R5 SPL for DDR configuration on OSD62x-PM device. 

Location to copy this file in u-boot: **`arch/arm/dts/k3-osd62x-ddr-config-xxx.dtsi`**

It should be included in R5 SPL device tree: **`/arch/arm/dts/k3-am625-r5-<board_name>.dts`**

# Example
For OSD62-PM-BRK:
DDR include file from this repository: **`arch/arm/dts/k3-osd62x-ddr-config-800MHz.dtsi`**

R5 SPl device tree: **`/arch/arm/dts/k3-am625-r5-osd625-brk.dts`**
R5 device tree must include the DDR config file:
```
// SPDX-License-Identifier: GPL-2.0
/*
 * OSD625-PM-BRK dts file for R5 SPL
 * Copyright (C) 2025 Octavo Systems - https://www.octavosystems.com/
 */

#include "k3-am625-osd625-brk.dts"
```
**`#include "k3-osd62x-ddr-config-800MHz.dtsi"`**
```#include "k3-am62-ddr.dtsi"
#include "k3-am625-osd625-brk-u-boot.dtsi"
.
.
.
```
