# Orchard Hardware

Hardware support and image-building resources for Linux on Apple devices. This repository owns device descriptions, kernel patches/configuration, firmware recipes, recovery tooling and the device runtime. It does not depend on a desktop distribution or the host CLI.

## Supported hardware

Currently: iPad 6 Wi-Fi (`iPad7,5`, J71b), experimental. Boot is tethered and GPU acceleration is not available.

## Use

For installing and starting a published system, use the [Orchard CLI](https://github.com/OrchardLinux/cli). Its release requirements select compatible CLI and hardware wheels automatically.

For building components or another image, follow [BUILD.md](BUILD.md). All commands run from this repository or installed package resources; no sibling source checkout is needed.

- [Kernel producers](kernel/README.md)
- [J71b compatibility audit and validation limits](docs/j71b-compatibility-audit.md)
- [Recovery tools](boot/initramfs/recovery/README.md)
- [GitHub builds and release ordering](docs/ci.md)
- [Shared launcher build and publication](boot/quiet/README.md)
- [Device protocol](https://github.com/OrchardLinux/cli/blob/main/docs/device-protocol.md)

Public packages contain recipes and code, not private Apple firmware, calibration, device trees captured from hardware, or session credentials. Device-specific inputs are prepared separately on the user's host.


## Control an already-running Omarchy desktop from a Mac

[iPad Controls](https://github.com/micro23/ipad-controls) is a small native macOS app that supplies mouse and keyboard input after the iPad has reached its Omarchy Linux desktop. Look at the iPad for its display; click the Mac app's pad to capture input and press Escape to release it. This is useful during bring-up when native touch or attached input is unavailable.

It uses your own authenticated SSH connection and temporary Linux uinput devices. Requirements include Python 3, permission to access `/dev/uinput`, an already-running compositor, and a verified SSH host key. The tested hardware is iPad Air 2/J81 with Labwc; other devices remain unqualified. The optional System info action requires the matching Omarchy About adapter. It does not boot or install Linux.

See the [setup instructions](https://github.com/micro23/ipad-controls#configure-your-connection) and [releases](https://github.com/micro23/ipad-controls/releases). Public builds contain no owner credentials or private device data; each user configures their connection locally.

## License

See [LICENSE](LICENSE), [NOTICE](NOTICE), `LICENSES/`, and per-file SPDX identifiers for component licenses and upstream credits.
