# Steps for executing SLL Drona Tests in Source Code

* Create a Drona.ini file, parallel to the project directory.
  
  ![Drona File Directory](Images/Drona%20File%20Directory.png)


* In the Drona.ini file, under the source section, enter the source VI path from the project directory on LauncherPath
  
* Set 'Run?' and 'Open?' as 'TRUE' to run and open source VI during the test.

  ![Drona.ini file](Images/Drona%20ini%20file.png)


* Create a new test library and add all test VIs in it, such that all the test names should start with the prefix “Test”. To get more details for creating the tests, look through the [Drona's Workflow](https://github.com/solitontech/SLL-Drona#workflow).

  ![Source Code Tests](Images/Source%20Code%20Tests.png)


* Each test can be performed individually, by running the corresponding test VI.

* To run all the tests in the project, select this option: 'Tools -> Caraya -> Run Tests in Active Project...'

  ![Run Tests in Active Project](Images/Run%20Tests%20in%20Active%20Project.png)


<br>
<br>
<br>
<br>
<br>
<br>

# Steps for executing SLL Drona Tests in EXE

* In the Drona.ini file, under the EXE section, mention the source VI name on LauncherName

   ![Drona.ini file](Images/Drona%20ini%20file.png)

  
* Create a new test library and add all test VIs in it, such that all the test names should start with the prefix “Test”.

  ![Example Project](Images/Example%20Project.png)


* Create a VI named “Run.vi” in the test library, and add Drona's 'Run Core' API (run all tests in the packed library). The VI should be named "Run.vi", because the 'EXE Run Tests' API will search for the VI in this name, to execute the tests in EXE.

   ![Run VI](Images/Run%20VI.png)

* To test Drona in EXE, certain properties need to be configured in the VI Server. In the Project window, on items view, right-click on 'My Computer' and select 'Properties'.
  
  ![My Computer Properties](Images/My%20Computer%20Properties.png)


* Go to 'VI Server' and enable TCP/IP under Protocols. Enter the port number as 5000.
   Note: If any other application already uses this port number, try with different port numbers (e.g. 5001, 5002, etc.,).
  
  ![VI Server Configuration](Images/VI%20Server%20Configuration.png)


* Scroll down to the 'Machine access' section and add the Machine names present in the below image.
  
  ![Machine Access List](Images/Machine%20Access%20List.png)


* Scroll down further to the 'Exported VIs' section and add the values present in the below image. After adding all these values, click OK and save the LV Project.
  
  ![Exported VIs List](Images/Exported%20VIs%20List.png)


* Create EXE for the source code that needs to be tested. Add the Drona.ini file in 'Always Included' and build the EXE.

  ![EXE Configuration](Images/EXE%20Configuration.png)
  ![EXE Preview](Images/EXE%20Preview.png)


* Create a Packed Library (PPL) for the test library, that contains all the Test VIs and build the PPL.

  ![PPL Configuration](Images/PPL%20Configuration.png)
  ![PPL Preview](Images/PPL%20Preview.png)


* Create a new VI (not needs to be in the test library) and connect the created EXE and PPL paths to the 'EXE Run Tests' API.

  ![EXE Run Tests](Images/EXE%20Run%20Tests.png)


* Close the LabVIEW Project and run the VI created in the previous step on LabVIEW Instance, to execute Drona tests in EXE.


<br>
<br>
<br>


**Note:** For further reference, you can find the Drona examples in this directory: **<LabVIEW_Installation_Folder>\examples\Soliton Technologies\SLL Drona\Examples**
