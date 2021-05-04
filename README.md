# Model_Identification_GUI_MATLAB_Implementation
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


