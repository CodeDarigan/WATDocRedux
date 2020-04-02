What is WAT?
=============

WAT is an automated testing plugin for the [Godot] game engine.

===========================
What is Automated Testing?
===========================

Have you ever been unsure if a function was returning the right value or even be called at all in the first place? 
And in your attempts to verify this you've written examples like the following

::

    var damage: int = attacker.calculate_damage()
    print(damage)

::

    func calculate_damage() -> int:
        print("calculate_damage was called")
        // code

::

    func battle(player: Object, attacker: Object) -> void:
        // code
        var damage: int = attacker.calculate_damage()
        var before_damage_check = player.health
        player.take_damage(damage)
        print(player.health == before_damage_check - damage)

All of the previous code examples are a naive form of [Unit Tests]. 

These tests are fine by themselves but games are not simple (even the simple ones are not simple)! The problems start to begin
when your game grows in size and now your code is cluttered with print statements everywhere! You start to have to needlessly spend your
mental energy on figuring out which code is game code and which code is test code.

You could choose to remove the old tests but then when a bug appears it may have been useful to have those tests just to make sure that
isn't what's causing the bug. Ask yourself if you have ever solved a bug only for it to reappear later when you no longer remember how
to fix it!

Automated Testing provides solutions for this by allowing you create scripts known as [Test Suites] isolated from your game code
with a number of methods known as [Tests] that you can run at the click of a button. 

Results are displayed inside a Godot Dock when you run tests in WAT 

[Results Panel]