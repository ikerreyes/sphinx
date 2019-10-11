
.. highlight:: text

Math
====

To use `mathematical expressions <http://www.sphinx-doc.org/en/stable/ext/math.html>`_,
you can use LaTeX expressions under the following directives:

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


In Sphinx, ``math`` directives can include an optional ``label`` which can be used to
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

Syntax
------

Math code in Sphinx uses LaTeX syntax.


.. contents::
   :local:

Symbols
*******

.. list-table:: Leters

   *  -  :math:`\alpha`
      -  ``\alpha``
      -  :math:`\beta`
      -  ``\beta``
   *  -  :math:`\gamma`
      -  ``\gamma``
      -  :math:`\Gamma`
      -  ``\Gamma``
   *  -  :math:`\delta`
      -  ``\delta``
      -  :math:`\Delta`
      -  ``\Delta``
   *  -  :math:`\epsilon`
      -  ``\epsilon``
      -  :math:`\varepsilon`
      -  ``\varepsilon``
   *  -  :math:`\theta`
      -  ``\theta``
      -  :math:`\Theta`
      -  ``\Theta``
   *  -  :math:`\eta`
      -  ``\eta``
      -  :math:`\kappa`
      -  ``\kappa``
   *  -  :math:`\lambda`
      -  ``\lambda``
      -  :math:`\Lambda`
      -  ``\Lambda``
   *  -  :math:`\mu`
      -  ``\mu``
      -  :math:`\nu`
      -  ``\nu``
   *  -  :math:`\xi`
      -  ``\xi``
      -  :math:`\pi`
      -  ``\pi``
   *  -  :math:`\rho`
      -  ``\rho``
      -  :math:`\sigma`
      -  ``\sigma``
   *  -  :math:`\phi`
      -  ``\phi``
      -  :math:`\Phi`
      -  ``\Phi``
   *  -  :math:`\psi`
      -  ``\psi``
      -  :math:`\Psi`
      -  ``\Psi``
   *  -  :math:`\omega`
      -  ``\omega``
      -  :math:`\Omega`
      -  ``\Omega``
   *  -  :math:`\varphi`
      -  ``\varphi``
      -  :math:`\hbar`
      -  ``\hbar``


.. list-table:: Operators

   *  -  :math:`\ne`
      -  ``\ne``
      -  :math:`\pm`
      -  ``\pm``
   *  -  :math:`\sim`
      -  ``\sim``
      -  :math:`\approx`
      -  ``\approx``
   *  -  :math:`\equiv`
      -  ``\equiv``
      -  :math:`\simeq`
      -  ``\simeq``
   *  -  :math:`\leq`
      -  ``\leq``
      -  :math:`\geq`
      -  ``\geq``
   *  -  :math:`\mid`
      -  ``\mid``
      -  :math:`\parallel`
      -  ``\parallel``
   *  -  :math:`\|`
      -  ``\|``
      -  :math:`\perp`
      -  ``\perp``
   *  -  :math:`\lim`
      -  ``\lim``
      -  :math:`\Pr`
      -  ``\Pr``
   *  -  :math:`\neg`
      -  ``\neg``
      -
      -

.. list-table:: Decorators

   *  -  :math:`\hat{a}`
      -  ``\hat{a}``
      -  :math:`\tilde{a}`
      -  ``\tilde{a}``
   *  -  :math:`\bar{a}`
      -  ``\bar{a}``
      -  :math:`\vec{a}`
      -  ``\vec{a}``
   *  -  :math:`\overline{abc}`
      -  ``\overline{abc}``
      -  :math:`\overrightarrow{abc}`
      -  ``\overrightarrow{abc}``
   *  -  :math:`\widehat{abc}`
      -  ``\widehat{abc}``
      -  :math:`\dot{a}`
      -  ``\dot{a}``



.. list-table:: Set symbols

   *  -  :math:`\in`
      -  ``\in``
      -  :math:`\notin`
      -  ``\notin``
   *  -  :math:`\emptyset`
      -  ``\emptyset``
      -  :math:`\varnothing`
      -  ``\varnothing``
   *  -  :math:`\cap`
      -  ``\cap``
      -  :math:`\cup`
      -  ``\cup``


