# Steps for executing SLL Drona Tests in Source Code

* Create a Drona.ini file, parallel to the project directory.
  
  ![Drona File Directory](Images/Drona%20File%20Directory.png)


* In the Drona.ini file, under the source section, enter the source VI path from the project directory on LauncherPath
  
* Set 'Run?' and 'Open?' as 'TRUE' to run and open source VI during the test.

  ![Drona.ini file](Images/Drona%20ini%20file.png)


* Create a new test library and add all test VIs in it, such that all the test names should start with the prefix “Test”.

  ![Example Project](Images/Example%20Project.png)


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


* Create a VI named “Run.vi” in the test library, and script the VI such that it runs all the tests present in that library. Drona's 'Run Core' API will perform this function (Run all tests present in the packed library).

   ![Run VI](Images/Run%20VI.png)


* Create EXE for the source code that needs to be tested. Add the Drona.ini file in 'Always Included' and build the EXE.

  ![EXE Configuration](Images/EXE%20Configuration.png)


* Create a Packed Library (PPL) for the test library, that contains all the Test VIs and build the PPL.

  ![PPL Configuration](Images/PPL%20Configuration.png)


* Create a new VI (not needs to be in test library) and connect the created EXE and PPL paths to the "EXE Run Tests" API.

  ![EXE Run Tests](Images/EXE%20Run%20Tests.png)


* Close the LabVIEW Project and run the VI created in the previous step on LabVIEW Instance, to execute Drona tests in EXE.


<br>
<br>
<br>


**Note:** For further reference, you can find the Drona examples in this directory: **<LabVIEW_Installation_Folder>\examples\Soliton Technologies\SLL Drona\Examples**
