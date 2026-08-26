# Prebuilt binary - Microsoft.Wpf.Interop.DirectX (x64)

This is a checked-in **x64** build of `Microsoft.Wpf.Interop.DirectX.dll`
(the `D3D11Image` WPF-Direct3D interop assembly), vendored so consumers can
reference it without needing the C++/CLI toolchain.

## How it was built

- Source: this repository, `src/Microsoft.Wpf.Interop.DirectX/Microsoft.Wpf.Interop.DirectX_winsdk.vcxproj`
- Configuration / Platform: **Release / x64**
- Built against Windows SDK `10.0.26100.0`, passed as an override rather than
  the `10.0.22621.0` the project declares. The project file is unchanged.
- Command:
  ```
  msbuild src\Microsoft.Wpf.Interop.DirectX\Microsoft.Wpf.Interop.DirectX_winsdk.vcxproj ^
    -p:Configuration=Release -p:Platform=x64 -p:WindowsTargetPlatformVersion=10.0.26100.0
  ```

## Properties

- PE: PE32+ / x86-64, mixed-mode managed assembly (`/clr`)
- Assembly: `Microsoft.Wpf.Interop.DirectX`
- Requires the Visual C++ 2015-2022 runtime (x64) at runtime.

To rebuild after changing the source, run the command above and copy the
resulting `x64\Release\Microsoft.Wpf.Interop.DirectX.dll` (and `.pdb`) over the files here.