.. list-table:: Other symbols

   *  -  :math:`\cdot`
      -  ``\cdot``
      -  :math:`\cdots`
      -  ``\cdots``
   *  -  :math:`\ldots`
      -  ``\ldots``
      - :math:`\vdots`
      -  ``\vdots``
   *  -  :math:`\ddots`
      -  ``\ddots``
      -  :math:`\times`
      -  ``\times``
   *  -  :math:`\rfloor`
      -  ``\rfloor``
      -  :math:`\lrcorner`
      -  ``\lrcorner``
   *  -  :math:`\infty`
      -  ``\infty``
      -  :math:`\prime`
      -  ``\prime``




Fonts
-----

.. list-table::

   *  -  :math:`\mathcal{A}`
      -  ``\mathcal{A}``
      -  :math:`\mathbb{A}`
      -  ``\mathbb{A}``
   *  -  :math:`\mathbf{A}`
      -  ``\mathbf{A}``  [#mathbf]_
      -  :math:`\boldsymbol{\alpha}`
      -  ``\boldsymbol{\alpha}``


Functions
---------

.. list-table::

   *  -  :math:`\min`
      -  ``\min``
      -  :math:`\max`
      -  ``\max``
   *  -  :math:`\lim`
      -  ``\lim``
      -  :math:`\sin`
      -  ``\sin``
   *  -  :math:`\cos`
      -  ``\cos``
      -  :math:`\tan`
      -  ``\tan``
   *  -  :math:`\exp`
      -  ``\exp``
      -  :math:`\log`
      -  ``\log``
   *  -  :math:`\ln`
      -  ``\ln``
      -  :math:`\arg`
      -  ``\arg``
   *  -  :math:`\sum`
      -  ``\sum``
      -  :math:`\int`
      -  ``\int``


Styling equations
*****************

**Align** equations to the left with ``align``

+---------------------------------------------------------------+------------------------------------------------------------------+
| ::                                                            |                                                                  |
|                                                               |     .. math::                                                    |
|     .. math::                                                 |                                                                  |
|                                                               |        \begin{align}                                             |
|        \begin{align}                                          |        &S = {A,B,C} \\                                           |
|        &S = {A,B,C} \\                                        |        &P(3, 2) = 6; \quad \{AB, AC, BA, BC, CA, CB\} \\         |
|        &P(3, 2) = 6; \quad \{AB, AC, BA, BC, CA, CB\} \\      |        \end{align}                                               |
|        \end{align}                                            |                                                                  |
+---------------------------------------------------------------+------------------------------------------------------------------+


Control the **size** of brackets and parentheses with:
``\big``, ``\Big``, ``\bigg``, ``\Bigg``

.. list-table::

   *  -  :math:`\big(`
      -  ``\big(``
      -  :math:`\Big]`
      -  ``\Big]``
   *  -  :math:`\bigg\{`
      -  ``\bigg\{``
      -  :math:`\Bigg \rangle`
      -  ``\Bigg \rangle``


Create a function with different steps using ``cases``:


+-------------------------------------------+-------------------------------------+
| ::                                        |                                     |
|                                           |     .. math::                       |
|     .. math::                             |                                     |
|                                           |        \kappa = \begin{cases}       |
|        \kappa = \begin{cases}             |        0 & \text{if censored} \\    |
|        0 & \text{if censored} \\          |        1 & \text{if not censored}   |
|        1 & \text{if not censored}         |      \end{cases}                    |
|        \end{cases}                        |                                     |
+-------------------------------------------+-------------------------------------+


----

https://en.wikipedia.org/wiki/Wikipedia:LaTeX_symbols

https://tex.stackexchange.com/questions/145657/align-equation-left

https://www.overleaf.com/learn/latex/Brackets_and_Parentheses

----

.. [#mathbf] ``\mathbf{A}`` does not work with other LaTeX symbols

