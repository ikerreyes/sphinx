
.. _show code:


Showing code
============

.. highlight:: python

There are different directives to show code (we will focus on Python,
but is possible to use different languages).

Check `<http://www.sphinx-doc.org/es/stable/markup/code.html>`_ for more information.

Code role
---------

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
--------------

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
--------------

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

The ``highlight`` can include the ``linenothreshold`` option
that produce line number for code blocks longer than the
value specified::

    .. highlight:: c
       :linenothreshold: 5

Also take a look at the `highlight_language
<http://www.sphinx-doc.org/es/stable/config.html#confval-highlight_language>`_
variable that can be used in the configuration.

Code-block directive
--------------------

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
--------------

This directive can also be used to show code.
It supports the same options of the code block,
as well as some others, like:

- language: to indicate the language
- lines: to show only parts of the file

::

   .. literalinclude:: ../conf.py
      :language: python
      :lines: 30-34
      :caption: sphinx extensions
      :emphasize-lines: 4


.. literalinclude:: ../conf.py
   :language: python
   :lines: 30-34
   :caption: sphinx extensions
   :emphasize-lines: 4

