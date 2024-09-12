# Code Style Guide

* In python, use 4 spaces for indentation, everywhere else, use 2 spaces for indentation, **no tabs**.
* All variable and function names should be written in snake_case.
* Class names should follow PascalCase.
* use type hints.
* favor pure functions.
* try and separate pure functions and functions with side effects.
* write testable function (keep in mind that the function should be testable when conceiving it).
* try and keep coneptual level in a function consistant (no low level action in high level functions).
* Use double quotes for strings except when using template literals.
* Place opening curly braces on the same line as the declaration.
* Maximum line length should be 100 characters. (be smart for this rule)
* Docstring should be written using block comments for functions and line comments for inline explanations.
* import should be sorted and sanitized.

In short, for python, use ruff to format text.
