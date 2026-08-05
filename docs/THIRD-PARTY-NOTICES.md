# CRDITO third-party notices

Copyright (c) 2026 AROLLCHEN. All rights reserved for the CRDITO code and
assets, except for the third-party material identified below.

CRDITO distributes and uses the following independent components. They remain
the property of their respective authors and are licensed under their own terms.
This notice does not change, replace, or restrict those terms.

| Component | Version | License | Source / notice |
| --- | --- | --- | --- |
| Inlay.CAD.OCCT | 1.6.0 | LGPL-2.1-only | NuGet package, e-s.team |
| OCCSharp | 7.8.0-preview1 | LGPL-2.1-only | https://gitee.com/GDIKodiak/occsharp |
| Inlay.CAD / Inlay.Core | 1.6.0 | Apache-2.0 | NuGet packages, e-s.team |
| Lay.Geometrics / Lay.Graphics / Lay.Numerics | 2.0.0 / 2.0.0 / 2.0.0.1 | See note below / BSD-3-Clause / BSD-3-Clause | NuGet packages, e-s.team |
| ExtendedWPF3D | 2.0.0 | Apache-2.0 | NuGet package |
| OpenTK and OpenTK.WinForms | 4.8.2 / 4.0.0-pre.8 | MIT | https://github.com/opentk/opentk |
| OpenMcdf | 3.1.4 | MPL-2.0 | https://github.com/ironfede/openmcdf |
| OriginalCircuit.Altium / AltiumSharp | 2.0.0-alpha.1 | Apache-2.0 (upstream notice retained) | https://github.com/issus/AltiumSharp |
| Microsoft.Data.Sqlite.Core | 10.0.10 | MIT | https://github.com/dotnet/efcore |
| SQLitePCLRaw | 3.0.3 | Apache-2.0 | https://github.com/ericsink/SQLitePCL.raw |
| SQLite (via SourceGear.sqlite3) | 3.50.4.5 | Public Domain | https://sqlite.org/copyright.html |
| NPNP | bundled executable | Apache-2.0 | `external/npnp/LICENSE-APACHE` |

The packaged `OriginalCircuit.Altium` dependency is based on the upstream
AltiumSharp repository. Its Apache-2.0 license is preserved at
`vendor/packages/LICENSE-OriginalCircuit.Altium.txt` in the CRDITO source tree.

## LGPL components

`Inlay.CAD.OCCT` and `OCCSharp` are distributed as independent runtime
assemblies. They are not relicensed by CRDITO. Their license is LGPL-2.1-only;
the corresponding source and build information are available from the package
and repository locations listed above. Recipients may replace those independent
assemblies with compatible builds where technically possible, as permitted by
their license.

The installed application includes the following full license texts in
`docs/licenses`:

- `LGPL-2.1.txt`
- `MPL-2.0.txt`
- `MIT.txt`
- `BSD-3-Clause.txt`
- `Apache-2.0-OriginalCircuit.Altium.txt`
- `Apache-2.0-NPNP.txt`

`Lay.Geometrics` 2.0.0 does not declare a license expression or license file in
its NuGet package metadata. Its copyright is declared as 2024 e-s.team. It is
listed here explicitly so that no broader license is implied. Before a
commercial redistribution, obtain written license confirmation from its
copyright holder or replace it with an audited alternative.

## Service and trademark notice

LCSC, EasyEDA and Altium Designer are names and marks of their respective
owners. CRDITO is an independent tool and is not affiliated with, endorsed by,
or sponsored by those owners. Content retrieved from online services, including
component information, symbols, footprints, 3D models and datasheets, remains
subject to the applicable service and content-owner terms. Users are responsible
for confirming the rights required for their particular use and redistribution.
