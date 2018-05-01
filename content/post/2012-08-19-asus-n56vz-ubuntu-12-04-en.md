---
author: minko_gechev
categories:
- Linux
- Ubuntu
date: 2012-08-19T00:00:00Z
tags:
- asus n56vz
- linux
- ubuntu
title: Asus N56VZ + Ubuntu 12.04 (en)
url: /2012/08/19/asus-n56vz-ubuntu-12-04-en/
---

[<img class="alignright size-medium wp-image-156" title="Asus N56VZ + Ubuntu 12.04" src="/images/legacy/uploads2012/08/UNSET1-300x225.jpg" alt="" width="300" height="225" />][1]It seems that it’s common a problem to setup Ubuntu on the new Asus N56VZ so I decided to create an English version of <a href="https://blog.mgechev.com/2012/07/22/asus-n56vz-ubuntu-12-04/" target="_blank">my post</a>.  
I was struggling with three issues about two weeks. Here are they:

1.  Multimedia buttons (Fn+F*)
2.  Subwoofer
3.  Ethernet adapter

I’ll start with the Subwoofer issue because it’s with the easiest fix. Adding **options snd-hda-intel model=asus-mode4 **at the end of <strong id="internal-source-marker_0.20856572198681533"> /etc/modprobe.d/<strong id="internal-source-marker_0.20856572198681533">alsa-base.conf </strong> </strong>will solve the problem.

For enabling the ethernet adapter you have to install **compat-wireless-2012-03-12-p** from<a title="http://www.orbit-lab.org/kernel/compat-wireless/2012/03/" href="http://www.orbit-lab.org/kernel/compat-wireless/2012/03/" target="_blank"> http://www.orbit-lab.org/kernel/compat-wireless/2012/03/</a>. The installation is straight-forward:

\# ./scripts/driver-select alx

\# make

\# make install

\# modprobe alx

And the last one (and most painful...) – multimedia buttons. Actually the problem wasn’t so hard if you know the solution (as usual)... You just have to update your kernel to version 3.5+ and install the patch - <a title="https://www.dropbox.com/s/0kd3p8lb9wg8xqi/asus-wmi-dkms_0.2_all.deb" href="https://www.dropbox.com/s/0kd3p8lb9wg8xqi/asus-wmi-dkms_0.2_all.deb" target="_blank">https://www.dropbox.com/s/0kd3p8lb9wg8xqi/asus-wmi-dkms_0.2_all.deb</a>. Updating the BIOS is not necessary.

 [1]: /images/legacy/uploads2012/08/UNSET1.jpg