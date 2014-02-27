Code related to testing Evil proper and evil packages.
## Installation

[Melpa](http://melpa.milkbox.net/):

    M-x package-install evil-tests

Or you can just put `evil-tests.el` somewhere on your
load path.

## Using in a package

Add this to the big comment block at the top:

    ;; Package-Requires: ((evil-tests "0.1"))

## API
* [evil-test-buffer](evil-test-buffer) `(@rest body)`
  Execute `FORMS` in a temporary buffer.
The following optional keywords specify the buffer's properties:

:state STATE            The initial state, defaults to `normal'.
:visual SELECTION       The Visual selection, defaults to `char'.
:point-start STRING     String for matching beginning of point,
                        defaults to \"[\".
:point-end STRING       String for matching end of point,
                        defaults to \"]\".
:visual-start STRING    String for matching beginning of
                        Visual selection, defaults to \"<\".
:visual-end STRING      String for matching end of
                        Visual selection, defaults to \">\".

Then follows one or more forms. If the first form is a string,
it is taken to be a buffer description as passed to
[evil-test-buffer-from-string](#evil-test-buffer-from-string), and initializes the buffer.
Subsequent string forms validate the buffer.

If a form is a list of strings or vectors, it is taken to be a
key sequence and is passed to `execute-kbd-macro`.  Remaining
forms are evaluated as-is. If the form is `(error SYMBOL ...)`
then the test fails unless an error of type `SYMBOL` is raised.

\(fn [[KEY VALUE]...] FORMS...)
## List to list

#### (#evil-test-buffer) `(@rest body)`
