Configure the Project
=====================

**Concept:** The ``Dockerfile`` is a recipe to build the environment where our function will run. The function itself is implemented in ``reactor.py``. A Python module built into the base Docker image (``reactors``) works with ``config.yml`` and ``message.jsonschema`` to provide declarative configuration and validation. The ``requirements.txt`` file is used with ``pip`` in the container image to specify additional Python modules to install. Finally, the Reactors workflow uses ``reactor.rc`` to specify name, version, and other metadata, and ``secrets.json`` as a way to pass sensitive information into a function without committing it to the container image.

Step 1: Edit config.rc
----------------------

Naivigate to the project directory and edit ``DOCKER_HUB_ORG`` in ``config.rc`` to reflect either **your** Docker Hub username or an organization where you have push and pull access. For example, if a person with the Docker Hub username ``taco`` is a member of Docker Hub group ``cabana``, they can choose either ``taco`` or ``cabana`` as the value for ``DOCKER_HUB_ORG``

Step 2: Edit config.yml
-----------------------

Change the config file to read as follows.

.. code-block:: yaml

    ---
    logs:
      level: INFO
      token: ~
    dont_reveal: ~

Step 3: Create secrets.json
---------------------------

Write a JSON file with the following contents.

.. code-block:: json

    {"_REACTORS_DONT_REVEAL": "This is a secret"}

