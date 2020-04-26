Utility Assertions
==================

Utility Assertions allow you to invoke special behaviour.

********
Methods
********

.. list-table::
    :widths: 100

    * - :ref:`asserts.that<asserts.that>`
    * - :ref:`asserts.fail<asserts.fail>`

********************
Method Descriptions
********************

.. _asserts.that:

* **assert.that** (obj: Object, method: String, args: Array, context: String, pass: String, fail: String):

    Calls method on obj with args. You can choose to passed in a ready to be formatted string for the pass and failed messages (that
    are typically shown underneath the assertion context message in the display).

    E.g

        ::

            var player = Player.new()
            var weapon = Weapon.new()
            player.equip(weapon)
            assert.that(player, "is_connected", ["attack", weapon, "_on_player_attacked"], 
            "Player can attack", "%s.%s is connected to %s.%s", "%s.%s is not connected to %s.%s")

        The formatted strings should show as "Object.signal is (not) connected to Object.method".

-----------------------------------

.. _asserts.fail:

* **asserts.fail** (context: String = "") -> void:

    An assert that always fail with an optional context message for unimplemented
    and or unfinished tests.