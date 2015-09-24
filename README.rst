******************************
 Plone 5 Development Buildout
******************************

Working on a new Python_ package for Plone_ version 5?  Well, do this::

    mkdir my-new-package
    cd my-new-package
    alias bootstrap.py curl -LO '"http://downloads.buildout.org/2/bootstrap.py"'
    bootstrap.py

(Put that alias in your ~/.cshrc; modify as needed for non-csh shells.)  Add
your ``setup.py`` and source code.

Now you've got the latest Buildout_ boostrapper, so make this two-line
``buildout.cfg``::

    [buildout]
    extends = https://raw.github.com/nutjob4life/plone5-dev-buildout/1.0.0/buildout.cfg

(Substitute version numbers as appropraite.)

Then do your usual::

    python2.7 bootstrap.py
    bin/buildout

And thanks to the magic of `buildout.packagename`_ you've got

``bin/plone``
    A Zope instance with Plone 4, Pillow, and your in-development package
    ready to launch.
``bin/test``
    A Zope test runner with your in-development package ready to test.
``parts/omelette``
    Zope, Plone, and your own source code in a greppable tree.
``bin/python``
    A Python interpreter loaded up with Zope, Plone, and your package ready
    for experimentation.

And you didn't have to repeat your package name all over the place, just once in
your ``setup.py``.  Life is good.

.. References:
.. _Python: http://python.org/
.. _Plone: http://plone.org/
.. _Buildout: http://buildout.org/
.. _`buildout.packagename`: https://github.com/witsch/buildout.packagename
