# pycoverage.el

An emacs minor mode for reporting inline on coverage stats for Python

# Dependencies

* python-coverage>=4.0

# Installation

Put something like this in your .emacs

    (require 'linum)
    (require 'pycoverage)

    (defun my-coverage ()
      (interactive)
      (when (derived-mode-p 'python-mode)
        (progn
          (linum-mode)
          (pycoverage-mode)
          )
        )
      )

Install cov2emacs using setuptools or virtualenv or distutils

There should be ``.coverage`` file in the directory of the module you
want coverage reporting on (or the parents of that directory).
Note that if your file has been modified later than the .coverage file, it
will be considered as stale and ignore it.

# Running

M-x pycoverage-mode

If there is a .coverage file in the directory (or a parent) of the
source file try to use it for coverage information.  Red highlights
mean that lines were missed (Coverage percent for file is in mode
line).

# Links

Forked from:

    https://github.com/mattharrison/pycoverage.el
