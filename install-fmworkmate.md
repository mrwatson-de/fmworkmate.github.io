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

- fmWorkMate is designed primarily **for macOS** where the MBS Plugin can work its integration wonders and where it has been extensively tested through daily use.
- **For Windows** there is an older runtime version available … or …

{:.note}
Window users - please help me get fmWorkMate working on Windows properly by reporting any issues you find on the [GitHub Issues page](https://github.com/mrwatson-de/fmWorkMate/issues)

![Mac](assets/images/mac.png){: .float-front-right .w-48}

## fmWorkMate for Mac

### Install the latest version on a Mac

To install fmWorkMate, simply

![fmWorkMate](fmworkmate.png){: .float-front-right .w-48}

1. Download the [latest release of fmWorkMate]({{page.github_latest}})
2. Unzip the archive
   - Note: If instead of using the latest release you have downloaded the latest code from the main repo using `Code > Download ZIP`, you will need to rename the `fmWorkMate-main` folder to just `fmWorkMate`
3. Move the `fmWorkMate` folder to your `Applications` folder (or wherever you like to keep your apps)
4. Double-click the `fmWorkMate.fmp12` file to launch fmWorkMate in FileMaker Pro

![Windows](assets/images/win.png){: .float-front-right .w-48}

## fmWorkMate for Windows

On windows you have two options:

1. Install the Mac version,
   - use the limited functionality that works (~80% of the tasks you need daily work)
   - help me get it working properly on windows
   - report any issues you find on the [GitHub Issues page](https://github.com/mrwatson-de/fmWorkMate/issues)
   - Thank you, if you do this!
   - Go for it: [install the latest macOS version of fmWorkMate](#install-the-latest-version-on-a-mac)
2. Read on and install the old Windows runtime version of fmWorkMate
   - It is no longer actively maintained, but is still available for download.
   - Use the  limited functionality (80% of the tasks you need)
   - copy the clipboard back and forth to/from your Mac to use the full functionality.

![fmWorkMate Runtime](assets/images/fmworkmate-runtime.png){: .float-front-right .w-48}

### Install the old fmWorkMate-Archive-Win runtime version on Windows

This version has more limited functionality, is no longer actively maintained, but is still available for download.

To install the old fmWorkMate Windows version:

1. Download the fmWorkMate Windows runtime version from the [Archive Windows Runtime Version on GitHub](https://github.com/mrwatson-de/fmWorkMate-Archive-Win)
   - Click `Code` > `Download ZIP`
2. Unzip the `fmWorkMate-Archive-Win-master.zip` archive
3. Then unzip the `fmWorkMate_Win_20140113.zip` archive that it contains
4. Move the `fmWorkMate` folder to your preferred location, such as to the  `Program Files` folder (but anywhere will do).
5. Double-click the `fmWorkMate.exe` file to fmWorkMate
6. Right Click the fmWorkMate tab in the windows task bar and select `Pin to taskbar` for easy access in the future.

Once installed proceed to [Setup fmWorkMate]

{% comment %}mrwMarkdownLinks{% endcomment %}
[Setup fmWorkMate]: setup-fmworkmate.html
