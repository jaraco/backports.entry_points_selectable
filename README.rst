.. image:: https://img.shields.io/pypi/v/backports.entry_points_selectable.svg
   :target: `PyPI link`_

.. image:: https://img.shields.io/pypi/pyversions/backports.entry_points_selectable.svg
   :target: `PyPI link`_

.. _PyPI link: https://pypi.org/project/backports.entry_points_selectable

.. image:: https://github.com/jaraco/backports.entry_points_selectable/workflows/tests/badge.svg
   :target: https://github.com/jaraco/backports.entry_points_selectable/actions?query=workflow%3A%22tests%22
   :alt: tests

.. image:: https://img.shields.io/badge/code%20style-black-000000.svg
   :target: https://github.com/psf/black
   :alt: Code style: Black

.. .. image:: https://readthedocs.org/projects/skeleton/badge/?version=latest
..    :target: https://skeleton.readthedocs.io/en/latest/?badge=latest


Compatibility shim to ease adoption of
`importlib_metadata 3.6 <https://importlib-metadata.readthedocs.io/en/latest/history.html#v3-6-0>`_. Avoids `deprecation warnings <https://github.com/python/importlib_metadata/issues/298>`_. Use this shim for libraries or applications invoking ``entry_points()`` that run on Python older than 3.10 or where importlib_metadata is older than 3.6. To use, add ``backports.entry_points_selectable`` to your project requirements. It will include ``importlib_metadata`` automatically where needed. Projects should still require ``importlib_metadata`` as appropriate for API uses other than ``entry_points``.

Then in code, instead of ``from importlib.metadata import entry_points``, use::

    from backports.entry_points_selectable import entry_points

And then use the "selectable" features (pass keyword arguments to ``entry_points`` or invoke ``.select()`` on the result).
