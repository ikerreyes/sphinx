
.. _docstrings:

Docstrings
==========

Docstrings purpose is to provide an overview of what a certain function, class, method... does.

Conventions:

- The first line should always be a short, concise summary of the object’s purpose.
- The first line should begin with a capital letter and end with a period.
- The second line should be blank.
- Tools that process documentation have to strip indentation.
  The first non-blank line after the first line of the string determines
  the amount of indentation for the entire documentation string.

Docstrings in Python documents can follow different formats, including the reST,
which is directly processed by Sphinx.
However, some formats are more readable than others, but they may require
a Sphinx extension to deal with them.

One of the most readable formats for docstrings is `Google docstrings <http://sphinxcontrib-napoleon.readthedocs.io/en/latest/example_google.html>`_.

Find an example of `the Google docstrings <http://sphinxcontrib-napoleon.readthedocs.io/en/latest/example_google.html?highlight=example#example-google-style-python-docstrings>`_
and more information about the `them <http://sphinxcontrib-napoleon.readthedocs.io/en/latest/index.html#id1>`_.

To ease the create of docstrings in Pycharm, the format can be selected in:
:menuselection:`File --> Settings... --> Tools --> Python Integrated Tool --> Docstrings --> Docstring format`
.

Sphinx needs to now the format of the docstrings to be able to parse them correctly.
By default, it parses the docstrings as if they were in reST format.
If it is not the case, take a look :ref:`at this section <google docstrings>`.
