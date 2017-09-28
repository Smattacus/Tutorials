# Tutorial: Writing a C++ Program using Visual Studio to Call the VME Interface Library.
## By Sean Mattingly


This document steps the user through creating a new project in Visual Studio
that links to the already existing .DLL (or .LIB) library “VME_Interface.dll”.
This library contains a number of routines for accessing the VME interface
through V2718, setting up a data acquisition, downloading the data from the
VME, and writing the data to the hard drive. I hope the library will be a good
springboard for a student in the Skiff lab at the University of Iowa who wants
to get started acquiring his or her own data for their own experiment.

This tutorial will also show the user where the code for the VME_Interface
library is held for the future event if they want to modify it and add their
own methods to it.

Finally, we will also cover the basics of creating a project in MS Visual
Studio 2015, which includes creating the project itself, writing the C++ code,
pointing the MSVS compiler / linker to the required libraries, compiling it,
and running the resulting executable.

* * *

1.  Go to “Start” -> Open “Visual Studio 2015.” Note there are older version of VS2015; do not use them.
2.  In the Visual Studio startup screen, select “Open Project…” under “Start.” Alternatively, you can do File -> Open -> Project / Solution (Ctrl + Shift + O).
![](new_project.jpg)
3.  In the file dialog that opens, go to “My Documents” -> “Visual Studio 2015” (NOT 2013 or 2010) -> “Projects” -> “VME_Interface” -> VME_Interface.sln. Alternatively, the full file path is C:\Users\SKIFFLAB\Documents\Visual Studio 2015\Projects\VME_Interface\VME_Interface.sln. Click “Open” to open the solution.
4.  MSVS2015 will open the full solution. There are a variety of projects inside this solution for different data acquisition processes. Before we create a new project in this solution, I want to point out the “VME_Interface” library: ![](vme_interface_cpp.jpg) In the Solution Explorer, there are a number of solutions. At the bottom (of the time of writing) is the solution “VME_Interface.” The source file “VME_Interface.cpp” contains all the methods that we can call using the DLL. The header file “VME_Interface_Funcs.h” contains the declarations of the externally usable  (“public”) functions. *At this point, do NOT make any modifications to VME_Interface.cpp.*

Now we will create a Project and add it to the VME_Interface solution. This
way, MSVS2015 will play nice with references when we try to link the code we
write to the functions inside VME_Interface.dll.

The Project that we create will also demonstrate linking all the necessary dependencies in Visual Studio 2015 and where they are 
on the data computer.

1.  Go to File -> Add -> New Project. Select "Win32 Console Application." For the name, enter "Demonstration_VME_Library_Call".
2.  In the Win32 Application Wizard that appears, click "Next." In the final screen select "Console Application" and "Empty Project" like so: ![](win32_wizard.jpg)
3.  Create a new source file in your new project. In the Project Explorer pane, expand the "Demonstration_VME_Library_Call" project, right click on "Source Files," and select "C++ Source File." Enter a new name for your soure file - I chose "VME_Demo.cpp"
4.  Add some code to it:

```c++
#include <iostream>
#include <cstdio>
#include "VME_Interface_Funcs.h"
#include "VME_Interface_Defs"

#define _HDF5USEDLL_

int main() {
}
```

VS should highlight the lines "VME_Interface_Funcs.h" and "VME_Interface_Defs.h," since it doesn't know where they are. Let's fix that.
