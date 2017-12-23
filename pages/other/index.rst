Other useful commands
=====================


Watch for a file change and execute a command on a `modify` event

    I'm using this one to rebuild this Sphinx page automatically after saving a file.

    -- Paweł

.. code-block:: bash

    while inotifywait -qr -e modify .; do { command_to_execute_on_change }; done


