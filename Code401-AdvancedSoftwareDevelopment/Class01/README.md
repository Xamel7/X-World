## Exception Handling

## Lab01A/ Visual Studio Code

# Create the app
Create a .NET console app project named "HelloWorld".

Start Visual Studio Code.

Select File > Open Folder (File > Open... on macOS) from the main menu.

In the Open Folder dialog, create a HelloWorld folder and select it. Then click Select Folder (Open on macOS).

The folder name becomes the project name and the namespace name by default. You'll add code later in the tutorial that assumes the project namespace is HelloWorld.

In the Do you trust the authors of the files in this folder? dialog, select Yes, I trust the authors.

Open the Terminal in Visual Studio Code by selecting View > Terminal from the main menu.

The Terminal opens with the command prompt in the HelloWorld folder.

In the Terminal, enter the following command:

.NET CLI

Copy
dotnet new console --framework net7.0
The project template creates a simple application that displays "Hello, World" in the console window by calling the Console.WriteLine(String) method in Program.cs.

C#

Copy
Console.WriteLine("Hello, World!");
Replace the contents of Program.cs with the following code:

C#

Copy
namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello, World!");
        }
    }
}
The first time you edit a .cs file, Visual Studio Code prompts you to add the missing assets to build and debug your app. Select Yes, and Visual Studio Code creates a .vscode folder with launch.json and tasks.json files.

# Run the app
Run the following command in the Terminal:

.NET CLI

Copy
dotnet run
The program displays "Hello, World!" and ends.

# Enhance the app
Enhance the application to prompt the user for their name and display it along with the date and time.

Open Program.cs.

Replace the contents of the Main method in Program.cs, which is the line that calls Console.WriteLine, with the following code:

C#

Copy
Console.WriteLine("What is your name?");
var name = Console.ReadLine();
var currentDate = DateTime.Now;
Console.WriteLine($"{Environment.NewLine}Hello, {name}, on {currentDate:d} at {currentDate:t}!");
Console.Write($"{Environment.NewLine}Press any key to exit...");
Console.ReadKey(true);
This code displays a prompt in the console window and waits until the user enters a string followed by the Enter key. It stores this string in a variable named name. It also retrieves the value of the DateTime.Now property, which contains the current local time, and assigns it to a variable named currentDate. And it displays these values in the console window. Finally, it displays a prompt in the console window and calls the Console.ReadKey(Boolean) method to wait for user input.

NewLine is a platform-independent and language-independent way to represent a line break. Alternatives are \n in C# and vbCrLf in Visual Basic.

The dollar sign ($) in front of a string lets you put expressions such as variable names in curly braces in the string. The expression value is inserted into the string in place of the expression. This syntax is referred to as interpolated strings.

Save your changes.

 Important

In Visual Studio Code, you have to explicitly save changes. Unlike Visual Studio, file changes are not automatically saved when you build and run an app.

Run the program again:

.NET CLI

Copy
dotnet run
Respond to the prompt by entering a name and pressing the Enter key.

Press any key to exit the program.

# User Input
Get User Input
You have already learned that Console.WriteLine() is used to output (print) values. Now we will use Console.ReadLine() to get user input.

In the following example, the user can input his or hers username, which is stored in the variable userName.

User Input and Numbers
The Console.ReadLine() method returns a string. Therefore, you cannot get information from another data type, such as int.

# C# Methods
A method is a block of code which only runs when it is called.

You can pass data, known as parameters, into a method.

Methods are used to perform certain actions, and they are also known as functions.
# Create a Method
A method is defined with the name of the method, followed by parentheses (). C# provides some pre-defined methods, which you already are familiar with, such as Main(), but you can also create your own methods to perform certain actions.
# Call a Method
To call (execute) a method, write the method's name followed by two parentheses () and a semicolon;

## Lab01B

