Ray Tutorial
============

Setup
-----

1. **Install Ray** by following the `Ray installation instructions`_. Verify
   that the following works.

  .. code-block:: bash

    python ray/test/runtest.py


2. Clone the tutorial repository with

  .. code-block:: bash

    git clone https://github.com/ray-project/tutorial.git

3. Install the tutorial package with

  .. code-block:: bash

    cd tutorial
    python setup.py install

.. _`Ray installation instructions`: http://ray.readthedocs.io/en/latest/index.html

4. Install the following additional dependencies.

  .. code-block:: bash

    pip install tensorflow
    pip install gym

  Verify that you can run ``import tensorflow`` and ``import gym`` in a Python
  interpreter.


Exercises
---------

Each file ``exercises/exercise*.py`` is a separate exercise. Instructions are
written in each file. Each file should run without raising any exceptions.
Throughout these exercises, you may find the `Ray documentation`_ helpful.

**Exercise 1:** Define a remote function, and execute multiple remote functions
in parallel.

**Exercise 2:** Execute remote functions in parallel with some dependencies.

**Exercise 3:** Pass object IDs into tasks to construct dependencies between
tasks.

**Exercise 4:** Call remote functions from within remote functions.

**Exercise 5:** Use ``ray.wait`` to ignore stragglers. See the
`documentation for wait`_.

**Exercise 6:** Use ``ray.wait`` to process tasks in the order that they finish.
See the `documentation for wait`_.

**Exercise 7:** Use actors to share state between tasks. See the documentation
on `using actors`_.

**Exercise 8:** Use ``ray.put`` to avoid serializing and copying the same
object into shared memory multiple times.

**Exercise 9:** Parallelize a serial example that uses a neural net to perform
rollouts in a gym environment.

**Exercise 10:** Extract neural network weights from an actor on one process,
and set them in another actor. You may want to read the documentation on
`using Ray with TensorFlow`_.

**Exercise 11:** Specify that an actor requires some GPUs. For a complete
example that does something similar, you may want to see the `ResNet example`_.

.. _`Ray documentation`: http://ray.readthedocs.io/en/latest/?badge=latest
.. _`documentation for wait`: http://ray.readthedocs.io/en/latest/api.html#waiting-for-a-subset-of-tasks-to-finish.
.. _`using actors`: http://ray.readthedocs.io/en/latest/actors.html
.. _`using Ray with TensorFlow`: http://ray.readthedocs.io/en/latest/using-ray-with-tensorflow.html
.. _`ResNet example`: http://ray.readthedocs.io/en/latest/example-resnet.html


Longer Examples
---------------

Now that you've completed the basic exercises, some more involved exercises are
provided under ``examples/``.

**Block Distributed Matrix Algorithms:** Implement a distributed matrix
multiplication algorithm for block distributed matrices. For this example, run
``python examples/block_linear_algebra.py``.

**Hyperparameter Search:** Here, a serial implementation of random
hyperparameter search is provided. Modify this example to parallelize the
hyperparameter search and to start a new experiment whenever one finishes. For
this example, run ``python examples/hyperparameter_search.py``.

**Evolutionary Algorithms:** Here, a serial implementation of an evolutionary
algorithm for solving reinforcement learning problems is provided. Modify this
example to parallelize the implementation. For this example, run
``python examples/evolution_strategies.py``.
