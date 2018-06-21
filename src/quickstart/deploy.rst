Deploy the Reactor
==================

**Concept:** Functions can be deployed with the ``abaco create`` CLI command using a Docker image that has been built and pushed to a public registry. This is a very flexible approach, but it requires the authorone to execute the same series of steps each time. The ``abaco deploy`` command implements a streamlined workflow that, with configuration guidance from ``reactor.rc``, automatically builds the image, pushes it, gathers environment variables, and deploys or updates the Reactor.

**Action:** Ensure the image builds correctly with a dry run

.. code-block:: console

   $ abaco deploy -R

    [INFO]   Build Options: --rm=true --pull
    Sending build context to Docker daemon  10.75kB
    Step 1/1 : FROM sd2e/reactors:python3
    python3: Pulling from sd2e/reactors
    Digest: sha256:789c9057306d618168193c75a6c47ca5c500bc6fcdb60dc30f27f9bf8b1af404
    Status: Image is up to date for sd2e/reactors:python3
    # Executing 5 build triggers
     ---> Using cache
     ---> Using cache
     ---> c06a54dcc66c
    Successfully built c06a54dcc66c
    Successfully tagged taco/hello_world:0.1
    [INFO] Stopping deployment as this was only a dry run!

**Action:** Deploy the Reactor

.. code-block:: console

   $ abaco deploy

    [INFO]   Build Options: --rm=true --pull
    Sending build context to Docker daemon  10.75kB
    Step 1/1 : FROM sd2e/reactors:python3
    python3: Pulling from sd2e/reactors
    Digest: sha256:789c9057306d618168193c75a6c47ca5c500bc6fcdb60dc30f27f9bf8b1af404
    Status: Image is up to date for sd2e/reactors:python3
    # Executing 5 build triggers
     ---> Using cache
     ---> Using cache
     ---> Using cache
     ---> Using cache
     ---> Using cache
     ---> c06a54dcc66c
    Successfully built c06a54dcc66c
    Successfully tagged taco/hello_world:0.1
    The push refers to repository [docker.io/taco/hello_world]
    f9dde2603ec7: Pushed
    87f9719c8a1d: Mounted from sd2e/reactors
    913edbb0371b: Mounted from sd2e/reactors
    0.1: digest: sha256:a944131700e2ae540dc76f2c1c2d72e3909fdfd287b42a505c339ff79615bac7 size: 7184
    [INFO] Pausing to let Docker Hub register that the repo has been pushed
    [INFO] Reading environment variables from secrets.json
    Successfully deployed actor with ID: e6rkEBlzJ8vG4