# Debugging
Use Debug build configuration
Debug and Release are .NET's built-in build configurations. You use the Debug build configuration for debugging and the Release configuration for the final release distribution.

In the Debug configuration, a program compiles with full symbolic debug information and no optimization. Optimization complicates debugging, because the relationship between source code and generated instructions is more complex. The release configuration of a program has no symbolic debug information and is fully optimized.

By default, Visual Studio Code launch settings use the Debug build configuration, so you don't need to change it before debugging.

# Set a breakpoint
A breakpoint temporarily interrupts the execution of the application before the line with the breakpoint is run.

Open the Program.cs file.

Set a breakpoint on the line that displays the name, date, and time, by clicking in the left margin of the code window. The left margin is to the left of the line numbers. Other ways to set a breakpoint are by pressing F9 or choosing Run > Toggle Breakpoint from the menu while the line of code is selected.

Visual Studio Code indicates the line on which the breakpoint is set by displaying a red dot in the left margin.

# Set up for terminal input
The breakpoint is located after a Console.ReadLine method call. The Debug Console doesn't accept terminal input for a running program. To handle terminal input while debugging, you can use the integrated terminal (one of the Visual Studio Code windows) or an external terminal. For this tutorial, you use the integrated terminal.

Open .vscode/launch.json.

Change the console setting from internalConsole to integratedTerminal:

JSON

Copy
"console": "integratedTerminal",
Save your changes.

# Start debugging
Open the Debug view by selecting the Debugging icon on the left side menu.

Select the green arrow at the top of the pane, next to .NET Core Launch (console). Other ways to start the program in debugging mode are by pressing F5 or choosing Run > Start Debugging from the menu.

Select the Terminal tab to see the "What is your name?" prompt that the program displays before waiting for a response.

Enter a string in the Terminal window in response to the prompt for a name, and then press Enter.

Program execution stops when it reaches the breakpoint and before the Console.WriteLine method runs. The Locals section of the Variables window displays the values of variables that are defined in the currently running method.

# Set a conditional breakpoint
The program displays the string that the user enters. What happens if the user doesn't enter anything? You can test this with a useful debugging feature called a conditional breakpoint.

Right-click (Ctrl-click on macOS) on the red dot that represents the breakpoint. In the context menu, select Edit Breakpoint to open a dialog that lets you enter a conditional expression.

Breakpoint context menu

Select Expression in the drop-down, enter the following conditional expression, and press Enter.

C#

Copy
String.IsNullOrEmpty(name)
Enter a conditional expression

Each time the breakpoint is hit, the debugger calls the String.IsNullOrEmpty(name) method, and it breaks on this line only if the method call returns true.

Instead of a conditional expression, you can specify a hit count, which interrupts program execution before a statement is run a specified number of times. Another option is to specify a filter condition, which interrupts program execution based on such attributes as a thread identifier, process name, or thread name.

Start the program with debugging by pressing F5.

In the Terminal tab, press the Enter key when prompted to enter your name.

Because the condition you specified (name is either null or String.Empty) has been satisfied, program execution stops when it reaches the breakpoint and before the Console.WriteLine method runs.

The Variables window shows that the value of the name variable is "", or String.Empty.

Confirm the value is an empty string by entering the following statement at the Debug Console prompt and pressing Enter. The result is true.

C#

Copy
name == String.Empty
Select the Continue button on the toolbar to continue program execution.

Select the Terminal tab, and press any key to exit the program and stop debugging.

Clear the breakpoint by clicking on the dot in the left margin of the code window. Other ways to clear a breakpoint are by pressing F9 or choosing Run > Toggle Breakpoint from the menu while the line of code is selected.

If you get a warning that the breakpoint condition will be lost, select Remove Breakpoint.

# Step through a program
Visual Studio Code also allows you to step line by line through a program and monitor its execution. Ordinarily, you'd set a breakpoint and follow program flow through a small part of your program code. Since this program is small, you can step through the entire program.

