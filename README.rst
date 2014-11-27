===================
tychoish.com README
===================

``tychoish.com`` is a personal blog, written by Sam Kleinman. Topics
include software development (build systems, infrastructure, technical
documentation), participatory music and dance (contra, morris, sacred
harp, etc.), science fiction literature, hand knitting, and
historicism.

You can see the rendered content at `tychoish.com
<http://www.tychoish.com/>`_. I look forward to your comments! This
document describes how to build the site.

Dependencies
------------

The site uses a `Sphinx <http://sphinx-docs.org>`_ based build system
that uses `ablog <http://ablog.readthedocs.org/en/latest/>`_ to handle
the blog structure and `giza <https://pypi.python.org/pypi/giza>`_ to
automate the build and deployment process. Installing ``ablog`` and
``giza`` will install all other required dependencies: ::

   pip install giza ablog alabaster

Build the Site
--------------

To build the documentation for testing use the following command: ::

   giza make html

This is a simple wrapper around the following operation:

   giza sphinx -b html

You will find the build artifacts in the ``build/<branch>/html``
directory.

Deploy the Site
---------------

To test the production version of the site, use one of the following
(equivalent) commands: ::

   giza make publish
   giza sphinx -b publish

The staged document "document root" of the built site is
``build/public/<branch>/``. You can deploy the build with the
following command: ::

   giza deploy -t push

You can combine the building and deploying operations using one of the
following commands: ::

   giza make push
   giza push -d push

Contribute
----------

Please feel free to submit pull requests or open `issues
<https://github.com/tychoish/tychoish.com/issues>`_ for corrections or
follow up. Comments on the blog are also welcome.
