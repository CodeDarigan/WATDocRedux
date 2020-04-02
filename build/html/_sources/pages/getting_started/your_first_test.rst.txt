Your First Test
================

We are going to test our character's movement for this example.

::

    extends Sprite
    class_name Player

    const SPEED: int = 400

    func _process(delta: float) -> void:
        var velocity: Vector2 = Vector2(0, 0)
        if Input.is_key_pressed(KEY_D):
            walk_forward(delta)
        elif Input.is_key_pressed(KEY_A):
            walk_backward(delta)
	
    func walk_forward(delta: float = 0.1) -> void:
        _walk(delta, 1)
        
    func walk_backward(delta: float = 0.1) -> void:
        _walk(delta, -1)

    func _walk(delta: float, direction: int) -> void:
        position.x += direction * SPEED * delta

Create a folder called ``tests`` in your Project's main folder then create a script that extends ``WAT.Test`` named ``player.test.gd``
and store it in that folder. This script is known as a ``Test Suite``.

The first thing we need to do is to give our test a title. By convention the title is written as ``Given a X`` where X is the class being tested. In this
case we're testing the ``Player`` class so following convention we will give it the name ``Given a Player``. 

::

    extends WAT.Test

    func title() -> String:
        return "Given A Player"

WAT will call this function and use the returned String internally. Similar to how _ready and _process work in Godot itself.


A ``Test Suite`` is a collection of ``Tests`` where each test is a unique function. In WAT these function are prefixed with the term ``test``. This prefix
is necessary for WAT to seperate the functions that are tests from the functions that are not.

By convention the name of these test functions are written as "When X" where X is an event. In our case we
are testing when the player walks forward. So with the necessary test prefix and a convention together we get ``test_when_they_walk_forward``.

::

    extends WAT.Test

    func title() -> String:
        return "Given A Player"

    func test_when_they_walk_forward() -> void:
        describe("When they walk forward")

The first thing to do when creating a test function is to call the describe function and pass in a String with the name of the test. 
This is a necessary action otherwise our tests will crash. 
It also allows for us to use special characters if necessary such ``%`` or ``$`` and so on to give our tests a more precise name.

Let's step back for a moment before we write the test itself and just remind ourselves of what we're testing. In this case we want to make sure our instance of
the ``Player`` class can ``walk_forward`` but what are we looking for in our results? Well let's check the code again:

::

    func walk_forward(delta: float = 0.1) -> void:
        _walk(delta, 1)

    func walk_backward(delta: float = 0.1) -> void:
        _walk(delta, -1)

    func _walk(delta: float, direction: int) -> void:
        position.x += direction * SPEED * delta

In this case we're passing in a positive or negative position depending if we're walking forward or backward. Therefore if we're walking forward we're checking to see
if our x position has increased.

With our goal in mind, let's write our test!

::

    extends WAT.Test

    func title() -> String:
        return "Given A Player"

    func test_when_they_walk_forward() -> void:
        describe("When they walk forward")

    func test_when_they_walk_forward() -> void:
        describe("When they walk forward")

        # Arrange
        var player = Player.new()
        var previous_x_position = player.position.x

        # Act
        player.walk_forward()
        var new_x_position = player.position.x

        # Assert
        asserts.is_true(previous_x_position < new_x_position, "Then they have moved to the right of the screen")



