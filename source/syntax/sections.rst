
.. highlight:: text

Sectioning
==========


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

However, in most cases you do not need so many level in the same
document, and as Sphinx decides de level automatically and you are not restricted to
those characters, I often use::

    ====

    ****

    ----

    ~~~~

Note that you can mix different characters in different documents.

.. _transitions explanation:

We can add transitions using ``----`` between two blank lines.

----

The line above is an example of transition.

.. important:: It is sometimes needed to have a blank line at the end of a document
   for Sphinx to build the sectioning hierarchy between documents properly.

