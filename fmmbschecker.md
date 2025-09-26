---
title: fmMBSChecker
strapline: What version do I need?
parent: More Utilities
nav_order: 0050
layout: default
---
- TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

{% capture explanation %}
FileMaker code in.

↓

![fmMBSChecker](fmmbschecker.png){: .w-128}

↓

Min. MBS version out.
{% endcapture %}<section>{{ explanation | markdownify }}</section>{: .side-note .text-center}

This little utility helps you find out which version of MBS Plugin you need for your code - and it's pretty flexible!

## What Version of MBS does this code need?

You can feed it

- a single `MBS ( "function" )` call
- an entire calculation
- a whole script text, for example copied straight from the [MBS website](https://www.mbsplugins.eu/XLBookAddConditionalFormat.shtml)

![fmMBSChecker Screenshot of the MBS minimum Version analysis](/assets/images/fmmbschecker-screenshot.png)

You can even feed it…

- script clipboard XML
  - just copy the scripts you want to check
  - the insert button will automatically convert to XML for you
- a dump of the *entire* database
  - as Save as XML
  - or as DDR

Yes! You can discover the minimum MBS version *for an entire solution* in moments!

### What MBS functions are used in this code?

Click the little (i) button.

### Are the MBS functions compatible with my OS?

Incompatible functions are shown in the list in red.

## MBS Functions List

fmMBSChecker also has a neat list of all MBS functions and the versions they were introduced in, including popup help and links to the documentation.

![fmMBSChecker Screenshot of the MBS functions list](/assets/images/fmmbschecker-mbs-functions-screenshot.png)

### Get + Check MBS function documentation in-app

An now you can instantly copy and check MBS example code from the MBS website in 3 clicks

![Check example code directly from popover MBS function documentation](/assets/images/fmmbschecker-mbs-functions-analyse-code-from-docs.png)

### Update now

Plus there's an [Update now] button to update the list automatically from the MBS website, giving you access to the new functions as soon as a new version is released.

😎 nice!
