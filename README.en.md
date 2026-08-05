<div align="center">
  <img src="src/Lcsc2Ad.App/Assets/Crdito.png" width="104" alt="CRDITO Logo">
  <h1>CRDITO</h1>
  <p><strong>A component-library bridge between JLC / LCSC and Altium Designer</strong></p>
  <p>Search, validate, preview, export, and place components directly into Altium Designer.</p>
  <p>
    <a href="README.md">简体中文</a> · English · <a href="README.ja.md">日本語</a>
  </p>
  <p>
    <a href="https://github.com/AROLLCHEN/CRDITO-Releases/releases/latest"><img src="https://img.shields.io/github/v/release/AROLLCHEN/CRDITO-Releases?display_name=tag&style=flat-square&color=0969da" alt="Latest release"></a>
    <a href="https://github.com/AROLLCHEN/CRDITO-Releases/releases"><img src="https://img.shields.io/github/downloads/AROLLCHEN/CRDITO-Releases/total?style=flat-square&color=1f883d" alt="Downloads"></a>
    <img src="https://img.shields.io/badge/Windows-10%20%7C%2011-0078d4?style=flat-square" alt="Windows 10/11">
    <img src="https://img.shields.io/badge/Altium-22%20%7C%2026-a35c00?style=flat-square" alt="Altium Designer 22/26">
    <img src="https://img.shields.io/badge/license-Proprietary-555?style=flat-square" alt="Proprietary license">
  </p>
  <p>
    <a href="https://github.com/AROLLCHEN/CRDITO-Releases/releases/download/v1.0.9/CRDITO-Setup-1.0.9-win-x64.exe"><strong>Download CRDITO 1.0.9</strong></a>
    ·
    <a href="https://github.com/AROLLCHEN/CRDITO-Releases/releases/latest">Release notes</a>
  </p>
</div>

---

CRDITO is a Windows desktop tool for electronics design workflows. It converts JLC / LCSC component data into validated Altium Designer schematic and PCB libraries, with previews for symbols, footprints, and STEP 3D models.

## Preview

<p align="center">
  <img src="docs/images/online-schematic-preview.png" width="92%" alt="CRDITO schematic preview">
</p>

<table>
  <tr>
    <td width="50%" align="center">
      <img src="docs/images/online-footprint-preview.png" alt="CRDITO PCB footprint preview"><br>
      <sub>PCB footprint and pad preview</sub>
    </td>
    <td width="50%" align="center">
      <img src="docs/images/online-3d-preview-gpu.png" alt="CRDITO 3D model preview"><br>
      <sub>GPU-accelerated STEP 3D preview</sub>
    </td>
  </tr>
</table>

## Highlights

| Capability | Details |
| --- | --- |
| Component search | Search by LCSC part number, MPN, keyword, or package with incremental loading and local caching |
| Consistent preview | Render symbols, PCB footprints, and 3D models with the same conversion rules used for export |
| Native library export | Generate `.SchLib`, `.PcbLib`, STEP, and machine-readable validation reports without launching AD |
| Direct placement | Create a placement task in CRDITO and place it on the active AD schematic with a linked unified footprint library |
| Strict validation | Check pins, pads, slots, custom pads, multi-unit symbols, model mapping, and binary library readback |
| Responsive inspection | Four-view layout, smooth zoom, measurement tools, camera presets, and cached meshes for large STEP files |

## Quick start

1. Download and install the latest build from [Releases](https://github.com/AROLLCHEN/CRDITO-Releases/releases/latest).
2. Search for a component and inspect its schematic, PCB footprint, and 3D views.
3. Export standalone libraries, or choose **Place in AD** to start the Altium Designer placement workflow.

The installer targets Windows 10/11 x64 and bundles .NET, NPNP, OCC, the VC++ runtime, and the AD placement extension. You can choose the installation directory; administrator privileges are required. Altium Designer and its commercial license are not included.

> Search, preview, and standalone export work without Altium Designer. Direct placement and PCB updates require a compatible Altium Designer installation.

## Output

```text
Component data
├── Altium schematic library (.SchLib)
├── Altium PCB library (.PcbLib)
├── STEP 3D model (.step)
└── Validation report (.validation.json)
```

Before publishing a library, CRDITO independently reads the generated binary files back. Export is blocked when pins are missing, identifiers are duplicated, pin-to-pad mappings disagree, or geometry validation fails.

## More information

- [Versions and release notes](https://github.com/AROLLCHEN/CRDITO-Releases/releases)
- [Issue tracker](https://github.com/AROLLCHEN/CRDITO-Releases/issues)
- [Software license](LICENSE)
- [Third-party notices](docs/THIRD-PARTY-NOTICES.md)

## Data, trademarks, and license

Online component data is fetched only in response to explicit user searches. CRDITO does not perform unattended bulk crawling or bypass login and CAPTCHA controls. Users must comply with the terms of JLC, LCSC, EasyEDA, Altium Designer, and the relevant content owners.

CRDITO is an independent interoperability tool and is not affiliated with, sponsored by, or endorsed by those companies. CRDITO is proprietary software. Copyright © 2026 AROLLCHEN. See [LICENSE](LICENSE) for the complete terms. The source repository remains private; official installers and update metadata are distributed only through the public [CRDITO-Releases](https://github.com/AROLLCHEN/CRDITO-Releases) repository.

<p align="right"><a href="#crdito">Back to top</a></p>
