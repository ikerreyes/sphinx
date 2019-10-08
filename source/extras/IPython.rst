
.. _ipython:


IPython
=======

IPython can also be used in your documentation.

Within the IPython project, two extensions have been
developed, which allow to use the **ipython**
directive. This directive will not only
highlight the code as the IPython console
but it also executes the code in an actual
kernel, so the outputs are obtained on
build time.

Let's see an example:

+---------------------------+-----------------------+
| ::                        |                       |
|                           | .. ipython:: python   |
|    .. ipython:: python    |                       |
|                           |    1+1                |
|       1+1                 |                       |
+---------------------------+-----------------------+


Enabling
********

To enable the ipython directive, two extensions
should be used::

    extensions = ['IPython.sphinxext.ipython_console_highlighting',
                  'IPython.sphinxext.ipython_directive']

You can simply add those to the extensions list
of the :file:`conf.py` file [#extensions]_


Additionally you can also declare (in the :file:`conf.py` file)
the ``ipython_execlines`` with lines to be executed by
the IPython console before executed any code in the
**ipython** directives::

    ipython_execlines = [
    'import numpy as np',
    # This ensures correct rendering on system with console encoding != utf8
    # (windows). It forces pandas to encode its output reprs using utf8
    # whereever the docs are built. The docs' target is the browser, not
    # the console, so this is fine.
    'pd.options.display.encoding="utf8"'
    ]


For example, with the above code ``numpy`` is imported as ``np``
so the following will work:

+---------------------------+-----------------------+
| ::                        |                       |
|                           | .. ipython:: python   |
|    .. ipython:: python    |                       |
|                           |    np.array([1,2,3])  |
|       np.array([1,2,3])   |                       |
+---------------------------+-----------------------+

.. important:: The python libraries you expect to use must be available
   in your environment.

Using
*****

The code executed in the IPython directive is executed in the same
kernel, thus variables... are saved:


+-------------------------------+-------------------------------+
| ::                            |                               |
|                               | .. ipython:: python           |
|    .. ipython:: python        |                               |
|                               |    arr = np.array([1,2,3])    |
|       arr = np.array([1,2,3]) |                               |
+-------------------------------+-------------------------------+


+---------------------------+-----------------------+
| ::                        |                       |
|                           | .. ipython:: python   |
|    .. ipython:: python    |                       |
|                           |    arr*2              |
|       arr*2               |                       |
+---------------------------+-----------------------+


.. [#extensions] IPython must be installed to find the extensions.
    If not, you can also copy them in a separate folder and
    include them. Check out how people from `pandas
    <https://github.com/pydata/pandas/tree/master/doc/sphinxext>`_ did it.
