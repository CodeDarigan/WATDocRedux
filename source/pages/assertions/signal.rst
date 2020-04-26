Signal Assertions
=================

Insert Something Here About Requiring Watching Signals

********
Methods
********

.. list-table::
    :widths: 100

    * - :ref:`asserts.signal_was_emitted<asserts.signal_was_emitted>`
    * - :ref:`asserts.signal_was_emitted_x_times<asserts.signal_was_emitted_x_times>`
    * - :ref:`asserts.signal_was_not_emitted<asserts.signal_was_not_emitted>`
    * - :ref:`asserts.signal_was_emitted_with_arguments<asserts.signal_was_emitted_with_arguments>`

********************
Method Descriptions
********************

.. _asserts.signal_was_emitted:

* **asserts.signal_was_emitted** (emitter: Object, _signal: String, context: String)

    Asserts that emitter emitted _signal at least once.

---

.. _asserts.signal_was_emitted_x_times:

* **asserts.signal_was_emitted_x_times** (emitter: Object, _signal: String, x: int, context: String)

    Asserts that emitter emitted _signal exactly x times.

---

.. _asserts.signal_was_not_emitted:

* **asserts.signal_was_not_emitted** (emitter: Object, _signal: String, context: String)

    Asserts that emitter did not emit _signal at all.

.. _asserts.signal_was_emitted_with_arguments:

* **asserts.signal_was_emitted_with_arguments** (emitter: Object, _signal: String, args: Array, context: String)

    Asserts that emitter emitted signal with args at least once.