## What is this?
I've extracted the test related code from Evil proper, to make it available to package writers.  The abstracts are
very good and there's frankly no use to re-invent the wheel in order
to test your evil-package.

## Installation

[Melpa](http://melpa.milkbox.net/):

    M-x package-install evil-tests

Or you can just put `evil-tests.el` somewhere on your load path.

## Using in a packge

Follow the [ELPA package format](http://marmalade-repo.org/doc-files/package.5.html)
and add this to the package header:
```cl
;; Package-Requires: ((evil-tests "0.1"))
```
