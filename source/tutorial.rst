
Sphinx tutorial
===============

In this tutorial we will see how to create documentation
for a Python project.

#. Get an :ref:`overview <overview>` of Sphinx and reST.

#. Create a new project and add a simple Python script to it::

      def f(a):
         return a*3

   We will assume this is our Python project code.

#. Launch sphinx and :ref:`configure it <start sphinx>`.

   Take a look at the ``docs`` folder and check :ref:`what are those files for <setup>`.

#. Compile your docs using the :file:`Makefile`:

   .. code:: bash

      make html

   and open the build files in your browser.

#. Add a new :file:`.rst` file in the **source** directory.
   For now in can contain only one sentence.

   Include the file in the ``toctree`` to make it visible.

   .. warning::

      The document must contain a title to be included.

#. Play around with the different
   :ref:`roles and directives <markup constructs>` that you can use.
   Take a look at the :ref:`code directives <show code>`.

   .. note::

      Remember to build your *docs* to make the changes visible
      in the HTML output.

#. Change the configuration file to include the :ref:`Read the Docs HTML theme <config html>`.

   .. note::

      The theme can be installed through conda:

      .. code:: bash

         conda install sphinx_rtd_theme

#. Add a :ref:`docstring <docstrings>` to the function.
   If you are using ``PyCharm`` change the default
   to **Google format**::

      def f(a):
          """
          Multipy by three

          Args:
              a (int): integer

          Returns:
              int: Three times value

          """
          return a*3

#. Make you code :ref:`accessible to Sphinx <apidocs>`
   and generate the docs automatically with
   :ref:`sphinx apidocs <apidocs>`

   .. warning::

      Run the command from the main project directory
      and not from the docs folder, to make your
      Python scripts accessible.

#. Now that Sphinx has created the :file:`.rst` files
   with your *apidocs*, add them to your toctree
   using the :ref:`modules <apidocs modules>` file.

   .. note::

      If you have decided to go for the *Google docstrings*
      format, add the :ref:`napoleon extension <google docstrings>`


#. Add a *module docstring* in your script and
   :ref:`cross-reference <crossrefPy>`
   Python objects from the standard library::

      """
      This modules does not import anything from the
      standard library like :obj:`integer <int>`,
      :mod:`os` or :func:`~os.listdir`
      """

   .. note::

      You do not need to rerun the command to generate the
      *apidocs* as they read the docstrings directly
      from the script file.

#. Add cross reference to other Python libraries
   using :ref:`intersphinx <intersphinx>`::

      """
      :class:`~matplotlib.figure.Figure`
      """

Enjoy documenting your projects

----

There are few items left but they are still interesting:

- How to link :ref:`version from your project <version and release>`
  with the *docs* version

- Using IPython to execute code and show on the
  output with the :ref:`ipython directive <ipython>`.

- Publish your docs at :ref:`Read The Docs <RtD>`.