Set a breakpoint on the opening curly brace of the Main method.

Press F5 to start debugging.

Visual Studio Code highlights the breakpoint line.

At this point, the Variables window shows that the args array is empty, and name and currentDate have default values.

Select Run > Step Into or press F11.

Step-Into button

Visual Studio Code highlights the next line.

Select Run > Step Into or press F11.

Visual Studio Code runs the Console.WriteLine for the name prompt and highlights the next line of execution. The next line is the Console.ReadLine for the name. The Variables window is unchanged, and the Terminal tab shows the "What is your name?" prompt.

Select Run > Step Into or press F11.

Visual Studio highlights the name variable assignment. The Variables window shows that name is still null.

Respond to the prompt by entering a string in the Terminal tab and pressing Enter.

The Terminal tab might not display the string you enter while you're entering it, but the Console.ReadLine method will capture your input.

Select Run > Step Into or press F11.

Visual Studio Code highlights the currentDate variable assignment. The Variables window shows the value returned by the call to the Console.ReadLine method. The Terminal tab displays the string you entered at the prompt.

Select Run > Step Into or press F11.

The Variables window shows the value of the currentDate variable after the assignment from the DateTime.Now property.

Select Run > Step Into or press F11.

Visual Studio Code calls the Console.WriteLine(String, Object, Object) method. The console window displays the formatted string.

Select Run > Step Out or press Shift+F11.

Step-Out button

Select the Terminal tab.

The terminal displays "Press any key to exit..."

Press any key to exit the program.

# Use Release build configuration
Once you've tested the Debug version of your application, you should also compile and test the Release version. The Release version incorporates compiler optimizations that can affect the behavior of an application. For example, compiler optimizations that are designed to improve performance can create race conditions in multithreaded applications.

To build and test the Release version of your console application, open the Terminal and run the following command:

.NET CLI

Copy
dotnet run --configuration Release

## Visual Studio 

# Create a project
First, you'll create a .NET Core console application project. The project type comes with all the template files you'll need, before you've even added anything!

Open Visual Studio.

If the start window is not open, choose File > Start Window.

On the start window, choose Create a new project.

On the Create a new project window, enter or type console in the search box. Next, choose C# from the Language list, and then choose Windows from the Platform list.

After you apply the language and platform filters, choose the Console Application template for .NET Core, and then choose Next.

Screenshot of the C# template for the Console App.

 Note

If you do not see the Console App template, you can install it from the Create a new project window. In the Not finding what you're looking for? message, choose the Install more tools and features link. Then, in the Visual Studio Installer, choose the .NET Core cross-platform development workload.

In the Configure your new project window, type or enter GetStartedDebugging in the Project name box. Then, choose Next.

Choose either the recommended target framework (.NET Core 3.1 (Long-term support)) or .NET 5.0 (Current) , and then choose Create.

Visual Studio opens your new project.

# Create the application
In Program.cs, replace all of the default code with the following code:

C#

Copy
using System;

class ArrayExample
{
    static void Main()
    {
        char[] letters = { 'f', 'r', 'e', 'd', ' ', 's', 'm', 'i', 't', 'h'};
        string name = "";
        int[] a = new int[10];
        for (int i = 0; i < letters.Length; i++)
        {
            name += letters[i];
            a[i] = i + 1;
            SendMessage(name, a[i]);
        }
        Console.ReadKey();
    }

    static void SendMessage(string name, int msg)
    {
        Console.WriteLine("Hello, " + name + "! Count to " + msg);
    }
}

# Start the debugger!
Press F5 (Debug > Start Debugging) or the Start Debugging button Image of the 'Start Debugging' button. in the Debug Toolbar.

F5 starts the app with the debugger attached to the app process, but right now we haven't done anything special to examine the code. So the app just loads and you'll see this console output.

Windows Command Prompt

