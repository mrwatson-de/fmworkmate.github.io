---
title: Prove you are Right
strapline: Leave guesswork to the novices!
parent: Solutions to Daily Problems
nav_order: 0320
layout: default
---
{% include standard-links.md %}

- TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

**Don't leave things to chance**, don't scan through code to see if it right, **check scientifically to test for zero errors and prove you are right!**

There's no better buzz!

## import.log and [fmLogAnalyser]

Have you imported scripts into a file, or inserted some steps into a script? or pasted some fields into a table?

In these cases FileMaker writes to the `import.log` file.

However, since this is nearly unreadable  you can use [fmLogAnalyser] to check if any errors occurred.

Have you pasted something into a layout, and want to check if it has broken?

## How to port code and prove you are right

Some things in FileMaker are not easily portable, because you can only create them manually. Some things 

Here is an overview of which methods to use when porting different things:

| Thing                  | Live Methods (Best First)           | import.log | To prove you are right…                                         |
|------------------------|-------------------------------------|:----------:|-----------------------------------------------------------------|
| Custom function        | Clipboard / Import                  | Partial    | Copy back to fmCheckMate and check for breakages                |
| Table                  | Clipboard[^1]                       | Yes        | Check [fmLogAnalyser]                       |
| Field                  | Clipboard[^2]                       | Yes        | Check [fmLogAnalyser]                       |
| Table Occurrence       | Manual                              | -          | Compare TO-names with [fmDBAnalyser] and [fmTextDiff]      |
| Relationship           | Manual                              | -          | Compare relationships with [fmDBAnalyser] and [fmTextDiff] |
| Value list             | Clipboard                           | Yes        | Check [fmLogAnalyser]                       |
| Theme                  | Import (*never* clipboard[^3])      | Partial    | Check [fmLogAnalyser]                       |
| Layout                 | Manual                              | -          | Manual check only                                               |
| Layout part            | Manual                              | -          | Manual check only                                               |
| Layout object          | Clipboard                           | No         | Copy back to fmCheckMate and perform Layout Analysis            |
| Script                 | Clipboard                           | Yes        | Check [fmLogAnalyser]                       |
| Script step            | Clipboard                           | Yes        | Check [fmLogAnalyser]                       |
| Custom menu set        | Clipboard                           | No         | Copy back and compare with [fmTextDiff]        |
| Custom menu            | Clipboard                           | No         | Copy back and compare with [fmTextDiff]        |
| Custom menu item       | Clipboard                           | No         | Copy back and compare with [fmTextDiff]        |
| Account                | Manual                              | -          | Manual check only                                               |
| Privilege set          | Manual                              | -          | Manual check only                                               |
| Extended Privilege     | Manual                              | -          | Manual check in Security dialog                                 |
| File Options           | Manual                              | -          | Manual check in File Options                                    |
| Style                  | Manual                              | -          | Manual check in Theme Styles                                    |
| External Data Source   | Manual                              | -          | Manual check in Manage External Data Sources                    |
| File Reference         | Automatic / Manual                  | -          | Manual check in Manage External Data Sources                    |
| File Authorisation     | Automatic / Manual                  | -          | Manual check in Manage External Data Sources                    |
| Script Trigger         | Manual                              | -          | Manual check in Layout Setup or Object Inspector                |

[^1]: Use MrWatson's special method to transfer tables with 99.9% accuracy
[^2]: If you need to maintain internal field IDs use MrWatson's special method to undelete fields.
[^3]: Themes should not be copied via the clipboard as this issues the theme a new internal ID, breaking the updateability of the theme from the original source file. Use the import method instead to maintain updateability of the theme from your theme master file.

{% comment %}mrwMarkdownLinks{% endcomment %}
[fmDBAnalyser]: fmdbanalyser.html
[fmLogAnalyser]: fmloganalyser.html
[fmTextDiff]: fmtextdiff.html
