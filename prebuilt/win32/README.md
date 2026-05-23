# Prebuilt binary — Microsoft.Wpf.Interop.DirectX (x86)

This is a checked-in **x86 (Win32)** build of `Microsoft.Wpf.Interop.DirectX.dll`
(the `D3D11Image` WPF↔Direct3D interop assembly), vendored so consumers can
reference it without needing the C++/CLI toolchain.

## How it was built

- Source: this repository, `src/Microsoft.Wpf.Interop.DirectX/Microsoft.Wpf.Interop.DirectX_winsdk.vcxproj`
- Retargeted from the original VS2015 settings:
  - `PlatformToolset`: `v140` → `v143`
  - `WindowsTargetPlatformVersion`: `8.1` → `10.0.22621.0`
  - `TargetFrameworkVersion`: `v4.5` → `v4.8`
- Configuration / Platform: **Release / Win32**
- Command:
  ```
  msbuild src\Microsoft.Wpf.Interop.DirectX\Microsoft.Wpf.Interop.DirectX_winsdk.vcxproj ^
    -p:Configuration=Release -p:Platform=Win32
  ```

## Properties

- PE: PE32 / I386 (x86), mixed-mode managed assembly (`/clr`)
- Assembly: `Microsoft.Wpf.Interop.DirectX`
- Requires the Visual C++ 2015–2022 runtime (x86) at runtime.

To rebuild after changing the source, run the command above and copy the
resulting `Release\Microsoft.Wpf.Interop.DirectX.dll` (and `.pdb`) over the files here.
