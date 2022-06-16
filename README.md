# rEFInd BSD Black

![Simulated screenshot of the theme](screenshot.png)


A mash-up of various black rEFInd themes to include the BSD OS icons and nicer version of the tools icons.

If anything is missing let me know where to find it or submit a PR.

## Installation

The following guide assumes your EFI partition is located at ada0p1 and your refind.conf is in the efi/boot folder.

Mount your existing EFI partition

`mount -t msdosfs /dev/ada0p1 /mnt`

Make the theme folder if necessary

`mkdir /mnt/efi/boot/themes`

Clone this repository onto your EFI partition

`git clone https://github.com/indgy/refind-bsd-black /mnt/efi/boot/themes`

Edit your `refind.conf` to reference the theme (assuming your refind folder is named `boot`)

`edit /mnt/efi/boot/refind.conf`

It should contain a single include line:

`include themes/refind-bsd-black/theme.conf`


You may wish to override the tools available, if so continue your config in refind.conf after the theme include.


#### Attributions:

DragonFlyBSD https://www.dragonflybsd.org/images/
FreeBSD http://seeklogo.com/freebsd-logo-273101.html
GhostBSD https://github.com/ghostbsd/ghostbsd-logo
MidnightBSD https://www.midnightbsd.org/art/
NetBSD https://netbsd.org/gallery/logos.html
NomadBSD https://github.com/nomadbsd/artwork
OpenBSD https://www.shareicon.net/openbsd-102884
Haiku butchered from https://commons.wikimedia.org/wiki/File:Haiku_(operating_system)_logo.svg

Refind theme based on
https://github.com/anthon38/refind-black
https://github.com/evanpurkhiser/rEFInd-minimal