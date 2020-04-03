Your First Test
================

We are going to test that our players can walk forward correctly.

::

    extends Sprite
    class_name Player

    const SPEED: int = 400

    func _process(delta: float) -> void:
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

Create a folder called ``tests`` in your Project's main folder then create a script named ``player.test.gd`` that extends ``WAT.Test``
and store it in that folder. This script is known as a ``Test Suite``.

The first thing we need to do is to give our test a title. By convention the title is written as ``Given a X`` where X is the class being tested. In this
case we're testing the ``Player`` class so following convention we will give it the name ``Given a Player``. 

::

    extends WAT.Test

    func title() -> String:
        return "Given A Player"

WAT will call this function and use the returned String internally. Similar to how _ready and _process work in Godot itself.


A ``Test Suite`` is a collection of ``Tests`` where each test is a unique function. In WAT these functions are prefixed with the term ``test``. This prefix
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

        # Assert
        var new_x_position = player.position.x
        asserts.is_true(previous_x_position < new_x_position, \
                         "Then they have moved to the right of the screen")

We seperate our test body into three distinct parts; Arrange, Act & Assert.

In the Arrange step we create an instance of our Player class and get its current position. This is our set of preconditions, we need a player
instance so we can move it and we need its current position so we can compare against our future position.

In the Act step we tell our player instance to walk_forward. This is the event or action that we're testing. We're testing to see if the walk_forward code
works as we expect it to do.

In the Assert step we get our new x position and check if it is greater than the older x position. This is our tests postcondition, what we need to
be true after the code has been executed for our test to pass. 

Click the Play button in WAT (near the top right of the bottom panel) and you should see this screen after a second.

.. image:: your_first_test_results.png

In the Assert step of our test body you will have noticed that we didn't use a simple ``print(previous_x_position < new_x_position)`` check like you may do in
a naive manual test, instead we called the ``is_true`` method of our ``asserts`` property. This is where Automated Testing starts proving its usefulness over
manual testing.

The asserts property is a list of functions that wrap common conditional checks. In addition to performing the check, these functions also allow us to add
a clear diagnostic message (the String we used in our test) which is then shown in our results tree with a green font and a checkmark if correct or 
a red cross and default white font if not. 

In the [introduction] we explained the conundrum manual testing presents to you by forcing you to choose either to have your code cluttered with 
print debug statements OR removing the tests after you've finished checking them only to have that code break down once again later when you no 
longer remember how you fixed it in the first place.

Automated Testing solves this by shifting all of these print debug statements to these Assertions and displaying them this in WAT's Result Tree.
Your production code is no longer cluttered with numerous print debug statements but you still have your tests! 
So if you do encounter a bug, any of your tests that fail may give you a greater idea about what happened. 
This is especially potent if you run your tests often and catch bugs early so you know the reason the code broke is something you just did!

In our test we used the basic ``is_true`` function but we could have also done either of these (among many others you can see at [assertions].

::

    asserts.is_greater_than(new_x_position, old_x_position, \
                             "Then they have moved to the right of the screen")

    asserts.is_less_than(old_x_position, new_x_position, \
                          "Then they have moved to the right of the screen")