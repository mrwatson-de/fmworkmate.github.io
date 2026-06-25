---
title: fmJAML
strapline: Code from your keyboard
parent: fmIDE
nav_order: 100
layout: default
github_repo: https://github.com/fmIDE/fmJAML
github_latest: https://github.com/fmIDE/fmJAML/releases/latest
---
[![Get me on Github](/assets/images/get-me-on-github.png){: .mrw-github-corner}]({{page.github_latest}})

- TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

{: .side-note}
fmJAML is  
in development  
but coming  
**VERY SOON**  
C U @  
Vienna Calling

# {{page.title}}

{{page.strapline}}

fmJAML is a compact templating language for JSON in FileMaker.

fmJAML is used in fmIDE to write fmIDE Action Scripts - literally [fmJAML Code from your Keyboard]

## Example 1

This fmJAML

```javascript
[+].fmJAML
[:]..name[+] = "FileMaker JaSON Markdown Language"
[:].       ] = "FileMaker JSON A Markdown Language"
[:].       ] = "FileMaker JSON As a Markdown Language"
[:]..date_of_inspiration = ;D; Date ( 3 ; 10 ; 2026 )
[:]..days_old = ;N; Get( CurrentDate ) - Date ( 3 ; 10 ; 2026 )
[:]..implementation_count = ;N; 1
#
# supports 'heredocs' to avoid escaping code:
[:]..text_logo= ===
    __                _         __  __ _
   / _|              | |  /\   |  \/  | |
  | |_ _ __ ___      | | /  \  | \  / | |
  |  _| '_ ` _ \ _   | |/ /\ \ | |\/| | |
  | | | | | | | | |__| / ____ \| |  | | |____
  |_| |_| |_| |_|\____/_/    \_\_|  |_|______|
===
```

produces this JSON (on May 20th, 2026)

```json
[
  {
    "fmJAML" : 
    {
      "date_of_inspiration" : "2026-03-10",
      "days_old" : 71,
      "implementation_count" : 1,
      "name" : 
      [
        "FileMaker JaSON Markdown Language",
        "FileMaker JSON A Markdown Language",
        "FileMaker JSON As a Markdown Language"
      ],
      "text_logo" : "    __                _         __  __ _\r   / _|              | |  /\\   |  \\/  | |\r  | |_ _ __ ___      | | /  \\  | \\  / | |\r  |  _| '_ ` _ \\ _   | |/ /\\ \\ | |\\/| | |\r  | | | | | | | | |__| / ____ \\| |  | | |____\r  |_| |_| |_| |_|\\____/_/    \\_\\_|  |_|______|"
    }
  }
]
```

## Example 2

Here are some more examples:

```javascript
[+].examples
#
# data types (T,N,B,D,I,M,R,O,A,J,U)
[:]..1_data_types
[:]...number  = ;N; "123"
[:]...date    = ;D; Get ( CurrentDate )
[:]...boolean = ;B; 1=2
#
# optional operator (`?`=drop, if value is empty)
[:]..2_optional
[:]...drop_empty_number = ;N?; $number
[:]...drop_junk_number  = ;N?; "dfg"
[:]...keep_number       = ;N?; 42
#
# trim operator (`*`=trim)
[:]..3_trim
[:]...spaces              = ;*;     "  spaces trimmed  "
[:]...horizontal          = ;**;    Char(9)&" tabs too "
[:]...vertical            = ;***;   Char(9)&"¶ trim WS ¶¶"
[:]...compact_json_string = ;****;  "¶{ \"a\":1 } ¶  "
[:]...format_json_string  = ;*****; "¶{ \"a\":1 } ¶  "
#
# …not operator (`!'0'`=empty, if the value = "0")
[:]..4_not_op
[:]...non_zero_number_drop_empty=;N!'0'?;""
[:]...non_zero_number_drop_zero=;N!'0'?;0
[:]...non_zero_number_keep=;N!'0'?;42
#
# EOL operator
[:]..5_eol_op
[:]...no_where        = ;¶'';  "no¶where"
[:]...convert_to_list = ;¶','; "a¶b¶c"
[:]...crs_only_please = ;¶'¶'; "a"&Char(10)&"b¶c"
[:]...first_line_only = ;¶1;   "first¶line¶only"
#
# Map operator
[:]..map_de_en  = ;!'ja'-'yes':!'nein'-'no'; "nein"
```

produces the following JSON

```json
[
  {
    "examples" : 
    {
      "1_data_types" : 
      {
        "boolean" : false,
        "date" : "2026-05-20",
        "number" : 123
      },
      "2_optional" : 
      {
        "keep_number" : 42
      },
      "3_trim" : 
      {
        "compact_json_string" : "{\"a\":1}",
        "format_json_string" : "{\r\t\"a\" : 1\r}",
        "horizontal" : "tabs too",
        "spaces" : "spaces trimmed",
        "vertical" : "trim WS"
      },
      "4_not_op" : 
      {
        "non_zero_number_keep" : 42
      },
      "5_eol_op" : 
      {
        "convert_to_list" : "a,b,c",
        "crs_only_please" : "a\rb\rc",
        "first_line_only" : "first",
        "no_where" : "nowhere"
      },
      "map_de_en" : "no"
    }
  }
]
```

{% comment %}mrwMarkdownLinks{% endcomment %}
[fmJAML Code from your Keyboard]: fmjaml-code-from-your-keyboard.html
