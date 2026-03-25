# SSIS_Bug
This repository contains packages to demonstrate different situations in which the scripttask debugger does not work in Visual Studio 2022 SSIS extension.
Tested with: Versions: VS Community 17.14.27 and SSIS Extension 16.0.5685.2. The packages are targeting SQL Server 2022.

## Setup
Each package contains only a scripttask. The scripttask consists of a main.cs and a TestTheBreakpoint.cs. 
The TestTheBreakpoint.cs will contain the problematic code.

## Debugger won't work:
- Get_Accessor.dtsx: The debugger will not open because of the use of the get accesssor
- In_Modifier.dtsx: The debugger will not open because of the use of the in modifier
- String_Formatting.dtsx: The debugger will not open becaus of the use of this string formatting method: `$"The message: {TheMessageAfterTheBreakpoint}";`

## Debugger works:
- Pass_By_Ref.dtsx: The code from the previous packages has been refactored into variants that won't stop the debugger from starting.
