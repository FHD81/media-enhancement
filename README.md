# Media Enhancement

Media Enhancement improves video playback in MPC-HC on PCs with an NVIDIA RTX graphics card. It upscales video to your display with NVIDIA Video Super Resolution, can remove film grain and sharpen the picture, and can generate in-between frames for smoother motion (2×, 3×, 4× or matched to your display's refresh rate).

It works as a DirectShow filter between the video decoder and the video renderer, so MPC-HC and MPC Video Renderer stay unmodified.

Media Enhancement is an independent project. It is not affiliated with, sponsored or endorsed by NVIDIA Corporation or the MPC-HC project.

## Download

Download the installer from the [latest release](../../releases/latest). The release notes list its SHA-256 checksum.

## Requirements

- Windows 10 or Windows 11, 64-bit.
- An NVIDIA RTX graphics card with a current NVIDIA driver:
  - **Upscaling and picture effects:** RTX 20 series or newer.
  - **Frame generation:** RTX 40 or RTX 50 series.
- MPC-HC 2.8 or newer. Setup installs MPC-HC 2.8.4.49 when no MPC-HC is found.
- About 2 GB of free disk space, most of it for the NVIDIA runtime files.

## Install

1. Run the installer. Windows may show a SmartScreen warning because the installer is not code-signed. Continue only if you downloaded it from this repository's releases.
2. Setup installs Media Enhancement in Program Files, so Windows asks for administrator permission. Setup then adds the filter to MPC-HC and installs the Microsoft Visual C++ runtime if needed.
3. Open a video in MPC-HC.

## Use

The settings can be changed in three places. They all change the same settings, and most changes apply to the playing video straight away.

- **In MPC-HC:** Play › Filters › Media Enhancement. The menu also opens the settings panel.
- **Control center:** the Media Enhancement app in the Start menu. It also shows the live status of the playing video.
- **Settings window:** Media Enhancement Settings in the Start menu, for quick changes.

## Features

- **Profiles:**
  - Auto chooses Movie, TV or Anime for each video and uses the recommended levels for that kind of video.
  - Movie, TV and Anime each keep their own grain removal, upscaling, detail and sharpening levels for each video height, which you can change.
  - Off turns the picture treatment off.
- **Upscaling:** NVIDIA Video Super Resolution enlarges video to the display size. Video that is already the display size can get a detail pass instead.
- **Film grain removal and sharpening:**
  - Grain removal uses NVIDIA's effect.
  - Sharpening is the filter's own contrast-adaptive pass. It sharpens edges without halos.
- **Frame generation:** NVIDIA Video Frame Generation at 2×, 3× or 4×, matched to the display's refresh rate, or off. The quality can be Auto, High, Medium or Low, and the filter detects scene changes.
- **Automatic fit:**
  - The filter chooses the richest settings that fit a GPU time budget you can set.
  - It favours either frame rate or picture quality, as you choose.
  - It greys out settings that have no effect on your display.
- **A/B hotkey:** compares the enhanced picture with the original while the video plays.
- **Experimental options**, off by default: HDR processing, direct GPU output to MPC Video Renderer, and native D3D11 decoding.

## Limits

- HDR video plays without enhancement unless the experimental HDR processing option is on.
- Interlaced video, very small (below 480×340) or very large (above 8K) video, and odd frame sizes play without enhancement.
- Frame generation is not available on RTX 20 and RTX 30 series cards. Upscaling and the picture effects still work.
- When the NVIDIA effects cannot run, video plays without enhancement and the status line says why.

## Uninstall

Use Settings › Apps › Installed apps › Media Enhancement › Uninstall, or Uninstall Media Enhancement in the Start menu. MPC-HC stays installed unless you choose to remove it.

## Licence

You may download and use Media Enhancement free of charge. All other rights are reserved. No licence is granted to copy, modify or redistribute the program, and its source code is not published.

The installer includes third-party components under their own licences. The NVIDIA runtime libraries are included for use with Media Enhancement only. See [THIRD-PARTY-NOTICES.md](THIRD-PARTY-NOTICES.md).

NVIDIA, GeForce and RTX are trademarks or registered trademarks of NVIDIA Corporation in the United States and other countries. Other product names are trademarks of their owners.