Copy
Hello, f! Count to 1
Hello, fr! Count to 2
Hello, fre! Count to 3
Hello, fred! Count to 4
Hello, fred ! Count to 5
Hello, fred s! Count to 6
Hello, fred sm! Count to 7
Hello, fred smi! Count to 8
Hello, fred smit! Count to 9
Hello, fred smith! Count to 10
In this tutorial, we'll take a closer look at this app using the debugger and get a look at the debugger features.

Stop the debugger by pressing the red stop Image of the 'Stop Debugging' button. button (Shift + F5).

In the console window, press a key to close the console window.

# Set a breakpoint and start the debugger
In the for loop of the Main function, set a breakpoint by clicking the left margin of the following line of code:

name += letters[i];

A red circle Image of a breakpoint. appears where you set the breakpoint.

Breakpoints are one of the most basic and essential features of reliable debugging. A breakpoint indicates where Visual Studio should suspend your running code so you can take a look at the values of variables, or the behavior of memory, or whether or not a branch of code is getting run.

Press F5 or the Start Debugging button Screenshot of the 'Start Debugging' button., the app starts, and the debugger runs to the line of code where you set the breakpoint.

Set and hit a breakpoint

The yellow arrow represents the statement on which the debugger paused, which also suspends app execution at the same point (this statement has not yet executed).

If the app is not yet running, F5 starts the debugger and stops at the first breakpoint. Otherwise, F5 continues running the app to the next breakpoint.

Breakpoints are a useful feature when you know the line of code or the section of code that you want to examine in detail. For information on the different types of breakpoints you can set, such as conditional breakpoints, see Using breakpoints.

# Navigate code and inspect data by using data tips
Mostly, we use the keyboard shortcuts here, because it's a good way to get fast at executing your app in the debugger (equivalent commands such as menu commands are shown in parentheses).

While paused on the name += letters[i] statement, hover over the letters variable and you see it's default value, the value of the first element in the array, char[10].

Features that allow you to inspect variables are one of the most useful features of the debugger, and there are different ways to do it. Often, when you try to debug an issue, you are attempting to find out whether variables are storing the values that you expect them to have at a particular time.

Expand the letters variable to see its properties, which include all the elements that the variable contains.

Screenshot of the debugger paused at the 'name+= letters[I]' statement.

Next, hover over the name variable, and you see its current value, an empty string.

Press F10 (or choose Debug > Step Over) twice to advance to the SendMessage method call, and then press F10 one more time.

