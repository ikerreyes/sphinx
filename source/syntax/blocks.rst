
.. highlight:: text

Blocks
======


Literal
-------

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
----

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
------

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
