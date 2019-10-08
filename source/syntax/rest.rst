
.. highlight:: text

Other reST directives
=====================


.. _content table:

.. contents:: `Table of contents`
   :depth: 2
   :local:



Table of contents
-----------------

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
------------------

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
------------

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
-------

.. sidebar:: Sidebar Title
   :subtitle: Optional

   Body

Sidebars are like miniature documents.

Example::

   .. sidebar:: Sidebar Title
      :subtitle: Optional

      Body

Topic
-----

.. topic:: a topic

   is a self-contained idea that is separate
   from the flow of the document

Example::

   .. topic:: title

      the body is separated
      by a blank line



Admonitions
-----------

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
----

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
----

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
----

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

