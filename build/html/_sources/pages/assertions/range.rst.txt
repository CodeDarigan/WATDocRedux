Range Assertions
================

********
Methods
********

.. list-table::
    :widths: 100

    * - :ref:`asserts.is_in_range<asserts.is_in_range>`
    * - :ref:`asserts.is_not_in_range<asserts.is_not_in_range>`

********************
Method Descriptions
********************

.. _asserts.is_in_range:

* **asserts.is_in_range** (value, low, high, context: String)

    Asserts that value is in range(low, high).

    Note: Range is exclusive. 9 in 1-10 is a success but 10 in 1-10 is
    a fail.

--------

.. _asserts.is_not_in_range:

* **asserts.is_not_in_range** (value, low, high, context: String)

    Asserts that value is not in range(low, high).

    Note: Range is exclusive. e.g 10 in 1-10 is a success.