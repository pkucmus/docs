Install a "clean" Python
========================

You may want to install additional libraries before compiling.

.. code-block:: bash

    sudo apt-get install -y \
        build-essential \
        libsqlite3-dev \
        libbz2-dev \
        zlib1g-dev \
        libssl-dev \
        libjpeg-dev

This will install Python in your `/opt` directory

.. code-block:: bash

    VAR=3.6.4  # set this to the newest Python 3 installation available on python.org
    cd /tmp
    wget https://www.python.org/ftp/python/$VAR/Python-$VAR.tgz
    tar -xzf Python-$VAR.tgz
    cd Python-$VAR/
    ./configure --prefix=/opt/python/$VAR
    make
    sudo make install

    sudo ln -s /opt/python/$VAR /opt/python/3.6

The lines below will install `pip` and `virtualenv` with `virtualenvwrapper`

.. code-block:: bash

    cd /tmp
    wget https://bootstrap.pypa.io/get-pip.py
    sudo /opt/python/3.6/bin/python get-pip.py

    sudo /opt/python/3.6/bin/pip install virtualenv
    sudo /opt/python/3.6/bin/pip install virtualenvwrapper

    echo "
    export VIRTUALENVWRAPPER_PYTHON=/opt/python/3.6/bin/python
    export VIRTUALENVWRAPPER_VIRTUALENV=/opt/python/3.6/bin/virtualenv
    export WORKON_HOME=~/.virtualenvs
    . /opt/python/3.6/bin/virtualenvwrapper.sh
    " >> ~/.bashrc
    source ~/.bashrc
