# Tutorial: Adding a Function to the VME Interface Library in C++.
## By Sean Mattingly

This is a short tutorial which shows how to add a function to the VME_Interface DLL.

* * *

1.  Go to “Start” -> Open “Visual Studio 2015.” Note there are older version of VS2015; do not use them.
2.  In the Visual Studio startup screen, select “Open Project…” under “Start.” Alternatively, you can do File -> Open -> Project / Solution (Ctrl + Shift + O).
![](new_project.jpg)
3.  In the file dialog that opens, go to “My Documents” -> “Visual Studio 2015” (NOT 2013 or 2010) -> “Projects” -> “VME_Interface” -> VME_Interface.sln. Alternatively, the full file path is C:\Users\SKIFFLAB\Documents\Visual Studio 2015\Projects\VME_Interface\VME_Interface.sln. Click “Open” to open the solution.
4.  MSVS2015 will open the full solution. There are a variety of projects inside this solution for different data acquisition processes. Before we create a new project in this solution, I want to point out the “VME_Interface” library: ![](vme_interface_cpp.jpg) In the Solution Explorer, there are a number of solutions. At the bottom (of the time of writing) is the solution “VME_Interface.” The source file “VME_Interface.cpp” contains all the methods that we can call using the DLL. The header file “VME_Interface_Funcs.h” contains the declarations of the externally usable  (“public”) functions. *At this point, do NOT make any modifications to VME_Interface.cpp.*
