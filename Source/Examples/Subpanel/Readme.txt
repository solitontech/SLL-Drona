1.The "Main.vi" is the main UI.
2.Select "latch boolean simulation" option in "VI to load" listbox.
3.In the subpanel control click the "boolean 1" button, check for the output from the string control.
4.Similarly click the "boolean 2" button and check the output in the string control.
5.Now select "Numeric Ctl coercion" in the "VI to load" listbox.
6.Enter a value less than 100 in the control and check how the control is coercing it.
7.Enter a value between 100 and 200 and check the value in the control.
8.Enter a value greater than 200 and check how the value is coerced.
9.The "SubpanelTests" library contains the list of test VIs which performs the operations mentioned above.
10.The Test VIs can be executed individually and also in collective manner.
11.To run them in a collective manner, Open the Project file for the particular example.
12.In the toolbar, navigate to Tools >> Caraya >> Run Tests in Active Project.
13.This action will run all the tests in the project and generates a test report.