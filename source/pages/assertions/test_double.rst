Test Double Assertions
======================

Assertions to be used on Test Doubles.

********
Methods
********

    * - :ref:`asserts.was_called<asserts.was_called>`
    * - :ref:`asserts.was_not_called<asserts.was_not_called>`
    * - :ref:`asserts.was_called_with_arguments<asserts.was_called_with_arguments>`

********************
Method Descriptions
********************

.. _asserts.was_called:

* **asserts.was_called** (test_double, method: String, context: String)

    Asserts that method was called on test_double.

----------------------

.. _asserts.was_not_called:

* **asserts.was_not_called** (test_double, method: String, context: String)

    Asserts that method was not called on test_double.

----------------------

.. _asserts.was_called_with_arguments:

* **asserts.was_called_with_arguments** (test_double, method: String, args: Array, context: String)

    Asserts that method was called on test_double with args

    The order of arguments must be exact. If you don't care about any particular argument, you can use the
    any() method from the test script that returns a placeholder that is skipped.