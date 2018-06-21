Write some code
===============

**Concept:** An Abaco function is a script or binary that is set as the default command in a container, accepts a message and parameters from environment variables, and can (optionally) make use of a pre-authenticated Agave API client. Functions can be written in any language, but the Reactors Python SDK streamlines these processes and adds support for some experimental platform features.

**Action:** Replace the contents of ``reactor.py``

.. code-block:: python
   :linenos:

    from reactors.runtime import Reactor


    def main():
        """Main function"""
        r = Reactor()
        r.logger.info("I received: {}".format(r.context['raw_message']))
        r.logger.debug("This is a DEBUG message from actor {}".format(r.uid))
        r.logger.info("This is an INFO message from actor {}".format(r.uid))
        r.logger.warning("This is a warning from actor {}".format(r.uid))

        r.logger.info("Here's that secret value: {}".format(
            r.settings.dont_reveal))

    if __name__ == '__main__':
        main()

This example illustrates use of the ``Reactor`` object, specifically, its *settings*, *context*, and *logging* functions. More features and use cases are described in the User Guide and Scenarios sections.
