Config
======

Sphinx behaviour can be modified by making some changes in the
:file:`conf.py` file.

Here we are going to see some of those possible changes.
You can find all the details in http://www.sphinx-doc.org/en/stable/config.html.


Useful extensions
-----------------

There are a number of extensions that can be useful for your docs:

- **sphinx.ext.autodoc**: enable to automatically load docs in the code
  with :ref:`autodoc <autodoc>`
- **sphinx.ext.intersphinx** (by default): link to other documentations
  with :ref:`intersphinx <intersphinx>`
- **sphinx.ext.napoleon** (by default): parse :ref:`Google or Numpy docstring format <google docstrings>`
- **sphinx.ext.viewcode**: enable to show the code in the API documentation
- **sphinx.ext.ifconfig**: conditional include of content
- **sphinx.ext.mathjax** (by default): load math with `MathJax <https://www.mathjax.org/>`_.
  Alternative, they can be rendered as images with ``sphinx.ext.imgmath``
- **sphinx.ext.coverage**
- **sphinx.ext.todo**: enable ``.. todo::`` directives.
  Content can be shown or hidden using:

  .. code:: python

     # If true, `todo` and `todoList` produce output, else they produce nothing.
     todo_include_todos = True


Find more extension in https://bitbucket.org/birkenfeld/sphinx-contrib/src/default/.

Other extension are:

- copy button for code blocks: https://sphinx-copybutton.readthedocs.io/en/latest/


.. _autodoc:

Using autodoc
-------------

Sphinx can automatically create the API docs from the Python
modules, as it is shown :ref:`here <apidocs>`.

To automatically generate documentation from your docstrings,
Sphinx needs to know the path for your code.
In the :file:`conf.py` file you will find these lines::

   # If extensions (or modules to document with autodoc) are in another directory,
   # add these directories to sys.path here. If the directory is relative to the
   # documentation root, use os.path.abspath to make it absolute, like shown here.
   #
   # import os
   # import sys
   # sys.path.insert(0, os.path.abspath('.'))

Uncomment the last three lines and :ref:`put the path to your code <apidocs>`.


.. _google docstrings:

Docstring format
----------------

Sphinx assumes the docstrings are in reST format. If it is not the case,
you need to add the appropiate extensions.

Particularly, for Google docstrings, you need to add `napoleon <http://sphinxcontrib-napoleon.readthedocs.io/en/latest/index.html#>`_ to the extensions list [#napoleon_note]_::

   extensions = [..., 'sphinx.ext.napoleon']

.. note::

   If Napoleon does not come with Sphinx, you can install it following the instructions in the above link
   and adding ``sphinxcontrib.napoleon`` to the extensions list.

.. _version and release:

Version and release
-------------------

Sphinx documentation is build with a version and release number.
Although they are initially hardcoded, this behaviour can be modified to
automatically import them::

   import <project name>
   version = <project name>.__version__
   release = <project name>.__version__

This way of taking the version will not work if the project is not installed.

   .. hint::

      **A workaround for uninstalled projects**

      Assume there is a file :file:`path/file_with_info.py` with a
      variable that contains the version:

      .. py:data:: __version__

      Then, load that file::

         project_info = {}
         with open('path/file_with_info.py') as f:
         exec(f.read(), project_info)

      And import the variable in :file:`conf.py`::

         version = project_info['__version__']

.. warning::

   If the project is not installed, the API documentation cannot be automatically generated,
   but the documentation for the rest will build.

.. _intersphinx:

Linking other projects documentation
------------------------------------

Sometimes it is useful to refer to Python objects
from other projects.

This can be done with the ``intersphinx`` extension.

This extension allows you to refer to projects that
are added to the :data:`intersphinx_mapping` :obj:`dictionary <dict>`.

The format of each link is::

   name: (target, inventory)

or::

   name: (target, (inventory1, inventory2, ...))

The *name* is the name you want to use to refer to that particular inventory
as ``:ref:`text <name:label>```, the *target* is the URL (or path) where to redirect
the links, and the *inventory* is where to find the inventory file.

A value of :obj:`None` in the *inventory* points to the :file:`objects.inv` file
in the URL (or path) that the *target* points to.
A different URL (or path) can be indicated, or even a list of inventories
(as soon as one success, it stops).

For example, to have not only the standard Python documentations, but also
Numpy, Pandas and Matplotlib do::


   intersphinx_mapping = {
               'python': ('https://docs.python.org/', None),
               'numpy': ('http://docs.scipy.org/doc/numpy/', None),
               'pandas': ('http://pandas-docs.github.io/pandas-docs-travis/', None),
               'matplotlib': ('http://matplotlib.org/', None)
               }

.. note:: Links done by :ref:`domains <crossrefPy>` also work.

.. _config html:

HTML output
-----------

The HTML output can be modified according to different
`HTML themes <http://www.sphinx-doc.org/es/stable/theming.html#builtin-themes>`_.

Moreover, other themes can also be used if you import them.

One that is common is the `Read the Docs theme <http://read-the-docs.readthedocs.io/en/latest/theme.html>`_.
After installing it, you can build your documentation by::

   html_theme = 'sphinx_rtd_theme'

.. note::

   In previous versions of Sphinx and the Read the Docs theme it
   was necessary to include it as follow::

       import sphinx_rtd_theme
       html_theme = 'sphinx_rtd_theme'
       html_theme_path = [sphinx_rtd_theme.get_html_theme_path()]

Include in all files
--------------------

Using the ``rst_epilog`` (or ``rst_prolog``) you can include a piece of reST at the end of all source files.
This can be useful for example to add substitutions that you want to be in all files.
E.g.::

    rst_epilog = """
    .. |psf| replace:: Python Software Foundation
    """



.. [#napoleon_note] The napoleon extension in needed to use Google or Numpy docstring. Skip this step if you are using reStructuredText format
   for the docstrings.
