# Third-party notices

The Media Enhancement installer contains or installs the software below, and the browser extension contains the code listed at the end. Each component keeps its own licence.

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

## Browser extension: AMD FidelityFX Super Resolution 1 (RCAS)

- **What:** the extension's sharpening pass is a port of RCAS from AMD's `ffx_fsr1.h`.
- **Licence:** MIT, reproduced here:

```
Copyright (c) 2021 Advanced Micro Devices, Inc. All rights reserved.

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and
associated documentation files (the "Software"), to deal in the Software without restriction,
including without limitation the rights to use, copy, modify, merge, publish, distribute,
sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or
substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT
NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM,
DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT
OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
```

## Browser extension: Catmull-Rom sampling in nine taps (Matt Pettineo)

- **What:** the extension's enlargement samples with Catmull-Rom weights from nine bilinear taps; the function is a port of `SampleTextureCatmullRom` by Matt Pettineo (MJP): <https://gist.github.com/TheRealMJP/c83b8c0f46b63f3a88a5986f4fa982b1>.
- **Licence:** MIT, the licence of all of the author's public gists (<https://gist.github.com/TheRealMJP/bc503b0b87b643d3505d41eab8b332ae>), reproduced here:

```
Copyright (c) 2019 MJP

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and
associated documentation files (the "Software"), to deal in the Software without restriction,
including without limitation the rights to use, copy, modify, merge, publish, distribute,
sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or
substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT
NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM,
DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT
OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
```

## Browser extension: OpenCV DIS optical flow

- **What:** the extension's motion estimation follows the Dense Inverse Search optical flow method (T. Kroeger, R. Timofte, D. Dai and L. Van Gool, "Fast Optical Flow using Dense Inverse Search", ECCV 2016) as OpenCV implements it (`modules/video/src/dis_flow.cpp` and `modules/video/src/opencl/dis_flow.cl`). It was written anew in WGSL and differs from the original: both flow directions in one pass, no variational refinement, flow at half resolution.
- **Copyright,** as listed in OpenCV's `COPYRIGHT` file (reproduced in `THIRD-PARTY-NOTICES.txt` inside each extension package): Intel Corporation (2000-2022); Willow Garage Inc. (2009-2011); NVIDIA Corporation (2009-2016); Advanced Micro Devices, Inc. (2010-2013); OpenCV Foundation (2015-2023); Itseez Inc. (2008-2016); Xperience AI (2019-2023); Shenzhen Institute of Artificial Intelligence and Robotics for Society (2019-2022); Southern University of Science And Technology (2022-2023); OpenCV AI (2023-2025); Bigvision LLC (2024). Third-party copyrights are property of their respective owners.
- **Licence:** OpenCV is licensed under the Apache License, Version 2.0: <https://www.apache.org/licenses/LICENSE-2.0>. The full text is in `THIRD-PARTY-NOTICES.txt` inside each extension package.
- **`dis_flow.cpp` licence header:** that file carries OpenCV's earlier 3-clause BSD licence header (Copyright (C) 2000-2008, Intel Corporation; Copyright (C) 2009, Willow Garage Inc.; third-party copyrights are property of their respective owners). The header is reproduced in full in `THIRD-PARTY-NOTICES.txt` inside each extension package.
- **Source code:** <https://github.com/opencv/opencv>.

## Picture in the README

The video in the README's browser extension picture is from *Tears of Steel*, (CC) Blender Foundation | mango.blender.org, licensed under the Creative Commons Attribution 3.0 licence: <https://creativecommons.org/licenses/by/3.0/>.
