.. _RtD:

Documentation in Read the Docs
==============================

`Read the Docs <https://readthedocs.org/>`_ hosts documentations. It can be used to automatically generate and
store the project documentation.

You can find information of how to use it in the
`Read the Docs documentation <https://read-the-docs.readthedocs.io/en/latest/getting_started.html>`_.



Setting up Read the Docs
------------------------

1. Log into the `Read the Docs <https://readthedocs.org/>`_ page and
   import your project.

#. After the initial configuration is done, got to ``Advanced Settings`` to:

   #. Check the ``install project`` option if you want to document your code.

   #. Add a :ref:`requirements file <req file>`.

   #. check the ``use system packages`` to make the build proccess faster.

   #. Choose the right Python Interpreter for your project.

#. Under the versions page, select the different `versions <https://read-the-docs.readthedocs.io/en/latest/versions.html>`_
   you want to build the documentation for.

   .. note::

      Versions are taken from the branches and from the tags.

#. Add a `webhook <https://read-the-docs.readthedocs.io/en/latest/webhooks.html>`_ to automate the
   `build process <https://read-the-docs.readthedocs.io/en/latest/builds.html>`_
   when a commit is made.


.. _req file:

The requirements file
---------------------

The requirement file contains some requirements that are for the Read the Docs build process
and not for others. This is a simple *.txt* file with a list of python packages.
The suggestion is to have a file :file:`docs/requirements.txt`.

Example::

      sphinxcontrib-napoleon

At the moment of writing some issues with the build process of Read the Docs force us to have the
rest of libraries needed for the project specified in :file:`requirements.txt`.

Using conda
-----------

At the time of writing, Python 3.5 was not supported directly by Read the Docs, so conda was used as a workaround.

A conda environment can be created to install the packages. To do so:

#. Create a conda YAML file with the packages your need.

    You can create a local environement and `export <http://conda.pydata.org/docs/using/envs.html#export-the-environment-file>`_
     it to a file.

#. Create a :file:`readthedocs.yml` file::

    requirements_file: docs/source/requirements.txt
    conda:
      file: docs/source/environment.yml
    python:
      setup_py_install: true

.. warning::

    At the time of writing, I have not been able to make the :file:`requirements.txt` file work with
    conda. If you have some special libraries there that are not in the environment (e.g.
    ``sphinxcontrib-napoleon``) add them to the conda YAML file.

.. hint::
    If you have the project installed in conda environment, remove it from the YAML file,
    so you ensure that the correct version is being build.


Using ReadTheDocs HTML theme
----------------------------

When building the documentation using ReadTheDocs, you can choose to use
their own HTML theme while when you build in local you can use another theme.
To do so, when building in ReadTheDocs, the environment variable
``READTHEDOCS`` is set to ``True``, so you can check it.
For example, in the :file:`conf.py` file::

    if os.environ.get('READTHEDOCS'):
        html_theme = 'sphinx_rtd_theme'
    else:
        html_theme = 'nature'

.. note:: The ReadTheDocs HTML theme can also be used locally.
   You can install it through ``pip`` or ``conda``.
   The package is named: ``sphinx_rtd_theme``.


