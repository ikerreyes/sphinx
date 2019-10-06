
.. _markup constructs:

#################################
reST and Sphinx markup constructs
#################################

.. highlight:: text

This document is intended to give some ideas of how to deal
with reST ans Sphinx. It is not a fully correct or something you should trust blindly.
There are probably better ways of doing most of the things you find here.

In this document reST and Sphinx are mixed.

More documentation can be found `in the Sphinx page <http://www.sphinx-doc.org/en/stable/contents.html>`_.

.. contents:: Contents
   :depth: 2
   :local:


**********
Sectioning
**********

There are different ways of declaring the sections in reST, here the Sphinx way
is presented::

    ####
    Part
    ####

    *******
    Chapter
    *******

    Section
    =======

    Subsection
    ----------

    Subsubsection
    ^^^^^^^^^^^^^

    Paragraph
    """""""""

    Normal paragraphs are separated by a blank line.


Sphinx will normally decide the level of the section automatically.

.. _transitions explanation:

We can add transitions using ``----`` between two blank lines.

----

*************
Inline markup
*************

.. list-table:: reST inline
   :header-rows: 1
   :stub-columns: 0

   *  -  output
      -  reST
   *  -  *ita\*lic*
      -  ``*ita\*lic*`` or ``:emphasis:`ita*lic```
   *  -  **bold**
      -  ``**bold**`` or ``:strong:`bold```
   *  -  ``lit\`eral``
      -  ````lit\`eral```` or ``:literal:`lit\`eral```
   *  -  co\ **mbin**\ ed
      -  ``co\ **mbin**\ ed`` or ``co\ :strong:`mbin`\ ed``
   *  -  sub\ :sub:`script`
      -  ``sub\ :sub:`script``` or ``sub\ :subscript:`script```
   *  -  super\ :sup:`script`
      -  ``super\ :sup:`script``` or ``super\ :superscript:`script```
   *  -  :t:`Title reference` [#titleref]_
      -  ``:title-reference:`Title reference``` or ``:title:`Title reference``` or ``:t:`Title reference```
   *  -  interpreted text: the meaning depends on the domain
      -  ```interpreted text```


.. list-table:: Sphinx inline
   :header-rows: 1
   :stub-columns: 0

   *  -  output
      -  Sphinx
   *  -  :abbr:`abbr (abrebiation)`
      -  ``:abbr:`abbr (abrebiation)```
   *  -  :command:`command -option`
      -  ``:command:`command -option```
   *  -  :file:`path/and/file.ext`
      -  ``:file:`path/and/file.ext```
   *  -  :menuselection:`Menu --> Selection`
      -  ``:menuselection:`Menu --> Selection```
   *  -  :program:`Program`
      -  ``:program:`Program```
   *  -  :samp:`Literal text with {variable}`
      -  ``:samp:`Literal text with {variable}```
   *  -  :kbd:`Control-x Control-f` (sequence of keystrokes)
      -  ``:kbd:`Control-x Control-f```
   *  -  :regexp:`[^regular](expression)`
      -  ``:regexp:`[^regular](expression)```
   *  -  :makevar:`MAKE_VARIABLE`
      -  ``:makevar:`MAKE_VARIABLE```

----

********
Comments
********

Any text which begins with an explicit markup
but does not use any known construction is
a comment:

+--------------------------+-----------------------+
| ::                       |                       |
|                          | .. This is a comment  |
|     .. This is a comment |                       |
+--------------------------+-----------------------+

Comments are not shown in the output.

----


******
Blocks
******

Literal
=======

Block which is not in interpreted at all.

To declare it it needs: ``::`` + blank line + indented block.

+--------------------------------------------+-----------------------------------------+
| ::                                         |                                         |
|                                            | ::                                      |
|    ::                                      |                                         |
|                                            |    **special characters** are not       |
|       **special characters** are not       |    ``interpreted``                      |
|       ``interpreted``                      |                                         |
|                                            |                                         |
+--------------------------------------------+-----------------------------------------+
| ::                                         |                                         |
|                                            | Other example::                         |
|    Other example::                         |                                         |
|                                            |    if there is not a blank space        |
|       if there is not a blank space        |    between text and :: then it is       |
|       between text and :: then it is       |     displayed as ':'                    |
|       displayed as ':'                     |                                         |
|                                            |                                         |
+--------------------------------------------+-----------------------------------------+
| ::                                         |                                         |
|                                            | ::                                      |
|    ::                                      |                                         |
|                                            |    in the text body                     |
|       in the text body                     |        indetation is                    |
|           indetation is                    |             preserved                   |
|                preserved                   |                                         |
|                                            |                                         |
+--------------------------------------------+-----------------------------------------+

Text in literal blocks is highlighted according to the :ref:`highlight language <hightlighted language>`.

Line
====

| Line blocks are preceded by ``|`` and at least 1 white space.
| The are useful when the structure of lines is
| important



+--------------------------------------------+-----------------------------------------+
| ::                                         |                                         |
|                                            | | Line blocks can be                    |
|    | Line blocks can be                    |   multiline                             |
|      multiline                             | |    And also preseve the indetation    |
|    |    And also preseve the indetation    |                                         |
|                                            |                                         |
+--------------------------------------------+-----------------------------------------+

Quotes
======

Quotes are created

   By indeting them more than
   the surrounding paragraphs.

   -- Someone - somewhere

+--------------------------------------------+-----------------------------------------+
| ::                                         |                                         |
|                                            | Someone said:                           |
|    Someone said:                           |                                         |
|                                            |     Indetation makes the body           |
|       Indetation makes the body            |                                         |
|                                            |     -- 2 or 3 ``-`` for attribution     |
|       -- 2 or 3 ``-`` for attribution      |                                         |
|                                            |                                         |
+--------------------------------------------+-----------------------------------------+

There are also directives to create quotes.
Look for: ``pull-quote`` and ``epigraph``.


----

*****
Lists
*****

Bulleted
========

- Bullets are "-", "*" or "+".
  Continuing text must be aligned after the bullet and whitespace.

   - A blank line before the first and last items is required.
     Blank lines between items are optional.

Example:

+--------------------------+---------------------+
| ::                       |                     |
|                          | - One               |
|     - One                |                     |
|                          | - Two               |
|     - Two                |   Multiline         |
|       Multiline          |                     |
|                          |   - Three           |
|     - Three              |                     |
|                          |     Multiparagraph  |
|       Multiparagraph     |                     |
|                          | - Four              |
|     - Four               |                     |
|                          |                     |
+--------------------------+---------------------+


Horizontal
==========

.. hlist::
   :columns: 3

   * list of
   * short items
   * that should be
   * displayed
   * horizontally

.. warning::
   The order of the list is not the one that you might expect

Example:

.. sidebar:: shown as:

   .. hlist::
      :columns: 3

      * one
      * two
      * three
      * four

::

    .. hlist::
       :columns: 3

       * one
       * two
       * three
       * four



Enumerated
==========

1. Possible enumerators:

   #. arabic numerals
      [1, 2,...]
   #. alphabet characters
      (upper- and lowercase)
      [a, b,..., A, B,...]
   #. roman numerals
      (upper- and lowercase)
      [i, ii,..., I, II,...]
   #. The auto-enumerator #.
      It can be intercalated with the others.

#. The enumerator must go with one of the following:

   #. .
   #. )
   #. ()



Example:

+-----------------------------+--------------------------+
| ::                          |                          |
|                             |  3. One                  |
|                             |       #. Two             |
|    3. One                   |          Multiline       |
|       #. Two                |                          |
|          Multiline          |  #. Three                |
|                             |                          |
|     #. Three                |     Multiparagraph       |
|                             |                          |
|        Multiparagraph       |                          |
|                             |  14. We can alter the    |
|     14. We can alter the    |      sequence of the     |
|         sequence of the     |      numbers             |
|         numbers             |                          |
|                             |                          |
+-----------------------------+--------------------------+


Definition
==========

Element
  Description

Example:

+-----------------------+--------------------+
| ::                    |                    |
|                       | Element 1          |
|    Element 1          |   Description 1    |
|      Description 1    |                    |
|                       | Element 2          |
|    Element 2          |   Description 2    |
|      Description 2    |                    |
|                       |    Multiparagraph  |
|      Multiparagraph   |                    |
|                       |                    |
+-----------------------+--------------------+

Field
=====

:Field id: description

Example:

+-----------------------------------+--------------------------------+
| ::                                |                                |
|                                   | :Field 1: description can      |
|    :Field 1: description can      |    also be multiline           |
|       also be multiline           | :Field 2: another description  |
|    :Field 2: another description  |                                |
+-----------------------------------+--------------------------------+


Options
=======

-v argument  Description
--o         Description 2

Example:

+--------------------------------------------+-----------------------------------------+
| ::                                         |                                         |
|                                            | -v              Option                  |
|    -v              Option                  | -v all          Option with value       |
|    -v all          Option with value       | --verbose       Long option             |
|    --verbose       Long option             | --verbose=all   Long option with value  |
|    --verbose=all   Long option with value  |                                         |
|                                            |                                         |
+--------------------------------------------+-----------------------------------------+

----

******
Tables
******

Simple
======

=============  ===========
``=`` is used  to indicate
the            columns
=============  ===========

Code::

   =============  ===========
   ``=`` is used  to indicate
   the            columns
   =============  ===========

==================================   =========
1                                    2
                                     multiline
3 first column cannot be multiline   4
==================================   =========

Code::

   ==================================   =========
   1                                    2
                                        multiline
   3 first column cannot be multiline   4
   ==================================   =========




====   ======
with   header
====   ======
1      2
3      4
====   ======

Code::

   ====   ======
   with   header
   ====   ======
   1      2
   3      4
   ====   ======


========  ======   ==================
column    spans    are created
========  ======   ==================
using a            sequence of `-`
----------------   ------------------
except    for the last row
--------  ---------------------------
and       last     header
where     `=` is   a must
========  ======   ==================

Code::

   ========  ======   ==================
   column    spans    are created
   ========  ======   ==================
   using a            sequence of `-`
   ----------------   ------------------
   except    for the last row
   --------  ---------------------------
   and       last     header
   where     `=` is   a must
   ========  ======   ==================

.. commented because latexpdf does not support nested tables
   +--------------------------------------------------------+-----------------------------------------------------+
   | ::                                                     |                                                     |
   |                                                        | ==================================   =========      |
   |    ==================================   =========      |  1                                    2             |
   |    1                                    2              |                                       multiline     |
   |                                         multiline      | 3 first column cannot be multiline   4              |
   |    3 first column cannot be multiline   4              | ==================================   =========      |
   |    ==================================   =========      |                                                     |
   |                                                        |                                                     |
   +--------------------------------------------------------+-----------------------------------------------------+
   | ::                                                     |                                                     |
   |                                                        | ====   ======                                       |
   |    ====   ======                                       | with   header                                       |
   |    with   header                                       | ====   ======                                       |
   |    ====   ======                                       | 1      2                                            |
   |    1      2                                            | 3      4                                            |
   |    3      4                                            | ====   ======                                       |
   |    ====   ======                                       |                                                     |
   |                                                        |                                                     |
   +--------------------------------------------------------+-----------------------------------------------------+
   | ::                                                     |                                                     |
   |                                                        | ========  ======   ==================               |
   |    ========  ======   ==================               | column    spans    are created                      |
   |    column    spans    are created                      | ========  ======   ==================               |
   |    ========  ======   ==================               | using a            sequence of `-`                  |
   |    using a            sequence of `-`                  | ----------------   ------------------               |
   |    ----------------   ------------------               | except    for the last row                          |
   |    except    for the last row                          | --------  ---------------------------               |
   |    --------  ---------------------------               | and       last     last header                      |
   |    and       last     header                           | where     `=` is   a must                           |
   |    where     `=` is   a must                           | ========  ======   ==================               |
   |    ========  ======   ==================               |                                                     |
   |                                                        |                                                     |
   +--------------------------------------------------------+-----------------------------------------------------+

Grid
====

+------+-------------------------------------+
| grid | tables combine `+` and `-` symbols  |
+------+-------------------------------------+
| and  | more complex types can be expressed |
+------+-------------------------------------+


.. example
   +------------------------+----------------+
   | ::                     |                |
   |                        | +------+-----+ |
   |    +------+-----+      | | 1    | 2   | |
   |    | 1    | 2   |      | +------+-----+ |
   |    +------+-----+      | | 3    | 4   | |
   |    | 3    | 4   |      | +------+-----+ |
   |    +------+-----+      |                |
   +------------------------+----------------+

.. commented because latexpfd does not support it
   +-----------------------+-------------------------+---------------+
   | headers are           | separated by  `=`                       |
   +=======================+=========================+===============+
   | Literal blocks        | Lists                   | Lines         |
   +-----------------------+   - one                 +---------------+
   | Example::             |   - two                 | | line 1      |
   |                       |                         |   Multiline   |
   |    **C**              |                         | | line 2      |
   +-----------------------+-------------------------+---------------+


Example::

   +-----------------------+-------------------------+---------------+
   | headers are           | separated by  `=`                       |
   +=======================+=========================+===============+
   | Literal blocks        | Lists                   | Lines         |
   +-----------------------+   - one                 +---------------+
   | Example::             |   - two                 | | line 1      |
   |                       |                         |   Multiline   |
   |    **C**              |                         | | line 2      |
   +-----------------------+-------------------------+---------------+

.. commented because latexpfd does not support it
   +--------------------------------------------------------------------------+--------------------------------------------------------------------------+
   | ::                                                                       |                                                                          |
   |                                                                          | +-----------------------+-------------------------+---------------+      |
   |   +-----------------------+-------------------------+---------------+    | | headers are           | separated by  `=`                       |      |
   |   | headers are           | separated by  `=`                       |    | +=======================+=========================+===============+      |
   |   +=======================+=========================+===============+    | | Literal blocks        | Lists                   | Lines         |      |
   |   | Literal blocks        | Lists                   | Lines         |    | +-----------------------+   - one                 +---------------+      |
   |   +-----------------------+   - one                 +---------------+    | | Example::             |   - two                 | | line 1      |      |
   |   | Example::             |   - two                 | | line 1      |    | |                       |                         |   Multiline   |      |
   |   |                       |                         |   Multiline   |    | |    **C**              |                         | | line 2      |      |
   |   |    **C**              |                         | | line 2      |    | +-----------------------+-------------------------+---------------+      |
   |   +-----------------------+-------------------------+---------------+    |                                                                          |
   +--------------------------------------------------------------------------+--------------------------------------------------------------------------+


CSV
====


.. todo::

   Example of CSV table

List
====

.. list-table:: list table
   :header-rows: 0
   :widths: 10 10 10 10
   :stub-columns: 1
   :name: list example

   *  -  Rows
      -  each cell
      -  can contain
      -  **markup**
   *  -  Columns
      -  its number
      -  must be
      -  constant


Code::

   .. list-table:: list table
      :header-rows: 0
      :widths: 10 10 10 10
      :stub-columns: 1
      :name: list example

      *  -  Rows
         -  each cell
         -  can contain
         -  **markup**
      *  -  Columns
         -  its number
         -  must be
         -  constant


Title
=====

The ``table`` directive can be used to create a table with title.

.. table:: table title

   =============  ===========
   simple         table
   with           title
   =============  ===========

Code::

   .. table:: table title

      =============  ===========
      simple         table
      with           title
      =============  ===========


.. Example:

.. commented because latexpfd does not support it
   +-----------------------------------+--------------------------------+
   | ::                                |                                |
   |                                   | .. table:: my table            |
   |    .. table:: my table            |                                |
   |                                   |    =============  ===========  |
   |       =============  ===========  |    simple         table        |
   |       simple         table        |    with           title        |
   |       with           title        |    =============  ===========  |
   |       =============  ===========  |                                |
   +-----------------------------------+--------------------------------+



----

****************
Cross references
****************

Hyperlink text
==============

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
===========================

Use ``.. _label name:`` plus a blank line before any text location.

Then you can reference to those labels in the reST way::

   `label name`_

Example: `transitions explanation`_

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
=========

You can create a footnote by::

   Put the reference in the text [1]_.

   .. [1] Footnote

Footnotes can have automatic labels with ``[#]`` [#somtText]_.

.. [#somtText] In addition you can also use ``[#someText]`` that will be displayed as any other label.

Together with automatic labels there are also automatic symbols using ``[*]``.


.. _citation:

Citations
=========

With a similar syntax to footnotes, there are [citations]_ ::

   .. [REL09] Citation

   Is referenced as [REL09]_ REL09_ or rel09_.


.. [citations] citation example


Other documents
===============

Other documetns can be referenced with the ``:doc:`` directive.

+--------------------------------------------------+-----------------------------------------------+
| ::                                               |                                               |
|                                                  | :doc:`reference to a doc <includeDirective>`  |
|    :doc:`reference to a doc <includeDirective>`  |                                               |
+--------------------------------------------------+-----------------------------------------------+

File includes
=============

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
==============

See: `cross-referencing Python <http://www.sphinx-doc.org/en/stable/domains.html#cross-referencing-python-objects>`_.
More information about it can be found :ref:`in this document <crossrefPy>`.



*********************
Other reST directives
*********************

.. _content table:

.. contents:: `Table of contents`
   :depth: 2
   :local:



Table of contents
=================

You can create a table of contents with the sections.
Use ``:local:`` to create a table with only subsections of the current section.
Otherwise, it will cover the whole file. Title is optional. :ref:`Example <content table>`::

   .. contents:: `Table of contents`
      :depth: ‹number›
      :local:

.. warning::

   reST table of contents is limited to the file. The table of contents from Sphinx
   covers multiple documents.

Images and figures
==================

To include an image in your docs, you only need to use the
`image <http://docutils.sourceforge.net/docs/ref/rst/directives.html#image>`_ directive

.. code-block:: rest

   .. image:: /_static/myimage.png

Usually, you place your images inside the ``_static`` folder under
the ``source`` folder of your documentation.
This folder will be copied when building HTML output,
so images can be fetched from a server.

There are also a number of options you can use to tweak your image:

.. code-block:: rest

   .. image:: /_static/myimage.png
      :height: 100px
      :width: 200 px
      :scale: 50 %
      :alt: alternate text
      :align: right


The `figure <http://docutils.sourceforge.net/docs/ref/rst/directives.html#figure>`_
directive an extension of the ``image`` one,
enabling to add an optional caption and legend to your image:


.. code-block:: rest

   .. figure:: /_static/myimage.png

      This is the caption.

      The legend consists of all elements after the caption.

Substituions
============

|substitutions| can be done by::

   .. |name| replace:: text for *replacing*

   Any |name| will be replaced by the text.


|substitutions| can also be done for images::

   .. |caution| image:: warning.png
                :alt: Warning!


.. |substitutions| replace:: **Substituions**


As reST does not support nested inline markup,
substitutions are used in combination with the "replace" directive
to create a reference with styled text.

E.g. to add bold to text in an hyperlink:


+-----------------------------------------------------------------+-----------------------------------------------------------+
|                                                                 |  I recommend you try |Python|_.                           |
|  ::                                                             |                                                           |
|                                                                 |  .. |Python| replace:: Python, *the* best language around |
|     I recommend you try |Python|_.                              |  .. _Python: http://www.python.org/                       |
|                                                                 |                                                           |
|     .. |Python| replace:: Python, *the* best language around    |                                                           |
|     .. _Python: http://www.python.org/                          |                                                           |
|                                                                 |                                                           |
+-----------------------------------------------------------------+-----------------------------------------------------------+


E.g. to have an hyperlink with abbreviation:

+-----------------------------------------------------------------+-----------------------------------------------------------+
|                                                                 |  I recommend you try |py|_.                               |
|  ::                                                             |                                                           |
|                                                                 |  .. |py| replace:: :abbr:`py (Python)`                    |
|     I recommend you try |py|_.                                  |  .. _py: http://www.python.org/                           |
|                                                                 |                                                           |
|     .. |py| replace:: :abbr:`py (Python)`                       |                                                           |
|     .. _py: http://www.python.org/                              |                                                           |
|                                                                 |                                                           |
+-----------------------------------------------------------------+-----------------------------------------------------------+


Sidebar
=======

.. sidebar:: Sidebar Title
   :subtitle: Optional

   Body

Sidebars are like miniature documents.

Example::

   .. sidebar:: Sidebar Title
      :subtitle: Optional

      Body

Topic
=====

.. topic:: a topic

   is a self-contained idea that is separate
   from the flow of the document

Example::

   .. topic:: title

      the body is separated
      by a blank line



Admonitions
===========

How the different admonitions are displayed depends
on the themes. Not all themes support all of the admonitions.
The most common ones are the first ones.


+--------------------+-----------------+
| ::                 |                 |
|                    | .. warning::    |
|    .. warning::    |    warning      |
|       warning      |                 |
+--------------------+-----------------+
| ::                 |                 |
|                    | .. note::       |
|    .. note::       |    note         |
|       note         |                 |
+--------------------+-----------------+
| ::                 |                 |
|                    | .. error::      |
|    .. error::      |    error        |
|       error        |                 |
+--------------------+-----------------+
| ::                 |                 |
|                    | .. hint::       |
|    .. hint::       |    hint         |
|       hint         |                 |
+--------------------+-----------------+
| ::                 |                 |
|                    | .. attention::  |
|    .. attention::  |    attention!   |
|       attention!   |                 |
+--------------------+-----------------+
| ::                 |                 |
|                    | .. caution::    |
|    .. caution::    |    caution      |
|       caution      |                 |
+--------------------+-----------------+
| ::                 |                 |
|                    | .. danger::     |
|    .. danger::     |    danger!!     |
|       danger!!     |                 |
+--------------------+-----------------+
| ::                 |                 |
|                    | .. important::  |
|    .. important::  |    important    |
|       important    |                 |
+--------------------+-----------------+
| ::                 |                 |
|                    | .. tip::        |
|    .. tip::        |    tip          |
|       tip          |                 |
+--------------------+-----------------+



Math
=====

To use `mathematical expressions <http://www.sphinx-doc.org/en/stable/ext/math.html>`_, you can use LaTeX expressions under the
following directives:

1. ``:math:`<expression>```

   Since Pythagoras, we know that :math:`a^2 + b^2 = c^2`.

   Code::

      Since Pythagoras, we know that :math:`a^2 + b^2 = c^2`.

#. ``.. math::`` directive

   .. math::

      (\prod \limits_{i=1}^n (x_i+1))^{1/n}-1 = \sqrt[n]{(x_1+1)(x_2+1) \cdots (x_n+1)} -1

   Code::

      .. math::

         (\prod \limits_{i=1}^n (x_i+1))^{1/n}-1 = \sqrt[n]{(x_1+1)(x_2+1) \cdots (x_n+1)} -1


In Sphinx, ``math`` directives can include an optinal ``label`` which can be used to
reference a formula (in the same document) using the ``:eq:`` role.


+--------------------------------------------+-----------------------------------------+
| ::                                         |                                         |
|                                            | .. math:: e^{i\pi} + 1 = 0              |
|   .. math:: e^{i\pi} + 1 = 0               |    :label: euler                        |
|      :label: euler                         |                                         |
|                                            | Euler's identity equation :eq:`euler`,  |
|   Euler's identity equation :eq:`euler`,   | as elected one of the most              |
|   as elected one of the most               | beautiful mathematical formulas.        |
|   beautiful mathematical formulas.         |                                         |
+--------------------------------------------+-----------------------------------------+


Raw
====

The ``raw`` directive can be used to include non-reST data.

+-----------------------------------+--------------------------------+
| ::                                |                                |
|                                   | .. raw:: html                  |
|   .. raw:: html                   |                                |
|                                   |    raw <b>html</b> <i>code</i> |
|      raw <b>html</b> <i>code</i>  |                                |
+-----------------------------------+--------------------------------+

There is also a ``raw`` role (inline) that can be used with the :ref:`role directive`
to have inline non-reST data. Find an example :ref:`below <inline html>`

.. _role directive:

Role
====

The ``role`` directive can be used to create new roles and to register them.
E.g. ``.. role:: custom`` creates a new role, named custom
which can be used as ``:custom:`some text```.

An interesting feature is that roles can inherit from a base role::

   .. role::<new role>(<base role>)
      <directives>

.. _inline html:

For example, we can create a role for inline HTML::

   .. role:: raw-html(raw)
      :format: html

.. role:: raw-html(raw)
   :format: html

and use it to include inline HTML code:


+-----------------------------------+--------------------------------+
| ::                                |                                |
|                                   | line :raw-html:`<br/>` break   |
|   line :raw-html:`<br/>` break    |                                |
+-----------------------------------+--------------------------------+



.. todo::

   Compound paragraph, Parsed literal block, Class, Container


----




***********************
Other Sphinx directives
***********************

Table of contents
=================

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
========

This role allow you to download files.
It is only included in output formats that allow it (like HTML).


+-----------------------------------+--------------------------------+
| ::                                |                                |
|                                   | :download:`conf.py`            |
|   :download:`conf.py`             |                                |
+-----------------------------------+--------------------------------+

Downloadable files are copied to the ``_downloads`` folder within the outuput folder.


Only
====

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
========

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
=====

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

----

.. _show code:

************
Showing code
************

.. highlight:: python

There are different directives to show code (we will focus on Python,
but is possible to use different languages).

Check `<http://www.sphinx-doc.org/es/stable/markup/code.html>`_ for more information.

Code role
=========

The code role marks its content as code in a formal language:

+-----------------------------+--------------------------+
| ::                          |                          |
|                             | :code:`print('hello')`   |
|    :code:`print('hello')`   |                          |
+-----------------------------+--------------------------+


.. _new code roles:

Although that might not be very helpful, you can use the :ref:`role directive <role directive>`
to create your own custom roles

::

   .. role:: python(code)
      :language: python

.. role:: python(code)
   :language: python

:python:`print('hello')`

+--------------------------------+-----------------------------+
| ::                             |                             |
|                                | :python:`print('hello')`    |
|    :python:`print('hello')`    |                             |
+--------------------------------+-----------------------------+

.. warning::

   Although this should work according to `docutils documentation <http://docutils.sourceforge.net/docs/ref/rst/roles.html#code>`_
   and `some other examples <https://stackoverflow.com/questions/10870719/inline-code-highlighting-in-restructuredtext>`_
   I have not been able to make it work.
   You can find related issues in `<https://stackoverflow.com/questions/21591107/sphinx-inline-code-highlight>`_,
   `<https://stackoverflow.com/questions/40598448/inline-code-highlighting-in-sphinx-rest>`_,
   `<https://stackoverflow.com/questions/10870719/inline-code-highlighting-in-restructuredtext>`_,
   `<https://stackoverflow.com/questions/21591107/sphinx-inline-code-highlight/21601271>`_,
   `<https://github.com/rst2pdf/rst2pdf/issues/467>`_

   The problem comes from the fact that `pygments <http://pygments.org/>`_
   generates a CSS file with the sort names (e.g. ``keyword`` is ``.k``)
   but the ``code`` directive generates the long ones.

.. https://bitbucket.org/klorenz/sphinxcontrib-inlinesyntaxhighlight/src

.. _code directive:

Code directive
==============

The reST *code* directive::

   .. code:: ‹language›
      :linenos:

      ‹body›


+-----------------------+--------------------+
| ::                    |                    |
|                       | .. code:: python   |
|    .. code:: python   |                    |
|                       |    print('hello')  |
|       print('hello')  |                    |
+-----------------------+--------------------+

Literal blocks
==============

In Sphinx, Python source code or interactive session can be use
directly as literal blocks::

   ::

      <code>

      >>> <code for interactive session>


+-----------------------+-----------------------+
| non interactive       | interactive           |
| ::                    | ::                    |
|                       |                       |
|    print('hello')     |    >>> print('hello') |
|    hello              |    hello              |
|                       |                       |
+-----------------------+-----------------------+

.. _hightlighted language:

By default Python is used as the language of literal blocks.
However this behaviour can be modified usign the
``highlight`` directive::

   .. highlight:: c

From that point on, any code in literal
blocks will be treated as C code
until the next ``highlight`` directive modifies it.

Also take a look at the `highlight_language
<http://www.sphinx-doc.org/es/stable/config.html#confval-highlight_language>`_
variable that can be used in the configuration.

Code-block directive
====================

When different code snippets in different languages
are display, the ``code-block`` directive can be used
to avoid modifying the language with the ``highlight``
directive:

+--------------------------+-----------------------+
| ::                       |                       |
|                          | .. code-block:: bash  |
|    .. code-block:: bash  |                       |
|                          |    echo TEST          |
|       echo TEST          |    TEST               |
|       TEST               |                       |
+--------------------------+-----------------------+

This is similar to the reST :ref:`code directive` but with more
options.

Some options that can be used with the *code-block* directive are:

- linenos: to number the lines
- emphasize-lines:
- caption:
- name:

+-----------------------------------+--------------------------------+
| ::                                |                                |
|                                   | .. code-block:: python         |
|    .. code-block:: python         |    :linenos:                   |
|       :linenos:                   |    :emphasize-lines: 1,3-4     |
|       :emphasize-lines: 1,3-4     |    :caption: function example  |
|       :caption: function example  |                                |
|                                   |    def f(val):                 |
|       def f(val):                 |        a=1                     |
|           a=1                     |        b=2                     |
|           b=2                     |        v=a+b+val               |
|           v=a+b+val               |        return v                |
|           return v                |                                |
|                                   |                                |
+-----------------------------------+--------------------------------+


Take a look at the `lexers <http://pygments.org/docs/lexers/>`_
that are supported.

Literalinclude
==============

This directive can also be used to show code.
It supports the same options of the code block,
as well as some others, like:

- language: to indicate the language
- lines: to show only parts of the file

::

   .. literalinclude:: conf.py
      :language: python
      :lines: 30-35
      :caption: sphinx extensions
      :emphasize-lines: 5


.. literalinclude:: conf.py
   :language: python
   :lines: 30-35
   :caption: sphinx extensions
   :emphasize-lines: 5


---------

.. [#titleref] It is the default interpreted text role.
   Tipically, they are combined with a :ref:`citation`, e.g.::

      `Design Patterns` [GoF95]_ is an excellent read.

