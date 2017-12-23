Project templates gallery
=========================

A simple project template prepared to be used as a service or a Django app.
Contains a `Dockerfile` leveraging the included `setup.py` file.
Aimed at projects that are meant to be one-app-per-service but more apps can be easily added

`One app per service template <https://github.com/pkucmus/django-project-template>`_

Template usage:

.. code-block:: bash

    django-admin startproject --template=https://github.com/pkucmus/django-project-template/archive/master.zip --extension py,md,Dockerfile {{ project_name }}

Quick runserver:

.. code-block:: bash

    cd /path/to/project
    docker build -t {{ project_name }} -f devel.Dockerfile .
    docker run -it --name {{ project_name }}_run_1 -p 8000:8000 -v $(pwd)/src/{{ project_name }}:/srv/app/{{ project_name }} {{ project_name }}
