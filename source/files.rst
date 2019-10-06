Documenting your project
========================

More docs
---------

To add more documents to the documentation, add new :file:`.rst` files
to the source directory (or in nested folders).
Files can also be in other folders, the latter recommendation is just for clarity.
There are some exceptions as the **readme** file, that is placed directly in the project folder.

The document structure stats with the masterdoc (:file:`index.rst` by default).

All *.rst* files will be compiled by Sphinx.
The ones that are not in any `toctree <http://www.sphinx-doc.org/es/stable/markup/toctree.html#the-toc-tree>`_ are not going to be shown.


.. note::

   Those files will still be accessible in the HTML output if you look for them in the search input.

Toctrees are not limited to the masterdoc, they can appear in any file.


.. _apidocs:

API documentation
-----------------

The API documentation for the code is generated from the docstrings.

Sphinx includes directives to create the API `documentation directly
from the docstrings <http://www.sphinx-doc.org/es/stable/ext/autodoc.html>`_.
These directives need to be called from a *.rst* file.

The first step to enable the API auto generation is to let Sphinx know where the docstrings are.
To do so, open :file:`docs/source/conf.py` and :ref:`set the path to your code <autodoc>`. E.g.::

   sys.path.insert(0, os.path.abspath('../..'))
   # use the relative path from this file to your project directory


Use the following command to generate :file:`.rst` files that will auto-generate the API docs when
Sphinx builds the docs:

.. code-block:: bash

   $ sphinx-apidoc -f -o docs/source projectdir

.. hint::
   A different output folder can be given to have the documentation for the code separated from other documents.
   Example:

      .. code-block:: bash

         $ sphinx-apidoc -f -o docs/source/pkg projectdir

.. _apidocs modules:

This command will create different *.rst* files. :file:`modules.rst` is the main one, and the one that
should be included in the documentation toctree.

This command does not need to be called with each modification of the docstrings, as they are read automatically.
It only needs to be re-run if functions, classes, files... are added or deleted.

The above shown command includes all modules and packages under the project directory.
Typically, the :file:`setup.py` and the test modules are part you do not want to have in the
documentation. To exclude those, you can add any path at the end of the command with the paths to
be excluded. Find more info in the `api-doc information <http://www.sphinx-doc.org/en/stable/man/sphinx-apidoc.html>`_.
