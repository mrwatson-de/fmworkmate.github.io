---
title: fmSimpleCalculator
strapline: 1+2 Quick & Dirty
parent: More Utilities
nav_order: 0400
layout: default
---
- TOC
{:toc}

{% include page-image.html width=site.page_image_width %}

# {{page.title}}

{{page.strapline}}

fmSimpleCalculator is a tiny utility that lets you do quick calculations right inside FileMaker.

## Open fmSimpleCalculator

In [fmWorkMate]

- scroll down and select the [fmSimpleCalculator] tool
- or just press <kbd>CMD</kbd><kbd>SHIFT</kbd><kbd>=</kbd>

In the dialog that appears you can type in your calculation.

Try some of these one-liner examples:

    _0x("FEFF") // → 65279 (convert hexadecimal to decimal)
    _Hex(15) // → "F" (convert decimal to hexadecimal)
    _HexF ( "0000" ; 15 ) // → "000F" (output formatted hexadecimal)
    _Ux( "25B9" ) // "▹" (output character corresponding to hexadecimal unicode point)

or these

    _0o("17") // → 15 (convert octal to decimal)
    _0b("1111") // → 15 (convert binary to decimal)
    _HexRGB ( 0 ; 255  ; 0 ) // → "00FF00" (green)
    _Octal ( 255 ) // → 377 (decimal)


    f // calls up the function list.

Of course it supports standard calculations too:

    sqrt(144) // -> 12
    5! // -> 120 (factorial)
    sin(30) // -> 0.5 (sine of 30 degrees)
    log(100) // -> 2 (base 10 logarithm)
    ln(2.718281828459) // -> 1 (natural logarithm)
    abs(-42) // -> 42 (absolute value)
    round(3.14159, 2) // -> 3.14 (rounded to 2 decimal places)
    pow(2, 8) // -> 256 (2 raised to the power of 8)
    max(10, 20, 5) // -> 20 (maximum value)
    min(10, 20, 5) // -> 5 (minimum value)

