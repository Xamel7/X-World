## C# Hello World
This tutorial shows how to create and run a .NET console application by using Visual Studio Code and the .NET CLI. Project tasks, such as creating, compiling, and running a project are done by using the .NET CLI. You can follow this tutorial with a different code editor and run commands in a terminal if you prefer.

Create the app
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

