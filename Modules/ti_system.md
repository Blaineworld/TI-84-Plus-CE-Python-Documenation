# `ti_system` Module

The `ti_system` module allows programs to control the terminal and access
features of the calculator outside of the Python app such as lists.

## `escape() -> bool`

This function returns `True` if the user pressed *clear* and `False` if the user
did not press `clear`.

### Return Value

Whether the user pressed clear.

### Errors

- `ValueError: invalid syntax for integer with base 10` happens when pressing
  any key when the function is called from the REPL.

## `recall_list(name) -> list`

The `recall_list` function loads a list from the calculator's memory.

### Arguments

- `name`: The name of the list to be used. This can be any object; it will be
  converted to a string using `str`.

### Return Value

It returns a list of `float`s.

### List Name Restrictions

List names can be either a digit from 1 to 6, or a different string which:

1. must be between 0 and 5 characters long.
2. must contain only capital letters and digits.
3. must not start with a digit.

### Errors

- `NameError: Variable name is invalid.` when the list name does not follow the
  name restrictions.
- `ValueError: Variable does not exist.` when the list does not exist.

## recall_RegEQ()

I have absolutely no idea what this function does at the time of writing this.

### Errors

- `ValueError: Variable does not exist.` happens every time I call the function,
  so I assume this function is meant to load something that I have not
  initialized. Unfortunately, I do not know what a RegEQ is.

## `sleep(seconds)`

This function suspends the execution of the program for the specified number of
seconds. It is identical in functionality to `time.sleep` but is not an alias of
that function.

### Arguments

- `seconds`: The number of seconds to wait for.

## `store_list(name, var)`

The `store_list` function saves a list to the calculator's memory. If the list
already exists, it is replaced. If it does not already exist, it is created.

### Arguments

- `name`: The name to save the list with. This can be any object; it will be
  converted to a string using `str`.
- `var`: The list to be saved. Items other than `int`s and `float`s are ignored.

### List Name Restrictions

It has the same name restrictions for as `recall_list`.

### Errors

- `NameError: Variable name is invalid.` when the list name does not follow the
  name restrictions.
- `TypeError: object of type ? has no len()` when the object passed in the `var`
  argument does not have an `__len__` method.
- `TypeError: Operation failed.` when the object passed in the `var` argument
  is not a `list`.
- `ValueError: Variable does not exist.` when the list does not exist.

## Display Functions

### `disp_at(...)`

This function has multiple different syntaxes, and I want to make sure I write
them all down. **TODO: Document `disp_at`.**

### `disp_clr()`

This function clears all text from the terminal identically to
`print("\x1B[2J", end = "")`.

### `disp_cursor(show)`

This function sets whether cursor is displayed or not. It is the only way I know
of to hide the cursor.

#### Arguments

- `show`: Specifies whether to show the cursor. It must be an `int`; `1` means
  to show the cursor and `0` means to not show it. Values other than `0` and `1`
  have no effect at all.

#### Errors

- `TypeError: can't convert ? to int` when the value provided is not an `int`.

### `disp_wait()`

This function suspends the execution of the program until the user presses
*clear*, then clears all text from the terminal identically to
`print("\x1B[2J", end = "")`.

#### Errors

- `ValueError: invalid syntax for integer with base 10` happens sometimes when
  calling it from the REPL.
