.. Reactors Python SDK documentation
   sphinx-quickstart on Sun Jun 17 09:17:00 2018.

Reactors SDK
============

Nearly any language can be used to build functions for TACC's `Abaco <http://useabaco.cloud/>`_ serverless computing `platform <http://developer.tacc.cloud/abaco.html>`_. This is the documentation for a specific, opinionated approach that embeds a client-side Python2.7/3.6 support library called `Reactors <https://pypi.python.org/pypi/taccreactors>`_ in the container that hosts an Abaco function.

Reactors extends the Abaco Actors concept with:

- YAML-based configuration mechanism with environment overrides
- Support for first-class mocking and local-side testing
- Semantic aliases for Actors and other TACC.cloud API assets
- Helper methods for working with integrations like Slack and IFTTT
- Introspection of the actor's platform-level attributes
- Advanced logging with support for redacting sensitive text
- Optimized TACC.cloud API operations

.. toctree::
   :maxdepth: 2
   :caption: Quick Start

   src/quickstart/index

.. toctree::
   :maxdepth: 2
   :caption: User Guide

   src/user_guide/index

.. toctree::
   :maxdepth: 2
   :caption: Scenarios

   src/scenarios/index

.. toctree::
   :maxdepth: 2
   :caption: Resources

   src/resources/index

.. toctree::
   :maxdepth: 2
   :caption: Porting

   src/porting/index

.. toctree::
   :maxdepth: 2
   :caption: Contributing

   src/contribute/index

Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
