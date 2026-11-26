# CachyOS Handheld Edition

Installation requires an internet connection. KDE Plasma is the only supported
desktop environment. See the [Handheld Edition installation guide](https://wiki.cachyos.org/installation/installation_handheld/).

Btrfs is the default filesystem. Installations using Btrfs and Limine get
automatic snapshots for rollback. The installer also offers `systemd-boot`.

## Features
- scx_lavd used as default scheduler - LAVD is a latency sensitive scheduler, which is intended to be used for handhelds and gaming
- Steam Deck-like Steam experience
- Gamescope Session properly implemented
- Kernel Patched to have support for Steam Deck OLED
- Steam Deck OLED Firmware included as default
- HDR correctly implemented via kernel patches
- Gaming dependencies included via `cachyos-gaming-meta`
- Support for Winesync/Fastsync/NTSync
- BBRv3 used as default
- OpenRGB Patches included
- CachyOS handheld Kernel
- CachyOS Repository (all packages compiled with avx2/avx512 including auto detection for cpu support)
- Orientation patches for several handheld devices
- Support for ROG Ally patched in the kernel
- Fixes and improvements for VRR on AMD

## Planned
- Improve the experience further to provide a Steam Deck similar experience to SteamOS
- Provide the Steam Deck Themes
- Enhance Hardware Support

## Handheld hardware
The kernel and [CHWD handheld profiles](https://github.com/CachyOS/chwd/blob/master/profiles/pci/handhelds/profiles.toml)
provide device-specific settings.
### Steam Deck
Valve's powerbuttond is used to handle power button events\
Steam is used for controller support.
### ROG Ally
steam-powerbuttond-git is used to handle power button events.\
InputPlumber is used for controller support.\
Rogue enemy is an alternative that provides power profile switching and controller support.
### Lenovo Legion
CHWD installs InputPlumber and `steamos-powerbuttond` on matching Lenovo Legion
models.

## Untested hardware
Screen orientation, audio, or controller support may need manual setup.

## Desktop PCs

On desktop PCs, switching between Gaming Mode and Desktop Mode may be
unreliable.

## Additional information

### How can I permanently boot to Desktop Mode?

The default handheld behavior starts the Gamescope session on every fresh boot.
To make the system remember the last selected session instead, run:
```
steamos-session-select persistent
```

After enabling persistent mode, switching to Desktop Mode will keep future boots
on the desktop session instead of forcing Gamescope again.

To restore the default handheld behavior, run:
```
steamos-session-select oneshot
```

With oneshot mode enabled, every fresh boot starts in the Gamescope session.

### How can I change or disable the scheduler?

See the [CachyOS scheduler guide](https://wiki.cachyos.org/configuration/sched-ext/).

## Credits
- ChimeraOS
- Ripplingsnake
- Manjaro (Phillip Müller for the base deckify package)
- Bazzite

## Maintainers
- Pogogo007 (Nekoh)
- ptr1337
