Object Assertions
=================

Wrappers around boolean methods on the base object class. This is the only
class to have dedicated assertions because these methods are shared with every other
class through inheritance in Godot.

********
Methods
********

.. list-table::
    :widths: 100
    
    * - :ref:`asserts.object_does_not_have_meta<asserts.does_not_have_meta>`
    * - :ref:`asserts.object_does_not_have_method<asserts.does_not_have_method>`
    * - :ref:`asserts.object_does_not_have_user_signal<asserts.does_not_have_user_signal>`
    * - :ref:`asserts.object_has_meta<asserts.has_meta>`
    * - :ref:`asserts.object_has_method<asserts.has_method>`
    * - :ref:`asserts.object_has_user_signal<asserts.has_user_signal>`
    * - :ref:`asserts.object_is_blocking_signals<asserts.is_blocking_signals>`
    * - :ref:`asserts.object_is_connected<asserts.is_connected>`
    * - :ref:`asserts.object_is_freed<asserts.is_freed>`
    * - :ref:`asserts.object_is_not_blocking_signals<asserts.is_not_blocking_signals>`
    * - :ref:`asserts.object_is_not_connected<asserts.is_not_connected>`
    * - :ref:`asserts.object_is_not_freed<asserts.is_not_freed>`
    * - :ref:`asserts.object_is_not_queued_for_deletion<asserts.is_not_queued_for_deletion>`
    * - :ref:`asserts.object_is_queued_for_deletion<asserts.is_queued_for_deletion>`


********************
Method Descriptions
********************

.. _asserts.does_not_have_meta:

* **asserts.object_does_not_have_meta** (obj: Object, meta: String, context: String)

    Asserts that obj does not have meta.

--------------

.. _asserts.does_not_have_method:

* **asserts.object_does_not_have_method** (obj: Object, method: String, context: String)

    Asserts that obj does not have method.

------------

.. _asserts.does_not_have_user_signal:

* **asserts.obect_does_not_have_user_signal** (obj: Object, user_signal: String, context: String)

    Asserts that obj does not have user_signal
    
    Note: user signals are added via add_user_signal and are not the same as signals hardcoded into
    a class.

----------------

.. _asserts.has_meta:

* **asserts.object_has_meta** (obj: Object, meta: String, context: String)

    Asserts that obj has meta.

-----------

.. _asserts.has_method:

* **asserts.object_has_method** (obj: Object, method: String, context: String)

    Asserts that obj has method.

------------

.. _asserts.has_user_signal:

* **asserts.object_has_user_signal** (obj: Object, user_signal: String, context: String)

    Asserts that obj has user_signal.

    Note: user signals are added via add_user_signal and are not the same as signals hardcoded into
    a class.


-------------

.. _asserts.is_blocking_signals:

* **asserts.object_is_blocking_signals** (obj: Object, context: String)

    Asserts that obj is blocking signals.

-------------

.. _asserts.is_connected:

* **asserts.object_is_connected** (emitter: Object, _signal: String, receiver: Object, method: String, context: String)

    Asserts that emitter._signal is connected to receiver.method.

------------

.. _asserts.is_freed:

* **asserts.object_is_freed** (obj: Object)

    Asserts that obj is freed.

-------------

.. _asserts.is_not_blocking_signals:

* **asserts.object_is_not_blocking_signals** (obj: Object)

    Asserts that obj is not blocking signals.

-----------

.. _asserts.is_not_connected:

* **asserts.object_is_not_connected** (emitter: Object, _signal: String, receiver: Object, method: String, context: String)

    Asserts that emitter._signal is not connected to receiver.method.


--------------

.. _asserts.is_not_freed:

* **asserts.object_is_not_freed** (obj: Object)

    Asserts that obj is not freed.

------------

.. _asserts.is_not_queued_for_deletion:

* **asserts.object_is_not_queued_for_deletion** (obj: Object)

    Asserts that obj is not queued for deletion (from methods such as queue_free())

-------------

.. _asserts.is_queued_for_deletion:

* **asserts.object_is_qeued_for_deletion** (obj: Object)

    Asserts that obj is queued for deletion (from methods such as queue_free())