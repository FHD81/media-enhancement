# Third-party notices

The Media Enhancement installer contains or installs the software below. Each component keeps its own licence.

## NVIDIA Video Effects SDK runtime 1.3

- **What:** runtime libraries and models of the NVIDIA Video Effects SDK 1.3.0, used for Video Super Resolution and Video Frame Generation.
- **Licence:** the NVIDIA Software License Agreement, the Product-Specific Terms for NVIDIA AI Products and the NVIDIA Open Model License Agreement. Setup installs these documents with the runtime, in the `VideoFX\license` folder of the installation.
- **Models:** Licensed by NVIDIA Corporation under the NVIDIA Open Model License.
- **The runtime's own third-party licences:** in `VideoFX\bin\ThirdPartyLicenses.txt`, which Setup installs with the runtime.
- The runtime libraries are distributed as part of Media Enhancement, for use with it only.
- Copyright © NVIDIA Corporation. All rights reserved.

## MPC-HC 2.8.4.49

- **What:** the unmodified MPC-HC installer. Setup runs it only when MPC-HC is missing, or when you choose to update it.
- **Licence:** GNU General Public License, version 3. The licence text is installed with MPC-HC.
- **Source code:** <https://github.com/clsid2/mpc-hc>. This build is published in the release tagged 2.8.4.17: <https://github.com/clsid2/mpc-hc/releases/tag/2.8.4.17>.
- **Relationship:** Media Enhancement contains no MPC-HC code. MPC-HC loads it as an external DirectShow filter.

## Microsoft Visual C++ Redistributable (x64)

- **What:** the unmodified Microsoft Visual C++ runtime installer, version 14.40 or newer. The NVIDIA runtime files need it. Setup runs it only when the runtime is missing or older.
- **Licence:** Microsoft's licence terms for the Visual C++ runtime. Its installer shows them when it runs on its own, but Setup runs it silently. Microsoft's download page: <https://learn.microsoft.com/cpp/windows/latest-supported-vc-redist>.

## Microsoft DirectShow base classes

- **What:** the DirectShow base classes from Microsoft's Windows classic samples, compiled unmodified into the Media Enhancement filter (`MediaEnhancement.ax`):
  - Repository: <https://github.com/microsoft/Windows-classic-samples>
  - Folder: `Samples/Win7Samples/multimedia/directshow/baseclasses`
  - Commit: `434f6002bdf9cf9829406c3ff2b33387982d6168`
- **Licence:** MIT, reproduced here:

```
The MIT License (MIT)

Copyright (c) Microsoft Corporation

Permission is hereby granted, free of charge, to any person obtaining a copy
 of this software and associated documentation files (the "Software"), to deal
 in the Software without restriction, including without limitation the rights
 to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
 copies of the Software, and to permit persons to whom the Software is
 furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
 all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
 IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
 FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
 AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
 LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
 OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
 THE SOFTWARE.
```

## Method credit

Media Enhancement's sharpening pass follows the contrast-adaptive sharpening method that AMD published as FidelityFX CAS. The implementation is Media Enhancement's own.
