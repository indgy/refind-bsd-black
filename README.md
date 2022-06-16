# rEFInd BSD Black

![Simulated screenshot of the theme](screenshot.png)


A mash-up of various black rEFInd themes to include the BSD OS icons.

If anything is missing let me know where to find it or submit a PR.

## Installation

**Note:** The following guide assumes your EFI partition is located at ada0p1 and your refind.conf is in the efi/boot folder.

Mount your existing EFI partition

```
mount -t msdosfs /dev/ada0p1 /mnt
```


Now either follow the Git or Release install.


### Using Git

Make the theme folder if necessary then clone this repository into the rEFInd themes folder.

```sh
mkdir /mnt/efi/boot/themes
git clone https://github.com/indgy/refind-bsd-black /mnt/efi/boot/themes
```


### Using the release

Make the theme folder if necessary, then fetch the latest release and extract into the rEFInd themes folder.

```sh
mkdir -p /mnt/efi/boot/themes/refind-bsd-black
cd /mnt/efi/boot/themes/refind-bsd-black
fetch https://github.com/indgy/refind-bsd-black/releases/download/0.1.0/refind-bsd-black.tgz
tar -xf 0.1.0.tar.gz
rm 0.1.0.tar.gz
```


## Configuring refind.conf

Edit your `refind.conf` to reference the theme (assuming your refind folder is named boot)

`edit /mnt/efi/boot/refind.conf`

It should contain a single include line:

`include themes/refind-bsd-black/theme.conf`

Anything you add after the include line will override the theme defaults.


### Example refind.conf

Sometimes you need to tell rEFInd which icon to use.

```sh
menuentry "DragonFlyBSD" {
    loader efi/dragonflybsd/loader.efi
    icon efi/boot/themes/refind-bsd-black/icons/os_dragonflybsd.png
}
menuentry "FreeBSD" {
    loader efi/freebsd/loader.efi
    icon efi/boot/themes/refind-bsd-black/icons/os_freebsd.png
}
menuentry "OpenBSD" {
    loader efi/openbsd/bootx64.efi
    icon efi/boot/themes/refind-bsd-black/icons/os_openbsd.png
}
menuentry "Windows" {
    loader efi/Microsoft/Boot/bootmgr.efi
}
```

Note the icon for Windows is found automatically by rEFInd.


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