F10 advances the debugger to the next statement without stepping into functions or methods in your app code (the code still executes). By pressing F10 on the SendMessage method call, we skipped over the implementation code for SendMessage (which maybe we're not interested in right now).

Press F10 (or Debug > Step Over) a few times to iterate several times through the for loop, pausing again at the breakpoint, and hovering over the name variable each time to check its value.

An animated screenshot of the Visual Studio Debugger showing the effect of pressing F10 to "Step Over" and iterate through a loop during debugging.

The value of the variable changes with each iteration of the for loop, showing values of f, then fr, then fre, and so on. To advance the debugger through the loop faster in this scenario, you can press F5 (or choose Debug > Continue) instead, which advances you to the breakpoint instead of the next statement.

Often, when debugging, you want a quick way to check property values on variables, to see whether they are storing the values that you expect them to store, and the data tips are a good way to do it.

While still paused in the for loop in the Main method, press F11 (or choose Debug > Step Into) until you pause at the SendMessage method call.

You should be at this line of code:

SendMessage(name, a[i]);

Press F11 one more time to step into the SendMessage method.

The yellow pointer advances into the SendMessage method.

Screenshot of the execution pointer at the SendMessage method.

F11 is the Step Into command and advances the app execution one statement at a time. F11 is a good way to examine the execution flow in the most detail. By default, the debugger skips over non-user code (if you want more details, see Just My Code).

Let's say that you are done examining the SendMessage method, and you want to get out of the method but stay in the debugger. You can do this using the Step Out command.

Press Shift + F11 (or Debug > Step Out).

This command resumes app execution (and advances the debugger) until the current method or function returns.

You should be back in the for loop in the Main method, paused at the SendMessage method call. For more information on different ways to move through your code, see Navigate code in the debugger.

# Navigate code using Run to Click
Select F5 to advance to the breakpoint again.

In the code editor, scroll down and hover over the Console.WriteLine method in the SendMessage method until the green Run to Click button Image of the 'Run to Click' button. appears on the left. The tooltip for the button shows "Run execution to here".

Screenshot of the 'Run to Click' button.

 Note

The Run to Click button is new in Visual Studio 2017. (If you don't see the green arrow button, use F11 in this example instead to advance the debugger to the right place.)

Click the Run to Click button Image of the 'Run to Click' button..

The debugger advances to the Console.WriteLine method.

Using this button is similar to setting a temporary breakpoint. Run to Click is handy for getting around quickly within a visible region of app code (you can click in any open file).

Restart your app quickly
Click the Restart Image of the 'Restart App' button. button in the Debug Toolbar (Ctrl + Shift + F5).

When you press Restart, it saves time versus stopping the app and restarting the debugger. The debugger pauses at the first breakpoint that is hit by executing code.

The debugger stops again at the breakpoint you previously set inside the for loop.

# Inspect variables with the Autos and Locals windows
Look at the Autos window at the bottom of the code editor.

If it is closed, open it while paused in the debugger by choosing Debug > Windows > Autos.

In the Autos window, you see variables and their current value. The Autos window shows all variables used on the current line or the preceding line (Check documentation for language-specific behavior).

Next, look at the Locals window, in a tab next to the Autos window.

Expand the letters variable to show the elements that it contains.

Screenshot of the Locals Window in Visual Studio.

The Locals window shows you the variables that are in the current scope, that is, the current execution context.

# Set a watch
In the main code editor window, right-click the name variable and choose Add Watch.

The Watch window opens at the bottom of the code editor. You can use a Watch window to specify a variable (or an expression) that you want to keep an eye on.

Now, you have a watch set on the name variable, and you can see its value change as you move through the debugger. Unlike the other variable windows, the Watch window always shows the variables that you are watching (they're grayed out when out of scope).

# Examine the call stack
While paused in the for loop, click the Call Stack window, which is by default open in the lower right pane.

If it is closed, open it while paused in the debugger by choosing Debug > Windows > Call Stack.

Click F11 a few times until you see the debugger pause in the SendMessage method. Look at the Call Stack window.

Screenshot of the Call Stack window in Visual Studio.

The Call Stack window shows the order in which methods and functions are getting called. The top line shows the current function (the SendMessage method in this app). The second line shows that SendMessage was called from the Main method, and so on.

 Note

The Call Stack window is similar to the Debug perspective in some IDEs like Eclipse.

The call stack is a good way to examine and understand the execution flow of an app.

You can double-click a line of code to go look at that source code and that also changes the current scope being inspected by the debugger. This action does not advance the debugger.

You can also use right-click menus from the Call Stack window to do other things. For example, you can insert breakpoints into specified functions, advance the debugger using Run to Cursor, and go examine source code. For more information, see How to: Examine the Call Stack.

# Change the execution flow
Press F11 twice to run the Console.WriteLine method.

With the debugger paused in the SendMessage method call, use the mouse to grab the yellow arrow (the execution pointer) on the left and move the yellow arrow up one line, back to Console.WriteLine.

Press F11.

The debugger reruns the Console.WriteLine method (you see this in the console window output).

By changing the execution flow, you can do things like test different code execution paths or rerun code without restarting the debugger.

 Warning

Often you need to be careful with this feature, and you see a warning in the tooltip. You may see other warnings, too. Moving the pointer cannot revert your application to an earlier app state.

Press F5 to continue running the app.

Congratulations on completing this tutorial!