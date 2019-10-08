
.. highlight:: text

Inline markup
=============


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

---------

.. [#titleref] It is the default interpreted text role.
   Tipically, they are combined with a :ref:`citation`, e.g.::

      `Design Patterns` [GoF95]_ is an excellent read.

