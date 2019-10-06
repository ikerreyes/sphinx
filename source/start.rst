Getting started
===============

.. _start sphinx:


Starting Sphinx
---------------

One of the easiest way to start Sphinx is using the *quickstart*.
It will create the basic files you need to be able to generate the
documentation.

To use the *quickstart* follow these steps:

1. Open a *terminal*, go to the project directory and create a *docs* folder:

  .. code-block:: bash

     $ cd path/to/project
     $ mkdir docs


2. Launch sphinx-quickstart

   .. code-block:: bash

      $ cd docs
      $ sphinx-quickstart


   Sphinx asks you how to set up the initial configuration.
   Few changes (at least) to the default options are suggested::

      Separate source and build directories (y/n) [n]: y

      autodoc: automatically insert docstrings from modules (y/n) [n]: y

      intersphinx: link between Sphinx documentation of different projects (y/n) [n]: y

      mathjax: include math, rendered in the browser by MathJax (y/n) [n]: y

      viewcode: include links to the source code of documented Python objects (y/n) [n]: y

   .. warning::

      Do not forget to create a Makefile

   After you answer all the questions, Sphinx will create some files for you like a :file:`conf.py`,
   a :file:`Makefile` and a main :file:`.rst` (named *index* if you haven't change it during the setup).


.. _setup:

The setup
---------

After setting up your docs folder, the project structure should be similar to
(note that the project directory is collapsed)::

   project/
   |
   |-- docs/
   |   |-- build/
   |   |-- source/
   |   |   |-- _templates
   |   |   |-- _static
   |   |   |-- index.rst
   |   |   |-- conf.py
   |   |-- Makefile
   |
   |-- project/
   |
   |-- README.rst
   |-- setup.py


The *source* folder is intended to contain the :file:`.rst` files or any other
files related to the documentations. It can also include templates or other static
files used during the build process.

The :file:`Makefile` is a script for building
the documentations. The usage is:

.. code-block:: bash

   make <output format>

E.g.:

.. code-block:: bash

   make html

:file:`index.rst` is the **masterdoc**. Its function is to serve as welcome page
and to contain the root of the :abbr:`toctree (table of contents tree)`.
All :file:`.rst` files in the source directory are compiled, but only the
ones explicitly set in a toctree are shown [#toctreeAccess]_.

The easiest way to include a new :file:`.rst` file is to add it to the *source* folder
and put its name (with or without extension) in the toctree of the masterdoc:

.. _toctree example:

.. code-block:: rst

   .. toctree::
      :maxdepth: 2

      intro
      tutorial
      ...



The :file:`conf.py` is the file where the configuration for the build process can be
modified.


.. [#toctreeAccess] Nested documents can include their own toctrees. Documents not mention in any toctree are still
   accessible through the search bar in the html output.
