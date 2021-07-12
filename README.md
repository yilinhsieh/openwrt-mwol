Mwol for (OpenWRT)
========================================

mwol is a program that uses the mqtt protocol to wake up a computer from the network to improve the user experience and security of the original wol.

Issues & Updates
----------------

Found a bug? Please create an issue on GitHub:
    https://github.com/mleaf/openwrt-mwol/issues

Further tests and PR's are welcome and appreciated.

Installation
------------

In time, Mwol may be included upstream by the OpenWRT crowd,
to have it always available, for now, please select an installation method
most suited for your case to get it:

### Adding mwol to your running OpenWRT as ipk package

#### via shell

    $ cd /tmp
    $ wget mwol_1.0.0-1_aarch64_cortex-a53_neon-vfpv4.ipk
    $ wget luci-app-wol_unknown-1_all.ipk
    $ opkg install mwol_1.0.0-1_aarch64_cortex-a53_neon-vfpv4.ipk
    $ opkg install luci-app-wol_unknown-1_all.ipk

### Adding Mwol to your own OpenWRT Build

Download mwol from github:

    # openwrt-mwol
    git clone https://github.com/yilinhsieh/openwrt-mwol  package/openwrt-mwol

Install the package:

    $ make menuconfig

Go to LuCI -> Applications select luci-app-mwol, exit, save and build as usual.

Enable the Mwol
----------------

  * Go to Services -> Mwol 
  * Choose Enable in the input checkbox

Screenshots
----------

### Luci
<p align="center">
<img 
    src="openwrt.png" 
    width="657" height="584" border="0" alt="Mwol">
</p>

## 捐赠
-------
<p align="center">
<img src="donate.png" width="397" height="528" border="0">
</p>

License
-------

This program is free software; you can redistribute it and/or
modify it under the terms of the GNU General Public License
as published by the Free Software Foundation; either version 2
of the License, or (at your option) any later version.
