# General Quirks

The TI-84 Plus CE Python's Python environment has some quirks that someone used
to using a Python environment for normal people might not expect. This file is
dedicated to listing those quirks.

## `__name__ != "__main__"`

Typically, one would check if `__name__ == "__main__"` to run different code
depending on whether the file is being run as a script or as a module, but the
TI-84 Plus CE Python runs files by executing `from 𝘍𝘐𝘓𝘌 import *` in the shell.

This means that `__name__` will always be the name of the file, never
`"__main__"`. As a result, `if __name__ == "__main__":` cannot be used.

## File Name Limitations

Unlike most modern file systems, file names on the TI-84 Plus CE Python cannot
be longer than 8 characters, must contain only capital letters and digits, and
cannot start with a digit.

This means you will have to abbreviate a lot of your file names.
