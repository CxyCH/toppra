Installation
=================


Core functionality
--------------------------
TOPP-RA can be installed from source by the following steps:

.. code-block:: shell

   git clone https://github.com/hungpham2511/toppra && cd toppra/
   pip install -r requirements.txt --user
   python setup.py install --user

These lines implement the most basic functionalities, such as
parametrize trajectories subject to velocity and acceleration
constraints. Some advanced functionalities require `openrave`, `cvxpy`
and so on. See :doc:`installation` for the full instruction.

(Optional) qpoases
--------------------------------

It is possible to use `qpoases` instead of the default LP solver
`seidel` as solverwrapper.  Install `qpOASES
<https://projects.coin-or.org/qpOASES/wiki/QpoasesInstallation>`_ by
entering the following commands in the terminal:

.. code-block:: shell

   git clone https://github.com/hungpham2511/qpOASES
   cd qpOASES/ && mkdir bin && make
   cd interfaces/python/
   pip install cython
   python setup.py install --user
   
Advanced functionality 
--------------------------------------

In order to run some of the examples, it is necesssary to install
`openRAVE <https://github.com/rdiankov/openrave>`_. A good instruction
for installing this library on Ubuntu 16.04 can be found
`here <https://scaron.info/teaching/installing-openrave-on-ubuntu-16.04.html>`_.

*note*: the humanoid examples are not maintained.

..
   Multi-contact and torque bounds.  To use these functionality, the
   following libraries are needed:

   1. [openRAVE](https://github.com/rdiankov/openrave)
   2. [pymanoid](https://github.com/stephane-caron/pymanoid)

   `openRAVE` can be tricky to install, a good instruction for installing
   `openRAVE` on Ubuntu 16.04 can be
   found
   [here](https://scaron.info/teaching/installing-openrave-on-ubuntu-16.04.html).

   To install `pymanoid` locally, do the following
   ``` sh
   mkdir git && cd git
   git clone <pymanoid-git-url>
   git checkout 54299cf
   export PYTHONPATH=$PYTHONPATH:$HOME/git/pymanoid
   ```




Building docs
------------------------------

The lastest documentation is available at
`<https://hungpham2511.github.io/toppra/>`_. 

To build and view the documentation, install `sphinx
<http://www.sphinx-doc.org/en/stable/index.html>`_ then run the
following commands in the terminal

.. code-block:: shell

   cd <toppra-dir>/docs/
   make clean && make html
   <browser> build/index.html

Testing
-------------------------------

TOPP-RA uses :code:`pytest` for testing, which can be installed from
:code:`pip`.  To run all the tests, do:

.. code-block:: sh

   cd <toppra-dir>/tests/
   pytest -v

