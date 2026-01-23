---
title: Install fmWorkMate
strapline: Installation - duh
parent: fmWorkMate
github_latest: https://github.com/mrwatson-de/fmWorkMate/releases/latest
nav_order: 01
layout: default
---
- TOC
{:toc}

{% include page-image.html width="500" %}

# {{page.title}}

There are different versions of fmWorkMate available, depending on your operating system.

fmWorkMate is designed primarily for macOS - where the MBS Plugin can work its integration wonders - and is extensively tested there.

For Windows there is an older runtime version available.

![Mac](assets/images/mac.png){: .float-front-right .w-48}

## Install the latest version on a Mac

To install fmWorkMate, simply

![fmWorkMate](fmworkmate.png){: .float-front-right .w-48}

1. Download the [latest release of fmWorkMate]({{page.github_latest}})
2. Unzip the archive
   - Note: If instead of using the latest release you have downloaded the latest code from the main repo using `Code > Download ZIP`, you will need to rename the `fmWorkMate-main` folder to just `fmWorkMate`
3. Move the `fmWorkMate` folder to your `Applications` folder (or wherever you like to keep your apps)
4. Double-click the `fmWorkMate.fmp12` file to launch fmWorkMate in FileMaker Pro

![Windows](assets/images/win.png){: .float-front-right .w-48}

## Install the archive runtime version on Windows

On windows there are two options:

1. **If you don't need the full functionality of the latest fmWorkmate** and just want to get the job done quickly, install the [old Windows runtime version of fmWorkMate](#old-windows-runtime-version-of-fmworkmate)
2. **If you want to use the latest version of fmWorkMate** with as much functionality as possible (and are willing to help test and report issues), [install the latest macOS version of fmWorkMate](#install-the-latest-version-on-a-mac) and run it in FileMaker Pro for Windows (some features may not work as expected)

{:.note}
Please help me get fmWorkMate working on windows properly by reporting any issues you find on the [GitHub Issues page](https://github.com/mrwatson-de/fmWorkMate/issues), thank you!

![fmWorkMate Runtime](assets/images/fmworkmate-runtime.png){: .float-front-right .w-48}

### Old Windows runtime version of fmWorkMate

This version has more limited functionality, is no longer actively maintained, but is still available for download.

To install the old fmWorkMate Windows version:

1. Download the fmWorkMate Windows runtime version from the [Archive Windows Runtime Version on GitHub](https://github.com/mrwatson-de/fmWorkMate-Archive-Win)
   - Click `Code` > `Download ZIP`
2. Unzip the `fmWorkMate-Archive-Win-master.zip` archive
3. Unzip the `fmWorkMate_Win_20140113.zip` archive it contains
4. Move the `fmWorkMate` folder to your preferred location, such as to `Program Files`
5. Double-click the `fmWorkMate.exe` file to fmWorkMate
6. Right Click the fmWorkMate tab in the windows task bar and select `Pin to taskbar` for easy access in the future.
