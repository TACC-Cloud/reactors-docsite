Start a Project
===============

**Concept:** The Abaco CLI will automatically generate a skeleton for your Reactor that is preconfigured for easy building, testing, and deployment. This same structure lends itself well to adopting continuous integration and unit testing if you should need those practices. The list of templates is limited at present, and constrained to Python language support. This is expected to change in the future. In addition, it is expected that deeper integration with Github and Gitlab will be added to the Reactors workflow.

Let's go!
---------

Run ``abaco init``, specifying language (``python2`` or ``python3`` for now) and a URL-safe name. A good rule-of-thumb is to name a Reactors project like one would a Git repository.

.. code-block:: console

   $ abaco init -l python3 -n hello_world
   $ ls hello_world/
   Dockerfile       config.yml      reactor.py      requirements.txt
   TEMPLATE.md      message.jsonschema  reactor.rc      secrets.json.sample

Details on what each project file does are provided in the User Guide.
