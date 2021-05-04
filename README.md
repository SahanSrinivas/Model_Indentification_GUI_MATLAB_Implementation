# Model Identification GUI MATLAB Implementation
Model Identification algorithms play a vital role in determining process dynamics. After performing bump test, the very next is to identify model dynamics to tune PID controller or MPC. Otherwise, there will be model-plant mismatch. To avoid this a precise model dynamics need to be considered. In this line, I developed model identification tool in MATLAB which takes bump test data in excel (.xlx and xls) formats. Models namely process models (FOPTD, Dual FOPTD), Transfer Function Models and State Space models can be identified.

![Figure 1](https://user-images.githubusercontent.com/36400481/116960497-2afe3a80-acbe-11eb-933b-1989cca14bb6.png)

Figure 1 shows the Model Identification tool overview. Below are the sailent featues of Model Identification

Model identification is intended to identify process parameters from a given bump test data. Model identification comprises:

• Model Identification Parameters
• State Space Matrix (Used as an extension for ABB APC Model Builder)
• Transfer Function Model (Used as an extension for ABB APC Model Builder)

# 1. Read Data File
The data usually read in the form of Microsoft excel file (.xlsx and .xlsm). The data can comprise of process raw data (input and output data). The raw data file from the DCS or from any OPC source should be allowed in a unique format. The format data can have any number of columns but there shouldn’t be time stamp column. If time stamp column is received it can be deleted prior importing in GUI. The sample figure 3 shows how data structure can be.

![Figure 2](https://user-images.githubusercontent.com/36400481/116960882-56355980-acbf-11eb-949e-339686d1f20c.png)

Figure 2. Sample Bump Test Data File Representation without Time Stamp
It is apparent from Figure 2. Bump Test File has no any time stamp and the respective column fields are input and output data.

To read the data click on **Read Data File** and window appears as shown in Figure 3 to select datafile.

![Figure 3](https://user-images.githubusercontent.com/36400481/116962037-8f22fd80-acc2-11eb-8e15-09612a2da424.png)

After selecting the useable data file, on top of read data file, file location appears in GUI as shown in Figure 4.

![Figure 4](https://user-images.githubusercontent.com/36400481/116962081-ab269f00-acc2-11eb-991c-934e7b1ad935.png)

If user discards reading data file and error appears as shown in Figure 5. Data file is not selected.

![Figure 5](https://user-images.githubusercontent.com/36400481/116962108-c4c7e680-acc2-11eb-8772-5f2b41982cf4.png)

# 2. Selecting Input and Output Data

Once the datafile is read, tool reads all columns data in respective input and output fields as shown in Figure 6. Now user needs to select input and output data in the respective drop-down menu and select it accordingly. Here, the input data is bump test data on manipulated variable whereas output data is corresponding bump test result on controlled variable.

![Figure 6](https://user-images.githubusercontent.com/36400481/116962229-107a9000-acc3-11eb-879e-921089371850.png)

Similarly, output data selection can also be selected from the drop-down menu as shown in Figure 7.

![Figure 7](https://user-images.githubusercontent.com/36400481/116962294-37d15d00-acc3-11eb-9939-2586513ba4cc.png)

As and when user finalizes, the input and output data. The corresponding plots can be seen in respective input data and output data axes. Figure 8 shows the plots of corresponding input and output data.

![Figure 8](https://user-images.githubusercontent.com/36400481/116962354-5c2d3980-acc3-11eb-8d83-085aa7ee3daf.png)

# 3. Model Identification for Bump Test Data

As and when user selects respective input and output data, now identification of model can be performed. All identification techniques are briefly mentioned.

# 3.1 Process Model Identification
Model parametric identification is to identify the process models and get the relevant information namely (gain, time constant, and time delay) from process data. To identify the model parameters in GUI, first user needs to select input and output data and corresponding identification is shown. Before performing Model Parametric Identification, the sampling time for the model should be given first. The sampling time is time intervals which samples are taken for input and output variables. The time here considered is in ‘Seconds’. For instance, sample time may be 1 second, 10 seconds, 15 seconds etc. Figure 9 shows the sample time in seconds, where used should give corresponding sample time.

![Figure 9](https://user-images.githubusercontent.com/36400481/116962438-972f6d00-acc3-11eb-913b-232b4f3f3b6b.png)

After giving the respective sampling time, input data and output data. User can perform identification by just clicking on Model Parametric Identification radio button as shown in Figure 10.

![Figure 10](https://user-images.githubusercontent.com/36400481/116962487-b29a7800-acc3-11eb-8592-0e393ef59f6b.png)

# 3.2 Results from Model Parametric Identification
When user clicks on radio button of Model Parametric Identification, the corresponding results can be seen in new plot, where estimations are done with respect to output variable as shown in Figure 11.

![Figure 11](https://user-images.githubusercontent.com/36400481/116962551-e1b0e980-acc3-11eb-9260-391a0bc8e717.png)

It is apparent from the figure that model identification is done based on estimation of output data and corresponding fit percentage is 74.78 % for used data. It is recommended that the fit percentage should be more than 75% of data which is used.
The corresponding identification parameters are shown in Figure 12.

![Figure 12](https://user-images.githubusercontent.com/36400481/116962572-f42b2300-acc3-11eb-895e-f021290ccd4e.png)

It is apparent from the figure, the model is First Order Plus Time Delay (FOPTD) with corresponding Gain, Time Constant, and Time Delay are obtained.

# 4. Reset Identification

Rest Identification clears the results of any identification techniques performed in the GUI which is shown in Figure 13.

![Figure 13](https://user-images.githubusercontent.com/36400481/116962634-20df3a80-acc4-11eb-93cc-5e7c8bc0f4e7.png)

# 5. Other Identification in GUI

# 5.1 State Space Matrix
State Space Matrix estimates the first order transfer and corresponding state space estimators namely A, B, C and D matrices respectively. It is estimated upon user giving Gain and Time Constant values. From the set of group radio buttons, to estimate the state space matrix, user can click on State Space matrix radio button as shown in Figure 14.

![Figure 14](https://user-images.githubusercontent.com/36400481/116962716-613eb880-acc4-11eb-9c83-35206e8f8459.png)

As and when user clicks the State Space Matrix, two dialogue boxes appear to enter Gain and Time Consant.

![Figure 15](https://user-images.githubusercontent.com/36400481/116962735-73205b80-acc4-11eb-91b5-b619a24d7263.png)

The corresponding transfer function is appeared in GUI and four other pops shows the A, B, C and D matrix values as shown in Figure 16.

![Figure 16](https://user-images.githubusercontent.com/36400481/116962755-8501fe80-acc4-11eb-88f8-301065d4bfa7.png)

# 5.2 Transfer Function Identification

It is used as standalone application, for finding out continuous time (s-domain) transfer function upon selecting used defined data. In this user need to give number of poles and number of zeros for data and corresponding TF is obtained. Figure 17 shows the procedure for TF identification.
  a. User need to select dataset with first row as output and second row as input
  b. User should input number of poles
  c. User should input number of zeros
  d. Corresponding TF result is obtained in result window of GUI
  
  ![Figure 17](https://user-images.githubusercontent.com/36400481/116962856-ddd19700-acc4-11eb-9e60-79b8629a69fb.png)
  
 Upon giving the poles and zeros, the corresponding TF is obtained in Figure 18. It is apparent from figure that the fit percentage is 88%. To get more fit percentage user can    change poles and zeros to obtained best fit percentage.
 
 ![Figure 18](https://user-images.githubusercontent.com/36400481/116962935-15404380-acc5-11eb-80b4-074559b29e2a.png)

# 6. Intended User
To run the model identification GUI tool. Users can download the MATLAB code and can run the file or else application (executable).exe file can be created using MATLAB and below are steps for installing MATLAB MCR runtime.

This is for users responsible to install MATLAB MCR runtime in machine.

# 6.1 Prerequisites before running Model_Identification.exe
a) Verify the MATLAB Runtime is installed and ensure you have installed version 9.1 (R2016b).
b) Run the MATLAB Runtime installer from the below location:
Download the Windows 64-bit version of the MATLAB Runtime for R2016b from the MathWorks Web site by navigating to
http://www.mathworks.com/products/compiler/mcr/index.html
For more information about the MATLAB Runtime and the MATLAB Runtime installer, see Package and Distribute in the MATLAB Compiler documentation in the MathWorks Documentation Center.
c) After successful installation, double click on Model_Identification.exe or run as administrator.

