
.. highlight:: text

Cross references
================


Hyperlink text
--------------

There are different ways to create a `link <http://bg.upf.edu>`_.

+-----------------------------------------------+------------------------------------------+
| ::                                            |                                          |
|                                               | Citation style `link 1`_.                |
|    Citation style `link 1`_.                  |                                          |
|                                               | .. _link 1: http://bg.upf.edu            |
|    .. _link 1: http://bg.upf.edu              |                                          |
+-----------------------------------------------+------------------------------------------+
| ::                                            |                                          |
|                                               | Inline 1 `link 2 <http://bg.upf.edu>`_.  |
|    Inline 1 `link 2 <http://bg.upf.edu>`_.    |                                          |
+-----------------------------------------------+------------------------------------------+
| ::                                            |                                          |
|                                               | Inline 2 `<http://bg.upf.edu>`_.         |
|    Inline 2 `<http://bg.upf.edu>`_.           |                                          |
+-----------------------------------------------+------------------------------------------+
| ::                                            |                                          |
|                                               | Sphinx styple http://bg.upf.edu          |
|    Sphinx styple http://bg.upf.edu            |                                          |
+-----------------------------------------------+------------------------------------------+

Interal document references
---------------------------

Use ``.. _label name:`` plus a blank line before any text location.

Then you can reference to those labels in the reST way
(only works for labels within the document)::

   `label name`_

Example: `citation`_

Or in the Sphinx way::

   :ref:`displayed text <label>`

Which can be used between documents.

Example: :ref:`paragraph <transitions explanation>`

Alternatively, you can also use the ``:name:`` option in most blocks::

   .. list-table::
      :header-rows: 0
      :name: list example

      ...

Example: :ref:`list <list example>`

Section titles, footnotes, and citations automatically are link targets.


.. note:: According to the Sphinx documentation
   you can also user the ``:ref:`` role directly
   with the label name (e.g. ``:ref:`label name```)
   if the label name is placed just before a section label.


Footnotes
---------

You can create a footnote by::

   Put the reference in the text [1]_.

   .. [1] Footnote

Footnotes can have automatic labels with ``[#]`` [#somtText]_.

.. [#somtText] In addition you can also use ``[#someText]`` that will be displayed as any other label.

Together with automatic labels there are also automatic symbols using ``[*]``.


.. _citation:

Citations
---------

With a similar syntax to footnotes, there are [citations]_ ::

   .. [REL09] Citation

   Is referenced as [REL09]_ REL09_ or rel09_.


.. [citations] citation example


Other documents
---------------

Other documetns can be referenced with the ``:doc:`` directive.

+--------------------------------------------------+-----------------------------------------------+
| ::                                               |                                               |
|                                                  | :doc:`reference to a doc <includeDirective>`  |
|    :doc:`reference to a doc <includeDirective>`  |                                               |
+--------------------------------------------------+-----------------------------------------------+

File includes
-------------

.. you can use the relative path to the file . Example: ../../../readme.rst

.. include:: includeDirective.rst

Example::

   .. include:: includeDirective.rst


The ``literalinclude`` directive allows you to include the file
into a container. This example::

   .. literalinclude:: includeDirective.rst
      :language: text
      :linenos:

is shown as:

.. literalinclude:: includeDirective.rst
   :language: text
   :linenos:


Python objects
--------------

See: `cross-referencing Python <http://www.sphinx-doc.org/en/stable/domains.html#cross-referencing-python-objects>`_.
More information about it can be found :ref:`in this document <crossrefPy>`.
