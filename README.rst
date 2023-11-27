.. image:: https://img.shields.io/pypi/v/backports.entry_points_selectable.svg
   :target: https://pypi.org/project/backports.entry_points_selectable

.. image:: https://img.shields.io/pypi/pyversions/backports.entry_points_selectable.svg

.. image:: https://github.com/jaraco/backports.entry_points_selectable/workflows/tests/badge.svg
   :target: https://github.com/jaraco/backports.entry_points_selectable/actions?query=workflow%3A%22tests%22
   :alt: tests

.. image:: https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/charliermarsh/ruff/main/assets/badge/v2.json
    :target: https://github.com/astral-sh/ruff
    :alt: Ruff

.. image:: https://img.shields.io/badge/code%20style-black-000000.svg
   :target: https://github.com/psf/black
   :alt: Code style: Black

.. .. image:: https://readthedocs.org/projects/PROJECT_RTD/badge/?version=latest
..    :target: https://PROJECT_RTD.readthedocs.io/en/latest/?badge=latest

.. image:: https://img.shields.io/badge/skeleton-2023-informational
   :target: https://blog.jaraco.com/skeleton

Compatibility shim to ease adoption of `importlib_metadata 3.6 <https://importlib-metadata.readthedocs.io/en/latest/history.html#v3-6-0>`_. Supplies forward-compatibility of "selectable" entry points even on older versions of ``importlib_metadata`` and ``importlib.metadata``, and avoids usage that triggers `deprecation warnings <https://github.com/python/importlib_metadata/issues/298>`_.

Use this shim for libraries or applications invoking ``entry_points()`` that run on Python older than 3.10 or where importlib_metadata is older than 3.6. In most cases, this shim is unnecessary and the easiest thing to do is simply require ``importlib_metadata >= 3.6`` on all Pythons (or only those prior to 3.10a7). In some environments, a library may be constrained on which versions of ``importlib_metadata`` can be required, so this library bridges that gap.

To use this shim, add ``backports.entry_points_selectable`` to the affected project's requirements. It will require ``importlib_metadata`` automatically where needed (prior to Python 3.8) but be satisfied by older versions. Projects should still require ``importlib_metadata`` as appropriate for API uses other than for ``entry_points``.

Then in code, instead of ``from importlib.metadata import entry_points``, use::

    from backports.entry_points_selectable import entry_points

And then use the "selectable" features (pass keyword arguments to ``entry_points`` or invoke ``.select()`` on the result).

This backport has a very lenient dependency on `importlib_metadata` for older Pythons and is a single module implementation. If adding a dependency is a concern, this module may be vendored into the affected project.
