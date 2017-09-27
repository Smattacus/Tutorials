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

1.  Go to “Start” -> Open “Visual Studio 2015.” Note there are older version of VS2015; do not use them.
2.  In the Visual Studio startup screen, select “Open Project…” under “Start.” Alternatively, you can do File -> Open -> Project / Solution (Ctrl + Shift + O).
