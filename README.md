[![Build Status](http://ci.eclipse.org/xacc/buildStatus/icon?job=xacc-vqe-bayesopt-ci)](http://ci.eclipse.org/xacc/job/xacc-vqe-bayesopt-ci/)

# XACC-VQE Plugin to perform Bayesian Optimization

Installation
------------
With the XACC framework installed, users can choose a couple ways to install these plugins:

Using CMake and Make without Python support
```bash
$ mkdir build && cd build
$ cmake .. -DXACC_DIR=$HOME/.xacc (or wherever you installed XACC)
$ make install 
```
or with Python support
```bash
$ cmake .. -DXACC_DIR=$(python -m pyxacc -L)
$ make install
```

Documentation
-------------

* [XACC Website and Documentation ](https://xacc.readthedocs.io)

Questions, Bug Reporting, and Issue Tracking
--------------------------------------------

Questions, bug reporting and issue tracking are provided by GitHub. Please
report all bugs by creating a new issue with the bug tag. You can ask
questions by creating a new issue with the question tag.

License
-------

XACC-VQE BayesOpt is licensed - [BSD 3-Clause](LICENSE).
