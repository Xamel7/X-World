## XUNITS

# Creating a unit test project

Start your Visual Studio, which brings you to the start up screen.Under "Get Started", click "Create a new project". With that you have taken your first steps to creating your project tests. In the drop down boxes, is where you can find what language(C# in this case), your platform, and your project type.Scroll until you reach "xUnit Test Project(.NET Core)". Click it, then hit "Next". Type a name into the "Project Name" box. Then, click "Create".

# Project File Review
TargetFramework specifies the target framework for your test project. By default this will be the latest version of .NET Core that your system supports (in this example, .NET 5.0). Later in this article, we will discuss running tests against multiple target frameworks.

IsPackable is here, though it is redundant (unit test projects cannot be packed by default). You can safely remove this line if you wish.

The xunit package brings in three child packages which include functionality that most developers want: xunit.core (the testing framework itself), xunit.assert (the library which contains the Assert class), and xunit.analyzers (which enables Roslyn analyzers to detect common issues with unit tests and xUnit.net extensibility).

The packages xunit.runner.visualstudio and Microsoft.NET.Test.Sdk are required for being able to run your test project inside Visual Studio as well as with dotnet test.

The coverlet.collector package allows collecting code coverage. If you don't intend to collect code coverage, you should remove this package reference.

# Learning to use Test Explorer

Test Explorer is the name of the window that lets you browse and run your tests from within Visual Studio. Open it by choosing Test > Test Explorer from the main menu. 

The toolbar of Test Explorer has buttons in several groups:

The first group contains buttons that are used for running tests, including the ability to run all tests, run selected tests, re-run the last tests, and re-run only the failed tests.
The second group contains buttons which allow filtering the list of tests based on current state (which includes "passed", "failed", and "not run").
The third group contains buttons which configure Test Explorer, including advanced options like changing processor architecture (x86, x64, or Auto) and automatically running tests after every successful build.
The main window of Test Explorer is split into two panes:

The left pane contains a tree view of the tests in your project (grouping criteria can be changed as you see fit). Columns can be configured to show details about the test, including things like the current state, how long the test took to run, metadata (traits) related to the test, and more.

As you select items in the tree view on the left pane, the right pane will provide information about your current selection, including test counts, outcomes, links to the source of the test, test output, and exception messages and stack traces for failed tests.

# Write your first tests

Edit UnitTest1.cs and replace the default file contents with this:

using Xunit;

namespace MyFirstUnitTests
{
    public class UnitTest1
    {
        [Fact]
        public void PassingTest()
        {
            Assert.Equal(4, Add(2, 2));
        }

        [Fact]
        public void FailingTest()
        {
            Assert.Equal(5, Add(2, 2));
        }

        int Add(int x, int y)
        {
            return x + y;
        }
    }
}
Now let's go run the tests again and see what happens:



We purposefully wrote both a passing and failing test, and we can see that the results reflect that. By clicking on the failed test, we can see a link both to the top of the unit test (at line 14), but also the failure message (we expected 5 but got 4) as well as a link to the exact line where the failure occurred (line 16).

# Write your first theory
You may have wondered why your first unit tests use an attribute named [Fact] rather than one with a more traditional name like Test. xUnit.net includes support for two different major types of unit tests: facts and theories. When describing the difference between facts and theories, we like to say:

Facts are tests which are always true. They test invariant conditions.

Theories are tests which are only true for a particular set of data.

A good example of this is testing numeric algorithms. Let's say you want to test an algorithm which determines whether a number is odd or not. If you're writing the positive-side tests (odd numbers), then feeding even numbers into the test would cause it fail, and not because the test or algorithm is wrong.

Let's add a theory to our existing facts (including a bit of bad data, so we can see it fail):

[Theory]
[InlineData(3)]
[InlineData(5)]
[InlineData(6)]
public void MyFirstTheory(int value)
{
    Assert.True(IsOdd(value));
}

bool IsOdd(int value)
{
    return value % 2 == 1;
}

Although we've only written 3 test methods, the test runner actually ran 5 tests; that's because each theory with its data set is a separate test. Note also that the runner tells you exactly which set of data failed, because it includes the parameter values in the name of the test. The Test Explorer UI even shows a new level in the tree, as each row of data becomes a test result underneath its test method.

Running tests against multiple target frameworks
Sometimes, you want to write tests and ensure they run against several target application platforms. The xUnit.net test runner that we've been using supports .NET Core 1.0 or later, .NET 5.0 or later, and .NET Framework 4.5.2 or later. With a single test project, we can have our tests run against multiple target frameworks. Open the .csproj file and make the following change.

Test Explorer supports any combination of .NET Core (including .NET 5+) and .NET Framework targets. You can even include multiple versions of the same target framework (for example, it's legal to have something like <TargetFrameworks>net452;net461;net48;netcoreapp2.1;netcoreapp3.1;net5.0</TargetFrameworks>). Application authors will typically only use a single target framework, related to the target framework the application is intended to run on. Library authors are more likely to use several target frameworks, to ensure their tests run successfully on all supported target frameworks.