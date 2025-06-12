---
title: Create Multiple FileMaker Apps on Mac OS
strapline: Ooooooh nice!
parent: fmLaunchPad
nav_order: 100
layout: default
---
1. TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

{: .under-construction}
This page is under construction!

![Mac only](/assets/images/mac.png){: .float-front-right .w-32}

Did you know that on Mac OS you can not only have multiple versions of FileMaker installed on your computer, but also multiple instances of the same version?

Just duplicate, rename and re-iconise the FileMaker app, and you can have multiple beautiful FileMaker based apps in your dock:

![Multiple FileMaker Apps using fmLaunchPad](/assets/images/fmlaunchpad-multiple-filemaker-apps.png)

## How to Create a FileMaker App on Mac OS

Here is how to create a FileMaker App, using the `MrWatson in the Table of Doom` App as an example

### 1. Duplicate the FileMaker App

- Select your standard FileMaker app in the Finder
- Duplicate it <kbd>⌘D</kbd>

### 2. Rename the App

- Press <kbd>⏎</kbd> and give it a new, unique, zingy, iconic name
- and, if you need to group it with some app FileMaker files, put it in a new folder of the same name and throw in the app's FileMaker files

### 3. Re-iconise the App

- Create a new icon for your FileMaker app
- Select the FileMaker app
- Show the Information window <kbd>⌘I</kbd> or right click and select 'Get Info'
- Drag your new icon to the file icon at the top left of the Get Info window

### 4. Setup fmLaunchPad to handle your app

- Open fmLaunchPad
- Change to List view
- Add a new module
  - easiest by duplicating and editing an existing module
- Edit the trigger condition to recognise your app
  - For example: `"MrWatson in the Table of Doom" = fmAppName`
    - Note: I tend to put the name before the `=` sign, since this acts better as a title for the section
  - There are a few Custom Functions you can use to make it easier…
    - fmAppName,  fmAppFolder
    - See the (?) button in fmLaunchPad for more information
- Change the type of the module to `Launch App File`
  - This will open a file relative to the location of the app file

  ![fmLaunchpad long](/assets/images/fmlaunchpad-long.png)

- Type the name of the file to start
  - no `.fmp12` extension needed
  - if the file is in a subfolder then use `«foldername»/«filename»`
- Change the name of the module displayed on the module wall
  - The field accepts two lines
  - the first line is the name for the left wall
  - the second line is the name for the right wall
- In the Settings popup you can choose [X] Capsule Mission

Voilá! Your new FileMaker app is ready to go!
