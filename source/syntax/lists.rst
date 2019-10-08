
.. highlight:: text

Lists
=====

Bulleted
--------

- Bullets are "-", "*" or "+".
  Continuing text must be aligned after the bullet and whitespace.

   - A blank line before the first and after the last items are required.
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
----------

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
----------

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
----------

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
-----

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
-------

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

Note that characters within the options are limited.
See the `reST docs for more details <http://docutils.sourceforge.net/docs/ref/rst/restructuredtext.html#option-lists>`_.
