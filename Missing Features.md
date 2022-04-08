# Missing Features

Many features one would normally expect to be able to use in Python are
genuinely missing on the TI-84 Plus CE Python, not just because it's an older
Python version. This file is dedicated to listing those missing features.

## Detailed Help

The `help` function simply tells you an object's type and lists its properties
and methods. This is unsurprising, as the Python app had to fit on a calculator.
Docstrings are ignored as far as I can tell.

## Most Random Functions

All features of the `random` module are missing, except `random`, `uniform`,
`randint`, `choice`, `randrange`, and `seed`.

## Most Time Functions

All features of the `time` module are missing, except `sleep` and `monotonic`.
This comes as a surprise to me, as the calculators do have built-in clocks that
can tell the time and date.
