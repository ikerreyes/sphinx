

.. Foreword


Before starting
===============

.. _overview:

General view
------------

`Sphinx`_ is a tool to create documentation.
Although it was originally created for Python, it supports other languages as well.

Sphinx uses `reStructuredText <http://docutils.sourceforge.net/rst.html>`_ as markup language.
:abbr:`reST (reStructuredText)` files have the *.rst* extension.
This language is simple. It basically contains 2 types of structures:

   #. Inline markup:

      .. code-block:: rst

         e.g. using ``*`` for *emphasis*

   #. Explicit construct (roles and directives):
      Used to construct complex structures like admonitions. E.g.::

         .. note:: A note

      is displayed as:

      .. note:: A note

The `reST markup specification <http://docutils.sourceforge.net/docs/ref/rst/restructuredtext.html>`_
contains all the reST syntax.
The *reST* markup is defined in the `docutils project <http://docutils.sourceforge.net/>`_.
This project includes also a text processor. You can try it online on http://rst.ninjs.org/ .
However, this project is only for single documents.

`Sphinx`_ compiles and links all the *.rst* files
to generate the documentation in different formats: *html*, *pdf*, *epub*...
However, **Sphinx** is not only a tool to process the |rst| files but also adds
new directives and interpreted text roles.
One of the most important directives added by Sphinx is the
`toctree <https://www.sphinx-doc.org/en/master/usage/restructuredtext/directives.html?highlight=toctree#directive-toctree>`_
because it allows the interconnection of different documents.


Alternatives
************

Sphinx and reST have alternatives when it comes to write technical documentation.
For example, `Asciidoctor <https://asciidoctor.org>`_ uses the
`asciidoc syntax <https://asciidoctor.org/docs/asciidoc-syntax-quick-reference/>`_
to create HTML and other formats.
`Doxygen <http://www.doxygen.org/>`_ is also another useful tool to create technical documentation.

`Markdown <https://en.wikipedia.org/wiki/Markdown>`_
in a popular markup language (as reST) which is specially designed for HTML outputs.
It can be used with `MkDocs <http://www.mkdocs.org/>`_, and optionally `Doxygen <http://www.doxygen.org/>`_
and `even Sphinx <https://www.sphinx-doc.org/en/master/usage/markdown.html>`_.

When it comes to choose between *reST* and *markdown*,
**reST** seems to be a better choice according to:
http://www.zverovich.net/2016/06/16/rst-vs-markdown.html ,
https://eli.thegreenplace.net/2017/restructuredtext-vs-markdown-for-technical-documentation/
and
http://ericholscher.com/blog/2016/mar/15/dont-use-markdown-for-technical-docs/

**Markdown** is designed for the web and you can write HTML is the markup syntax is not enough.
Said that, it also has some issues.
The main one is probably the *lack of a standard*. There are many different
`"flavours" <https://github.com/commonmark/CommonMark/wiki/Markdown-Flavors>`_ incompatible between them.
The `common mark specication <http://spec.commonmark.org/>`_ is there to solve this problem,
but is still not widely used.
Moreover, the *invisible markup* might not be a good idea; e.g.:
When you do want to insert a ``<br />`` break tag using Markdown, you end a line with two or more spaces, then type return.

On the other hand **reST** is more standardized and uniform and it has built-in support for extensions
(and it is written in Python).
However, reST is not free of issues. A notable one is that nested markup is not supported
(`yet <http://docutils.sourceforge.net/docs/dev/todo.html#nested-inline-markup>`_).


.. note:: If you need to switch your documents from one markup to another you can use `pandoc <https://pandoc.org/>`_


Placing documentation in the project
------------------------------------

The suggested place to put the documentation is in a separate folder
named *doc* or *docs* just below the project main folder.

The structure of a Python project is open and depends on the developers.
One of the recommended ways is as follows::

   project/
   |
   |-- project/
   |   |-- package/
   |   |   |-- __init__.py
   |   |   |-- module.py
   |   |
   |   |-- __init__.py
   |   |-- main.py
   |
   |-- README.rst
   |-- setup.py

.. note::

   If your project has more modules and packages, put them
   under the project directory.

When adding documentation, the structure of the project will
end up in something similar to::

   project/
   |
   |-- docs/
   |   |-- build/
   |   |-- source/
   |   |   |-- _templates
   |   |   |-- _static
   |   |   |-- pkg/
   |   |   |-- index.rst
   |   |   |-- conf.py
   |   |-- Makefile
   |
   |-- project/
   |   |-- package\
   |   |   |-- __init__.py
   |   |   |-- module.py
   |   |
   |   |-- __init__.py
   |   |-- main.py
   |
   |-- README.rst
   |-- setup.py


.. _Sphinx: http://www.sphinx-doc.org/
