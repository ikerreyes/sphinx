Sphinx in short
===============

Brief view of the steps to set up Sphinx for your project:

1. Open a *terminal* and go to the project directory.

#. Launch sphinx-quickstart

   .. code-block:: bash

      $ sphinx-quickstart


#. Open :file:`docs/source/conf.py` to make the following changes:

   #. Set the path to the code::

         sys.path.insert(0, os.path.abspath('../..'))

   #. Add `napoleon <http://sphinxcontrib-napoleon.readthedocs.io/en/latest/index.html#>`_ to the extensions list [#napoleon_note]_::

         extensions = [..., 'sphinx.ext.napoleon']

   #. Import version from the project::

         import <project name>
         version = <project name>.__version__
         release = <project name>.__version__

   #. Change the HTML theme::

         html_theme = 'sphinx_rtd_theme'

#. Create your docs and add them to the toctree:

   .. code-block:: rst

      .. toctree::
         :maxdepth: 2

         intro
         tutorial
         ...

#. Generate API docs

   #. Create the files to automatically load the docstrings
      and generate the corresponding docs:

      .. code-block:: bash

         $ sphinx-apidoc -f -o docs/source/pkg . test setup.py

   #. Add the :file:`docs/source/pkg/modules.rst` file to a toctree.

#. Build your docs:

   .. code-block:: bash

      $ make html



.. [#napoleon_note] The napoleon extension in needed to use Google or Numpy docstring. Skip this step if you are using reStructuredText format
   for the docstrings.