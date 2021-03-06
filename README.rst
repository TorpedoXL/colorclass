==========
colorclass
==========

Yet another ANSI color text library for Python. Provides "auto colors" for dark/light terminals. Works on Linux, OS X,
and Windows. For Windows support you just need to call ``Windows.enable()`` in your application.

On Linux/OS X ``autocolors`` are toggled by calling ``set_light_background()`` and ``set_dark_background()``. On Windows
this can be done automatically if you call ``Windows.enable(auto_colors=True)``.

In Python2.x this library subclasses ``unicode``, while on Python3.x it subclasses ``str``.

* Python 2.6, 2.7, PyPy, PyPy3, 3.3, and 3.4 supported on Linux and OS X.
* Python 2.7, 3.3, and 3.4 supported on Windows (both 32 and 64 bit versions of Python).

Tested on Windows XP and Windows 10 technical preview.

.. image:: https://img.shields.io/appveyor/ci/Robpol86/colorclass/master.svg?style=flat-square&label=AppVeyor%20CI
   :target: https://ci.appveyor.com/project/Robpol86/colorclass
   :alt: Build Status Windows

.. image:: https://img.shields.io/travis/Robpol86/colorclass/master.svg?style=flat-square&label=Travis%20CI
   :target: https://travis-ci.org/Robpol86/colorclass
   :alt: Build Status

.. image:: https://img.shields.io/codecov/c/github/Robpol86/colorclass/master.svg?style=flat-square&label=Codecov
   :target: https://codecov.io/github/Robpol86/colorclass
   :alt: Coverage Status

.. image:: https://img.shields.io/pypi/v/colorclass.svg?style=flat-square&label=Latest
   :target: https://pypi.python.org/pypi/colorclass/
   :alt: Latest Version

.. image:: https://img.shields.io/pypi/dm/colorclass.svg?style=flat-square&label=PyPI%20Downloads
   :target: https://pypi.python.org/pypi/colorclass/
   :alt: Downloads

Quickstart
==========

Install:

.. code:: bash

    pip install colorclass

Example Implementation
======================

.. image:: https://github.com/Robpol86/colorclass/raw/master/example.png?raw=true
   :alt: Example Script Screenshot

.. image:: https://github.com/Robpol86/colorclass/raw/master/example_windows.png?raw=true
   :alt: Example Windows Screenshot

Source code for the example code is: `example.py <https://github.com/Robpol86/colorclass/blob/master/example.py>`_

Usage
=====

Different colors are chosen using curly-bracket tags, such as ``{red}{/red}``. For a list of available colors, call
``colorclass.list_tags()``.

The available "auto colors" tags are:

* autoblack
* autored
* autogreen
* autoyellow
* autoblue
* automagenta
* autocyan
* autowhite
* autobgblack
* autobgred
* autobggreen
* autobgyellow
* autobgblue
* autobgmagenta
* autobgcyan
* autobgwhite

Methods of Class instances try to return sane data, such as:

.. code:: python

    from colorclass import Color
    color_string = Color('{red}Test{/red}')

    color_string
    u'\x1b[31mTest\x1b[39m'

    len(color_string)
    4

    color_string.istitle()
    True

There are also a couple of helper attributes for all Color instances:

.. code:: python

    color_string.value_colors
    '\x1b[31mTest\x1b[39m'

    color_string.value_no_colors
    'Test'

Changelog
=========

This project adheres to `Semantic Versioning <http://semver.org/>`_.

1.2.0 - 2015-03-19
------------------

Added
    * Convenience single-color methods by `Marc Abramowitz <https://github.com/msabramo>`_.

1.1.2 - 2015-01-07
------------------

Fixed
    * Maintaining ``Color`` type through ``.encode()`` and ``.decode()`` chains.

1.1.1 - 2014-11-03
------------------

Fixed
    * Python 2.7 64-bit original colors bug on Windows.
    * resetting colors when ``reset_atexit`` is True.
    * Improved sorting of ``list_tags()``.

1.1.0 - 2014-11-01
------------------

Added
    * Native Windows support and automatic background colors.

1.0.2 - 2014-10-20
------------------

Added
    * Ability to disable/strip out all colors.

1.0.1 - 2014-09-11
------------------

Fixed
    * ``splitlines()`` method.

1.0.0 - 2014-09-01
------------------

* Initial release.
