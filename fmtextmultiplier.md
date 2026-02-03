---
title: fmTextMultiplier
strapline: Multiplies your productivity
parent: Text Tools
nav_order: 5
layout: default
---
- TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

{: .note}
Need  the same code for a whole bunch of fields?

Just programme for the first one, then copy the fields you want to multiply - starting with the one field - and let fmTextMultiplier do the rest for you.



Say you are resetting some fields in a date picker:

    Set Field [ _DatePicker_::MonthDay01 ; "" ]

You've got 46 fields to reset, one for each day of the month. You could write out all 46 lines of code manually,

{: .note}
but that's tedious and error-prone.

Instead, you can use fmTextMultiplier to generate the code for you.

Just multiply the above code by a list of the field suffixes:

    Day01
    Day02
    Day03
    Day04
    :
    Day43
    Day44
    Day45
    Day46


et voilá! 

fmTextMate will give you:

    Set Field [ _DatePicker_::MonthDay01 ; "" ]
    Set Field [ _DatePicker_::MonthDay02 ; "" ]
    Set Field [ _DatePicker_::MonthDay03 ; "" ]
    Set Field [ _DatePicker_::MonthDay04 ; "" ]
    :
    Set Field [ _DatePicker_::MonthDay43 ; "" ]
    Set Field [ _DatePicker_::MonthDay44 ; "" ]
    Set Field [ _DatePicker_::MonthDay45 ; "" ]
    Set Field [ _DatePicker_::MonthDay46 ; "" ]


- fmTextMultiplier is a neat way of 'multiplying up your code'
- fmTextMultiplier is not much mre than a wrapper for the Substitute function, but it generates a result for *each* substitution rather than applying each substitution sequentially to the same text.

## Use fmTextMultiplier together with fmTextSeries

What's more, you can use it in combination with fmTextSeries to generate the list of suffixes instantly.

For example, to generate the list of suffixes Day01 to Day31, just use:

1. Open fmTextSeries
2. Click `[New]`or press <kbd>CMD</kbd><kbd>2</kbd> to start a new series
3. Enter `Day1` in the first `Text` field
4. Enter `46` in the second `Times` field
5. Leave the `1`in third `Increment` field
6. Press ÒK`

This generates a list with 46 entries, with each line incrermented by 1:

    Day01
    Day02
    Day03
    :
    Day44
    Day45
    Day46

## How to use fmTextMultiplier