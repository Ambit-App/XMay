# XMay (Xray-core Fork for Ambit)

**XMay** is the open-source network core fork of [XTLS/Xray-core](https://github.com/XTLS/Xray-core) used by the Android proxy client [Ambit](https://ambitx.org) via [AndroidXMayLite](https://github.com/Ambit-App/AndroidXMayLite).

- **Version:** `26.11.9` (`b56ffef`)
- **Upstream Base:** `XTLS/Xray-core` commit `b56ffef`
- **License:** Mozilla Public License 2.0 ([LICENSE](./LICENSE))
- **Website:** https://ambitx.org

## Modifications from Upstream XTLS/Xray-core

All modifications are isolated to [`core/core.go`](./core/core.go):

- Updated core branding and build metadata (`build = "b56ffef"`, `codename = "XMay, Penetrates Everything."`).
- Added exported `core.BuildHash() string` helper so Android bindings (`AndroidXMayLite`) can report the exact core commit hash.
- Updated `core.VersionStatement()` to identify the runtime as `XMay`.

## Building from Source

Requirements: **Go 1.27+**

```bash
git clone https://github.com/Ambit-App/XMay.git
cd XMay
go build -o xmay -trimpath -ldflags "-s -w -buildid=" ./main
```

To build the Android AAR library (`libv2ray.aar`) used by Ambit, see [Ambit-App/AndroidXMayLite](https://github.com/Ambit-App/AndroidXMayLite).

## License

This repository is licensed under the **Mozilla Public License Version 2.0 (MPL-2.0)**. See [`LICENSE`](./LICENSE) for the full license text.
