v1.1.1
======

Refreshed packaging.

v1.1.0
======

Add compatibility support for access by index and EntryPoints
mutability as introduced in importlib_metadata 4.4.

v1.0.4
======

#2: For test dependencies, when indicating Python 3, use ``>=3``
instead of ``>3`` to satisfy
`python-poetry/poetry#3862 <https://github.com/python-poetry/poetry/issues/3862>`_.

v1.0.3
======

Clarify docs in readme.

v1.0.2
======

#1: Fix AttributeError when ``EntryPoint`` does not yet implement
``matches``.

v1.0.1
======

Make universal wheel.

v1.0.0
======

Initial release presenting ``entry_points`` compatibility shim.
