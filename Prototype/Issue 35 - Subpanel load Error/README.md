# 1145 - SUBPANEL ERROR
![](Images/Subpanel%20error%201145.png)
## Demo Test 1
### Logic:
1. Controls: VI Path
2. Indicators: Sub panel, VI name, VI Ref same?, Error out
3. **Demo VI** path is given as input 
4. The reference taken from demo  vi is inserted into the sub panel
5. The Inserted vi reference was again taken and compared with actual demo vi reference
6. The inserted vi is removed from sub panel
7. All the opened references were closed in the required order
### Result:
> When the Inserted VI reference was closed 
> ![](Images/Demo%20Test%201%20close%20ref.png)
> SLL Drona\Prototype\Issue 35 - Subpanel load Error\Demo test 1.vi
1. Only first time the execution was proper
2. Second time got 1145 Error (Description:  Cannot open VI because it is already in a subpanel control)
3. Also the Demo vi was still in memory
> When the Inserted VI reference was not closed
> ![](Images/Demo%20Test%201%20open%20ref.png)
1. The execution was proper and the error ont occured
2. Also the Demo vi was not in memory after each execution
   
## Demo Test 2
### Logic:
1. Controls: VI Path, Subpanel VI Path
2. Indicators: VI name, VI Ref same?, Error  out
3. **Demo VI** path is given as input 
4. **Subpanel VI** path is given as input to subpanel vi path
5. The from demo vi is made to run and then inserted into the sub panel
6. The Inserted vi reference was again taken and compared with actual demo vi reference
7. The inserted vi is removed from sub panel
8. The Demo vi is aborted
9. All the opened references were closed in the required order
### Result:
> When the Subpanel VI is in **Closed** state
> ![](Images/Demo%20Test%202%20no%20error.png)
> SLL Drona\Prototype\Issue 35 - Subpanel load Error\Demo test 2.vi
1. While executing the Demo Test 2 the error not occured
2. The Subpanel VI was not in memory
3. But the Demo VI was in memory when the reference was closed and vice versa
4. **Note**: *Even though the Inserted VI reference was closed the error not occured*
> When the Subpanel VI is in **Open** state
> ![](Images/Demo%20Test%202%20SP%20open%20with%20CR.png)
1. With Subpanel VI open and **Inserted VI reference closed** the error 1145 occured (Description: Cannot open VI because it is already in a subpanel control) and still the Demo VI was in memory after execution
2. With Subpanel VI open and **Inserted VI reference open** the error was not faced and the Demo VI was not in memory after execution

## <u>Inference:</u>
1. When the Inserted VI reference is kept open the VI which was loaded into sub panel was not in memory after execution and was vise versa when the inserted vi reference was closed
2. When the VI containing the sub panel is in closed state then it doesn't matter that the Inserted VI reference is closed or not. On both conditions the execution was fine and error was not faced
3. When the Subpanel VI is in open state then the Inserted VI reference matters and the execution works fine only when that reference is not closed
4. **Note:** In all cases if the Inserted VI reference is not closed then there occurs a reference leak traced by dett (Desktop Exe Trace Toolkit). But that specific vi (which was loaded into subpanel) was not in memory after execution or after closing the curent VI reference


## **Final Solution**
> ![](Images/Main%20Inst%20solution.png)
> SLL Drona\Source\Test\Tests\CurrentInstance.vi
### <u>Before Implementation:</u>
1. The Main VI ref and Application ref was closed even before the Main VI unloads the VI from Subpanel and stops execution
2. Due to this the sub vi was not properly removed from the Subpanel which lead to the 1145 - Subpanel load error
### <u>Solution Proposed:</u>
1. To close the Main vi and Application ref after the Main vi completes its execution and comes to **Idle state**
2. So that the Main vi could properly remove the sub vi from the Subpanel using **Remove VI** property node
### <u>After Implementation:</u>
1. The Main vi properly removes the sub vi from the subpanel leading to no 1145 - Subpanel Error while next time inserting the sub vi into Subpanel
2. The CurrentInstance vi waits until the Main VI completes execution using ***AssertVIExecIdle.vi*** from "*SLL Drona\Source\APIs\Assert\AssertVI\AssertVIExecIdle.vi*". 
3. It has also a default timeout of 5sec to stop its execution even if the Main vi still remains in running state.