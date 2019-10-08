
.. highlight:: text

Other Sphinx directives
=======================


Table of contents
-----------------

::

   .. toctree::
      :maxdepth: ‹depth›

      ‹file 1 without file name extension›
      ...

Some options that can be used:

``:glob:``
   Enables the use of wildcards
``:hidden:``
   The table will not be displayed
``:caption:``
   Caption name for the file in the toctree

As it has already been mentioned, this directive is useful to link different documents
and give structure to the docs.

Any file that is not in any toctree is not accessible in the output format
unless you include it through a different way [#toctree_out]_.

.. [#toctree_out] In the html output, the file will still be accessible if you search for it.


Download
--------

This role allow you to download files.
It is only included in output formats that allow it (like HTML).


+-----------------------------------+--------------------------------+
| ::                                |                                |
|                                   | :download:`../conf.py`         |
|   :download:`../conf.py`          |                                |
+-----------------------------------+--------------------------------+

Downloadable files are copied to the ``_downloads`` folder within the outuput folder.


Only
----

Conditional inclusion of part of a document can be selected with the `only <http://www.sphinx-doc.org/en/stable/markup/misc.html#including-content-based-on-tags>`_
directive.

+-----------------------------------+--------------------------------+
| ::                                |                                |
|                                   | .. only:: html                 |
|   .. only:: html                  |                                |
|                                   |    this is only in HTML output |
|      this is only in HTML output  |                                |
+-----------------------------------+--------------------------------+


Glossary
--------

The `glossary <http://www.sphinx-doc.org/en/stable/markup/para.html#glossary>`_ directive can be used to create
a list of term definitions:


+-----------------------------------+--------------------------------+
| ::                                |                                |
|                                   | .. glossary::                  |
|   .. glossary::                   |                                |
|                                   |    term 1                      |
|      term 1                       |       Term 1 definition        |
|         Term 1 definition         |                                |
|                                   |    term 2                      |
|      term 2                       |    term 3                      |
|      term 3                       |       Terms 2 and 3 share      |
|         Terms 2 and 3 share       |       definition               |
|         definition                |                                |
+-----------------------------------+--------------------------------+

Terms defined in the ``glossary`` can be referenced with the ``term`` role.

+-----------------------------+--------------------------+
| ::                          |                          |
|                             | Due to :term:`term 1`... |
|    Due to :term:`term 1`... |                          |
+-----------------------------+--------------------------+


Index
-----

You can create index entries with the ``index`` directive
and role. Read more in http://www.sphinx-doc.org/en/stable/markup/misc.html#index-generating-markup.

There are several options for the index entries, single, pair, and triple:

+--------------------------------------------------+-----------------------------------------------+
| ::                                               |                                               |
|                                                  | .. index::  single 1; subentry                |
|   .. index::  single 1; subentry                 |                                               |
|                                                  | .. index::                                    |
|   .. index::                                     |    single: single 2; subentry                 |
|      single: single 2; subentry                  |                                               |
|                                                  |                                               |
|                                                  | .. index::                                    |
|   .. index::                                     |    pair: pair 1; pair 2                       |
|      pair: pair 1; pair 2                        |                                               |
|                                                  | this :index:`single inline; subentry` is...   |
|   this :index:`single inline; subentry` is...    |                                               |
+--------------------------------------------------+-----------------------------------------------+

