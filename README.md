# ooiptables: Sovereign IPTABLES SHIM

<div align="center">

```
================================================================================
                                ooiptables
               Sovereign openOODA IPTABLES SHIM
================================================================================
```

**Sovereign IPTABLES SHIM**  
*Compatibility shim translating iptables commands into openOODA nftables rules.*  
*Two Faces, One Engine:* Modern terminal ergonomics for humans • Zero-leakage MCP for AI agents  
Written in 100% pure [openOODA](https://github.com/openOODA).

[![License: Apache-2.0](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![openOODA](https://img.shields.io/badge/openOODA-1.0-emerald.svg)](https://openooda.org)
[![Architecture: x86_64 | aarch64](https://img.shields.io/badge/Arch-x86__64%20%7C%20aarch64-lightgrey.svg)]()

</div>

---

## 1. Quick Install

### Automated Installer (Linux x86_64 & aarch64)
```bash
curl -fsSL https://openooda-tools.github.io/ooiptables/install.sh | bash
```

### Native Package Managers
```bash
# Arch Linux (AUR / PKGBUILD)
yay -S ooiptables-bin
# Or manual PKGBUILD:
cd packaging/arch && makepkg -si

# Debian / Ubuntu (.deb)
curl -fsSL https://openooda-tools.github.io/ooiptables/install.sh | bash -s -- --deb

# Fedora / RHEL (.rpm)
curl -fsSL https://openooda-tools.github.io/ooiptables/install.sh | bash -s -- --rpm
```

### Uninstallation
```bash
ooiptables-uninstall
# or: curl -fsSL https://openooda-tools.github.io/ooiptables/uninstall.sh | bash
```

---

## 2. CLI Usage

```
usage: ooiptables [options] [ARGUMENTS]...

Compatibility shim translating iptables commands into openOODA nftables rules.

Options:
  -h, --help           display this help and exit
  -v, --version        output version information and exit
      --json           output formatted as JSON Lines
      --color <WHEN>   colorize output: auto, always, never [default: auto]
      --theme <NAME>   override active oote palette
      --mcp            run as Model Context Protocol stdio server
```

---

## 3. Theming Integration (`oote`)

`ooiptables` synchronizes visual styles and status colors with [oote](https://github.com/openOODA-tools/oote):
* **Configuration:** Reads active palette from `~/.openooda/theme.oot`.
* **Environment Overrides:** Respects `$OODA_THEME` and `$NO_COLOR`.

---

## 4. Model Context Protocol (MCP)

When invoked with `--mcp`, `ooiptables` runs a JSON-RPC 2.0 stdio server providing structured tools for AI coding agents:

```bash
ooiptables --mcp
```

---

## 5. Security & Zero Ambient Authority

* **Pure Capability Bounded:** Operates strictly with explicit tokens (&NetCap, &TlsCap, &McpCap). Physical absence of ambient disk/net leakage.
* **Negative-Trust Architecture:** Strict input validation and operational limits.
* **Hermetic Binary:** Standalone zero-dependency executable.

---

## 6. License

Apache License, Version 2.0. See [LICENSE](LICENSE) for details.
