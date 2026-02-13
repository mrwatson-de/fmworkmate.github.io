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

## Try it out

In the dialog that appears you can type in your (FileMaker) calculation.

fmSimpleCalculator also has some special custom functions up its sleeve

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

Of course, fmSimpleCalculator supports all the standard [FileMaker functions](https://help.claris.com/en/pro-help/content/functions-reference.html) too:

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

## Special commands

fmSimpleCalculator has a few commands you can enter

### b is for back

Enter a `b` to go back to the previous calculation.


### f is for function

If you enter just an `f` you get a menu of functions to choose from.

    1.  Number Functions…
    2.  Base Functions…
    3.  Text Functions…
    4.  Value Functions…
    5.  Word Functions…
    6.  Character Functions…
    7.  DateTime Functions…
    8.  Truth Functions…
    9.  Repeat…

Enter the number to get a submenu and choose a function.

If you prefix a value with `f:`, e.g. `f:12345`, the value is passed to the function you choose, for example, to find out what the value of the  `0xfffe` is in decimal:

    f:fffe⏎ // Prefix the value fffe with the choose function prefix f:
    2⏎ // Choose 2. Base Functions…
    2⏎ // Choose 2. Convert TO decimal…
    1⏎ // Choose 1. _0x ( "|" ) // Hex -> Dec
    _0x ( "fffe" )⏎ // Press return to calculate the function
    65534 // The answer

### h is for help

Enter just an `h` to get a small help guide.

The help guide shows several shortcuts for *even quicker conversions* 😜.

    Enter a calulation or a command and press OK, or use a shortcut:

    N ; N ; N      to convert RGB to hex.
    N ; N ; N ; N  to convert RGBA to hex.
    #NNNNNN	       to convert a hex number to decimal.
    0xNNNN         to convert a hex number to decimal.
    0oNNNN         to convert an octal number to decimal.
    0bNNNN         to convert a binary number to decimal.
    UxNNNN         to convert a unicode hex number to a character.
    U+NNNN         to convert a unicode hex number to a character.
    h    once to open this help page
    h    again to open the online help page

### q is for quote

If you have a text or calculation that you need the quoted form of then type `q:` and paste in the text:

    q:"hi"
    "\"hi\""

## Customise the Functions

The functions menu can be customised in the [fmWorkMate Settings].

Simply add further lines to the menu tree. Use indentation to make the hierarchy.

    Number Functions…
        Abs ( | )
        Ceiling ( | )
        Div ( | )
        Floor ( | )
        Int ( | )
        Mod ( | ; divisor )
        Round ( | ; precision )
        Sqrt ( | )
        Maths…
            Exp ( | )
            Factorial ( | )
            Lg ( | )
            Ln ( | )
            Log ( | )
            Sign ( | )
            Truncate ( | ; precision )
        Trigonometrioc functions…
            Acos ( | )
            Asin ( | )
            Atan ( | )
            Cos ( | )
            Degrees ( | )
            | * Pi
            Radians ( | )
            Sin ( | )
            Tan ( | )
        Logical functions…
            Evaluate ( | )
        Financial functions…
            FV ( | interestRate ; periods )
            NPV ( | ; interestRate )
            PMT ( | ; interestRate ; term )
            PV ( | ; interestRate ; periods )
    Base Functions…
        Convert FROM decimal…
            _Hex ( | ) // Dec -> Hex
            _HexF ( pFormat ; | ) // Dec -> Hex, e.g. _HexF ( "#000000" ; 255 ) -> #0000FF
            _HexRGB ( pRed ; pGreen ; pBlue )
            _HexRGBA ( pRed ; pGreen ; pBlue ; pAlpha )
            _Octal ( | ) // Dec -> Octal
            _Bin ( | ) // Dec -> Binary
            _Base( pBase ; | ) // Dec -> any base
        Convert TO decimal…
            _0x ( "|" ) // Hex -> Dec
            _0o ( "|" ) // Octal -> Dec
            _0b ( "|" ) // Binary -> Dec
            _0( pBase ; "|" ) // Any Base -> Dec
    Text Functions…
        Left ( "|" ; 1 )
        Middle ( "|" ; 2 ; 3 )
        Right ( "|" ; 1 )
        PatternCount ( "|" ; "search" )
        Position ( "|" ; "search" ; 1 ; 1 )
        Substitute ( "|" ; "search" ; "replace" )
        Trim ( "|" )
        Length ( "|" )
    Value Functions…
        GetValue ( "|" ; 1 )
        LeftValues ( "|" ; 1 )
        MiddleValues ( "|" ; 2 ; 3 )
        RightValues ( "|" ; 1 )
        ValueCount ( "|" )
        FilterValues ( "|" ; "values" )
        _ValuesRemove ( "|" ; "values¶to¶remove" )
    Word Functions…
        LeftWords ( "|" ; 1 )
        MiddleWords ( "|" ; 2 ; 3 )
        RightWords ( "|" ; 1 )
        WordCount ( "|" )
    Character Functions…
        Char ( | )
        Code ( "|" )
        Quote ( "|" )
        Upper ( "|" )
        Lower ( "|" )
        Proper ( "|" )
        Filter ( "|" ; "characters" )
        Exact ( "|" ; "comparisonText" )
        More…
            _Ux( "|" ) // Return Unicode character (from hex)
            _GetAsUnicodeCodePoints( "|" )
            _GetAsUTF8Codes( "|" )
            _GetAsUTF8Hex( "|" )
            _GetAsUTF8Encoded( "|" )
            _GetAsUTF8Calculation( "|" )
            _ListMultibyteUTFChars( "|" )
            GetAsURLEncoded( "|" )
    DateTime Functions…
        d ( "|" )
        t ( "|" )
        ts ( "|" )
        yrs ( | ) //astronomical
        mnths ( | ) //astronomical
        wks ( | )
        hrs ( | )
        mins ( | )
        secs ( | )
        ms ( | )
        µs ( | )
    Truth Functions…
        _Boolean( | )
        _Truelean( | )
        _Trilean( | )
        _TrueFalse( | )
    Repeat…
        |
        ||
        |||
        ||||
        |||||
        ||||||
        |||||||
        ||||||||
        |||||||||
        ||||||||||

## Custom Functions: Adding / Editing / Using

If you want to manage (edit / copy / add to) the available custom functions, you need to [re-login to get full access].

You can then access the custom functions as normal from the Manage Custom Function menu.

{: .note}
You may have to change the menu set from the Tools menu

{: .note}
and you may have to first enable the tools menu by choosing `use advanced tools` in the FileMaker Settings dialog


{: .note}
and in that case you'll' have to restart Fielmaker

{: .note}
Note: If you add you own custom functions to fmSimpleCalculator, remember that they will be lost when you next update fmWorkMate.

{% comment %}mrwMarkdownLinks{% endcomment %}
[fmSimpleCalculator]: fmsimplecalculator.html
[fmWorkMate]: fmworkmate.html
[fmWorkMate Settings]: fmworkmate-settings.html
[re-login to get full access]: re-login-to-get-full-access.html
