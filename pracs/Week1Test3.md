---
layout: template
---
This page outlines the key tasks for this week's Workshop 1. 

Workshop tasks
Task 1: Environment Check and Project Bootstrap (15 m)
Procedure
In a clean folder, run dotnet new console -n IntroTopic.
Open in VS Code and run with dotnet run.
Set a breakpoint in Program.cs, step through, and inspect variables.
Output
Screenshot of dotnet --info.
Screenshot of a successful debug session hitting a breakpoint.


Task 2: Python-to-C# Translation (35 m)

Objective:

Practise translating a short Python program into equivalent C# code.

This helps you understand how Python’s dynamic, interpreted model compares to C#’s compiled, statically typed structure.

Given Python Program

# payroll_calculator.py
TAX_RATE = 0.2

def calculate_pay(hours, rate):
    if hours < 0 or rate < 0:
        raise ValueError("Hours and rate must be positive.")
    gross = hours * rate
    tax = gross * TAX_RATE
    net = gross - tax
    return net

def main():
    name = input("Enter employee name: ")
    hours = float(input("Hours worked: "))
    rate = float(input("Hourly rate: "))
    net_pay = calculate_pay(hours, rate)
    print(f"{name} earned ${net_pay:.2f} after tax.")

if __name__ == "__main__":
    main()

Your Task: Translate to C#

Create a new console project:
dotnet new console -n PayrollCalculator
>cd PayrollCalculator
Implement the equivalent logic in C#:
Create a constant for the tax rate.
Define a static method CalculatePay(double hours, double rate) returning a double.
Use try catch to handle invalid input.
Request input using Console.ReadLine().
Convert inputs with double.Parse() or double.TryParse().
Output formatted currency using string interpolation ($"{value:F2}").
Compile and run:
dotnet run
Example Expected Output
Enter employee name: Casey
Hours worked: 38
Hourly rate: 42.5
Casey earned $1292.00 after tax.
Extension Challenge (Optional)
Add rounding to two decimal places.
Handle invalid input using exception handling (FormatException, ArgumentException).
Refactor your logic into a separate class Payroll with a static method CalculatePay.
Output Submission
A working Program.cs file containing your translated and tested code.
A short text file (Note.txt) describing at least three differences you noticed between Python and C#, for example:
Input parsing is explicit (double.Parse() vs float()).
Variables must be declared with a type.
Errors are checked at compile-time rather than at runtime.




Task 3: First Class Model (40 m)

Create a Person class with:

Auto-properties: FirstName, LastName, Age.
Constructor validations.
Method FullName() returning “LastName, FirstName”.
Procedure

Add Person.cs and instantiate in Program.cs.

Demonstrate property use and method call.

Add a second method IsAdult() returning a bool.

Output

Person.cs and updated Program.cs.

Console output screenshot demonstrating both methods.




Task 4: Git Hygiene (30 m)
Procedure
git init, add a .gitignore for .NET.
Make three small commits:
 “feat: translate payroll to C#”
 “feat: add Person class with validation”
“chore: add .gitignore and README”
Push to your private GitHub repo if available.
Initialise the repository
Open a terminal in the project folder and run
git init
Create a .gitignore suited for .NET
Add a file named .gitignore in the root with the standard .NET ignores. The simplest way is
dotnet new gitignore
This generates the Microsoft-maintained template (ignores bin, obj, user files, etc.).
Stage and commit the first change
Translate your old payroll code into C# (or whatever “payroll” refers to in your context), add the files, then commit:
git add .
git commit -m "feat: translate payroll to C#"
Add the Person class and commit
After creating Person.cs and updating Program.cs, stage and commit again:
git add Person.cs Program.cs
git commit -m "feat: add Person class with validation"
Add housekeeping files and commit
Create or update your README, confirm .gitignore exists, then commit:
git add .gitignore README.md
git commit -m "chore: add .gitignore and README"
Push to GitHub 
If you already have a private GitHub repo, add it as the remote:
git remote add origin https://github.com/<your-username>/<repo>.git
Push the main branch:
git branch -M main
git push -u origin main
Output
git log --oneline screenshot showing the three commits. 
Repository URL or local log if offline.
