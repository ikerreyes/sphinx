
.. _crossrefPy:

Cross referencing Python objects
================================

When writing your docs, it is usually helpful to have cross references
to Python objects.

For cross-referencing Python objects, take a look at the `possible roles <http://www.sphinx-doc.org/en/stable/domains.html#cross-referencing-python-objects>`_.

Cross reference syntax takes one of these formats:

- ``:role:`target```
- ``:role:`title <target>```

Additonally,

- Prefix the content with ``!`` to avoid creating a link.
- Prefix the content with ``~`` to the link text will only be the last component of the target.
  For example, ``:py:meth:`~Queue.Queue.get``` will refer to ``Queue.Queue.get``
  but only display ``get`` as the link text.
  This does not work with all cross-reference roles, but is domain specific.

The ``py`` that precedes each identifier refers to the `domain <http://www.sphinx-doc.org/en/stable/domains.html#sphinx-domains>`_.
In this case it implies the `Python domain <http://www.sphinx-doc.org/en/stable/domains.html#the-python-domain>`_.
The Python domain is the default one, but it can be modified using
the `default-domain <http://www.sphinx-doc.org/en/stable/domains.html#directive-default-domain>`_ directive
or
the config value `primary_domain <http://www.sphinx-doc.org/en/stable/config.html#confval-primary_domain>`_.

When cross referencing an object of the default domain, it is not required to use the domain.
E.g. if Python is the default domain ``:py:meth:`~Queue.Queue.get``` is
equivalent to ``:meth:`~Queue.Queue.get```.


.. note::

   To be able to cross reference object from different projects, take a look at
   :ref:`linking to other projects <intersphinx>`.
