Having trouble debugging a Script task or component in your SSIS package?  Do you have a breakpoint set, but it never seems to get "triggered"?

Here's a quick tip to troubleshoot:

## 1) Open the Script task/component
### Script Task (Control Flow)
Click the Control Flow tab
Double-click the Script *task*

### Script Component (Data Flow)
Click the Data Flow tab
Double-click the Script *component*

Click Script and then click Edit Script.

## 2) Set the breakpoint
Locate the line of script on which you want to set a breakpoint
Click in the margin to the left of the code to set a breakpoint (a red dot will appear)
On the File menu, click Exit.

--> **Click OK.** <--

## 3) Verify that the task/component has a breakpoint set
The SSIS user interface will indicate that the breakpoint was successfully set by showing a red dot next to the name of the task/component.

Save the package and re-attempt running the package.  The breakpoint should be triggered if execution of the package makes it to the line of code where you've set the breakpoint.
