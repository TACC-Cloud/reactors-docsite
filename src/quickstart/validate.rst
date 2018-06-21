Validate deployment
===================

**Concept:** A Reactor that has been deployed successfully will be accessible via the ``actors`` API and will report a status of **SUBMITTED** while the function is being deployed, then **READY** when it is prepared to accept messages.

**Action:** List the new actor by its identifier

.. code-block:: console

   $ abaco ls e6rkEBlzJ8vG4

The expected response should resemble this JSON document:

.. code-block:: json
    :linenos:

    {
        "message": "Actor retrieved successfully.",
        "result": {
        "_links": {
          "executions": "https://api.sd2e.org/actors/v2/e6rkEBlzJ8vG4/executions",
          "owner": "https://api.sd2e.org/profiles/v2/taco",
          "self": "https://api.sd2e.org/actors/v2/e6rkEBlzJ8vG4"
        },
        "createTime": "2018-06-21 14:39:16.435800",
        "defaultEnvironment": {
          "_REACTORS_DONT_REVEAL": "This is a secret"
        },
        "description": "",
        "gid": 845005,
        "id": "e6rkEBlzJ8vG4",
        "image": "taco/hello_world:0.1",
        "lastUpdateTime": "2018-06-21 14:39:16.435800",
        "mounts": [
          {
            "container_path": "/work",
            "host_path": "/work",
            "mode": "rw"
          },
          {
            "container_path": "/corral",
            "host_path": "/corral/projects/TACC-Cloud",
            "mode": "rw"
          }
        ],
        "name": "hello_world",
        "owner": "taco",
        "privileged": false,
        "state": {},
        "stateless": false,
        "status": "READY",
        "statusMessage": " ",
        "tasdir": "05201/taco",
        "type": "none",
        "uid": 845005,
        "useContainerUid": false
        },
        "status": "success",
        "version": "0.8.0"
    }


Note that ``result.status`` is **READY** - this means the actor is ready to do work. If it reads **SUBMITTED**, deployment is stil in progress. If it reads **ERROR**, a problem has been encountered.

