Using The CLI
==============

You can run WAT from the command line by navigating to your project's root directory and then
entering the command: "godot addons/WAT/cli.tscn -?" where ? is one of the following commands

*********
Commands
*********

* run_all

    Runs all tests in your test directory

* run_dir=?

    Runs all tests in ? where ? is a subdirectory

    e.g run_dir=res://tests/unit/

* run_script=?

    Runs ? where ? is a single test suite.

    e.g run_script=res://tests/unit/player.test.gd

* run_method=?

    Runs ? where is a single test method.

    e.g xxxx

* list_all

    Lists all test scripts in your tests folder

* list_dir=?

    Lists all tests in ? where ? is a subdirectory

    e.g list_dir=res://tests/unit/

****************
Repeating Tests
****************

To repeat a test x times, enter one of the commands above appended by =X where X
is the amount of times to repeat the test.

e.g run_all=2

This example will run all tests twice