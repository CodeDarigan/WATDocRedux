C# API Differences
===================

* You still extend from WAT.Test (WAT is a namespace)
* func title -> public override String Title
* func start() -> public override void Start()
* func pre() -> public override void Pre()
* func post() -> public override void Post()
* func end() -> public override void End()
* described -> Described
* Assertions are PascalCase (check addons/WAT/core/assertions/Assertions.cs)
* Yield Methods work with await ToSignal(until_x())
* Add the [Test] Attribute to test Methods (instead of prefixing the names with test)
* Add the [RunWith(arguments)] Attribute to Parameterized Tests (and pass them through the method)
* TestSuiteOfSuites is not implemented in C# (yet)
* PoolArrays Assertions were removed
* Test Doubles don't exist (C# is a big language, this may take work)

*********************
Installing WAT-Sharp
*********************

Add the WAT folder from https://github.com/CodeDarigan/WATSharp to your addons folder

In your csproj file add the following scripts;

* <Compile Include="addons\WAT\core\assertions\Assertions.cs" />
* <Compile Include="addons\WAT\core\test\Recorder.cs" />
* <Compile Include="addons\WAT\core\test\Test.cs" />

*********
Examples
*********

You can find WAT-Sharp's own simple TestSuite at https://github.com/CodeDarigan/WATSharp/tree/master/tests
which should also provide as fairly reasonable documentation on how to use C# features