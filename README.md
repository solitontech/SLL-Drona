# SLL Drona
## Vision
To provide an Open - Source Labview UI Testing Framework to automate manual UI testing. 

UI testing plays an important part in Overall testing process of each application/product. Drona allows Engineers to automate the UI test by writing some test cases that involves the concept of setting values to UI controls and asserts it to check the test case. It quite increases the overall software quality which is predominantly needed in today's existing or developing products. It also reduces the time taken by Engineers to the test the UI.

## SLL Drona in GLA Summit
SLL Drona as an Open Source LabVIEW UI testing framework was presented in GLA Summit 2022 organized by McQuillan, cbutcher, .aCe.. (Open group).  For more details please watch over the [video](https://www.youtube.com/watch?v=4JryzEPQexM)


## Minimum Compatible LabVIEW Version
Source code is saved with LabVIEW 2016.

## Installation
Please find the latest SLL Drona package available [here](https://github.com/solitontech/SLL-Drona/releases/tag/v0.3.0) and install it using VI Package Manager.

## Usage
Drona provides a library of VIs that are used to automate and test the UI without any flaws. It can be used to test any LabVIEW application and supports creating test cases from SLL Drona APIs.

## Palette
To test the UI of the application you need to create the test cases using corresponding SLL Drona APIs. It can be accessed under the following location.

### In Block diagram:
Functions Palette -> Addons -> SLL Drona 
![](Images/Functions%20Palette.png)

## Workflow
Drona provides a library of APIs that helps to create test cases for UI testing. There are certain steps in creating a test case to make the workflow of the UI testing smooth and possible. The 4 steps that needs to be followed for creating test cases are:

1. [Setup](#1-setup)
2. [Stimulus](#2-stimulus)
3. [Assert](#3-assert)
4. [Cleanup](#4-cleanup)

You can find the related APIs to these steps in SLL Drona palette

### 1. Setup:
<ul> First step in creating the test case is the setting up of the project and having a Drona configuration file inside the application instance. The Drona configuration file contains information such as the name of the Launcher VI that needs to be under UI test and whether to open and run it while launching the test. If you have configured the Drona file then you can just start creating the test case by dragging and dropping the Setup VI in block diagram which in return gives out the application reference and VI reference of the Launcher VI that needs to be tested. </ul>

![Drona ini file](Images/Drona%20ini%20file.png) <br/>
The above shown is the sample format required for creating Drona configuration file.
### 2. Stimulus:
<ul>Stimulus is the step where you assign values to the UI controls based on the need and operations to perform. This poly API available in SLL Drona palette provides a set of stimulus VIs that helps you in assigning the value for various types of control. </ul>

![Stimulus Control](Images/Stimulus%20API%20control.png) ![Stimulus Keyboard](Images/Stimulus%20API%20keyboard.png) ![Stimulus VI](Images/Stimulus%20API%20VI.png) <br/>
<ul>You can set values for a control that are inside a tab control or a sub panel, etc by giving a proper valid control path and value for that control. The control path contains the label name of the controls with delimiters to access the specific or target control. </ul>

For example, To access the numeric control as in the below depicted UI you need to give the control path as: <br/>
![Stimulus control](Images/Stimulus%20control.png) <br/>
*Tab Control>>Cluster>>Numeric* <br/>
![Stimulus workflow](Images/Stimulus%20workflow.png) <br/>
As mentiond above you should give the label name of the controls and ensure whether its as same as the label name of the UI as its case sensitive. </ul>

### 3. Assert:
<ul>In this step you will assert the value obtained with the actual and restun whether the test is passed or failed. This poly API available in SLL Drona palette provides a set of assert VIs that helps you in asserting the values. </ul>

![Assert Control Value](Images/Assert%20Control%20value.png) ![Assert Control Disable](Images/Assert%20Control%20disable.png) ![Assert Subpanel Inserted VI](Images/Assert%20Subpanel%20Inserted%20VI.png)
 ![Assert VI](Images/Assert%20VI%20Exec.png)  
<ul>As same as stimulus here also there needs to be a valid control path given. There are a set of Assert VIs available in SLL Drona palette which can be used to assert the value or obtained result. </ul> 

For example, To assert the value of the string in the below sample UI you need to give the input as <br/>
![Assert control](Images/Assert%20control.png)<br/>
*Tab Control>>Tab Control 2>>Cluster>>String* <br/>
![Assert workflow](Images/Assert%20workflow.png)
### 4. Cleanup:
<ul> Close all the references that are opened while setting up the test case. For this just drag and drop the Close API in the Block diagram from SLL Drona palette and give the Launcher VI reference and application reference that are need to be closed. </ul>

## Unit Tests
You can find the examples for different use cases in the following path: <br/>
<*LabVIEW>\vi.lib\SLL Drona\Examples*  <br/>
There are 4 different types of examples available here based on the use case.
To get to know more about the use cases please visit the testcases under the following path: <br/>
<*LabVIEW>\vi.lib\SLL Drona\Test\Tests\SubTests* 

## Package Build
To build the SLL Drona package, please visit this [document](BUILD.md) for more details.

## Contributing 
### Steps for contributing to SLL Drona:
+ Fork the main repository
+ Create a new branch and make the changes with it
+ Commit your changes 
+ Push to the new branch
+ Submit a pull request 

To contribute to SLL Drona, you need to have LabVIEW 2016 - 32 bit development environment.

## License 
SLL Drona is distributed under MIT [license](https://github.com/solitontech/SLL-Drona/blob/main/LICENSE). 

## Credits
SLL Drona uses open source components. You can find the source code of their open source projects along with license information below. We acknowledge and are grateful to these developers for their contributions to open source. 

* Project: Caraya https://github.com/JKISoftware/Caraya <br/>
License (BSD): https://github.com/JKISoftware/Caraya/blob/master/LICENSE.md

* Project: SLL Toolkit https://github.com/solitontech/SLL-Toolkit <br/>
License (MIT): https://github.com/solitontech/SLL-Toolkit/blob/master/LICENSE

* Project: OpenG https://sourceforge.net/projects/opengtoolkit/ <br/> 
License: BSD

* Project: NI Forum https://forums.ni.com/t5/Example-Programs/ct-p/code-documents <br/>
License: MIT

## Inviting users and contributors

Please fill out the below form if you are interested in trying out and/or contributing to SLL Drona.
https://forms.office.com/r/jQkLb2WeL6
