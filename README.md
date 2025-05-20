# Digital_VLSI_SoC_VSD_Nasscom
Exploring OpenLane
# Day1:OpenLane Directory Structure
# Exploring PDKs (Process Design Kits)
PDKs contain LEF & DEF files. open_pdk makes foundary level PDKs to be compatible with open source EDA tools. sky130A is one such PDK. Its a variant.
![VirtualBox_VSD_18_05_2025_13_19_18](https://github.com/user-attachments/assets/392d5c8f-6b2f-4245-a609-ba7a9cc07d52)
libs.ref contains process specific files and libs.tech contains tools specific files
![VirtualBox_VSD_18_05_2025_13_30_03](https://github.com/user-attachments/assets/9eb526b3-e84d-4b2f-bbde-79e572309fa7)
Here, we are going to work on sky130_fd_sc_hd , which means sky130 nm process foundary standard cell high density. lets see what it contains
![VirtualBox_VSD_18_05_2025_13_36_29](https://github.com/user-attachments/assets/6fc440b7-961e-42fd-b549-e42f10c6c47f)
Having seens PDKs, Now lets work inside openLane in an interactive mode. Without interactive, it will run the complete flow.
# Design Preparation STEP
![VirtualBox_VSD_18_05_2025_16_27_07](https://github.com/user-attachments/assets/ada131e7-0d76-4343-bbc2-4071f8cc21b9)
Now we are require to import packages needed to run the flow. Also we require the design for which we require to run the flow.
# seeing designs inside openlane and selecting picorv32a
![VirtualBox_VSD_18_05_2025_16_36_46](https://github.com/user-attachments/assets/f16ee9a3-27b8-42b1-89f9-b112b6388d73)
It contains the source file and its the one where veilog code is present.
![VirtualBox_VSD_18_05_2025_16_41_12](https://github.com/user-attachments/assets/7d6f5c14-edd3-4637-aa2d-a3ac154dc493)
Let us also see the config.tcl file
![VirtualBox_VSD_18_05_2025_16_45_26](https://github.com/user-attachments/assets/0ea9a37e-cfe7-4c78-973c-f357ebe6c431)
# design preparation setup
![VirtualBox_VSD_18_05_2025_16_58_41](https://github.com/user-attachments/assets/e63506be-4314-4652-ac05-08acb2715f75)
'runs' directory is now created in the picorv32a design difrectory.
![VirtualBox_VSD_18_05_2025_17_04_43](https://github.com/user-attachments/assets/700eaeb6-c0a6-4a36-8293-bfe58be24122)
# reviewing files after design preparation and run synthesis
lets now see whats inside 'runs' directory wich is created with the time stamp
![VirtualBox_VSD_18_05_2025_17_11_40](https://github.com/user-attachments/assets/87d8ca65-8ce5-4d23-b5cd-bf7c451fd4cb)
Except tmp, all other folders will be empty. now let's see the files inside tmp.
![VirtualBox_VSD_18_05_2025_17_14_44](https://github.com/user-attachments/assets/5c085a75-1372-4cb4-985e-2d746a72f9e0)
now let us see LEF information. it consists of all design connect details
![VirtualBox_VSD_18_05_2025_17_19_53](https://github.com/user-attachments/assets/96a25077-ac04-4350-ac85-b824a16fd45d)
# running systhesis
This will run Yosys synthesis as well as abc
![VirtualBox_VSD_18_05_2025_17_27_46](https://github.com/user-attachments/assets/2835597f-2815-4d63-83b7-a8c7883dbab0)
# FloorPlanning
Before Running Floor Planning we need to do few changes inside switches. These switches can be found inside configuration directory of openlane. We can set the variable inside the synthesis flow. These variable are nothing but switches.
Inside Floor Planning we have a variable FP_CORE_UTIL. Its by default set to 50%. Similary we have another variable for aspect ratio, which sets height and width of the core. by deafult its set to 1. There are other variables also available in floor plan, which can be set according to design requirements. We also have few variable inside Placemen, Clock Tree Synthesis etc.

Now lets see how to set the switches inside FloorPlan. Let us try to see, what are the default values.
![VirtualBox_VSD_20_05_2025_12_48_03](https://github.com/user-attachments/assets/f236e00e-1e4d-4744-b3b7-bcd0ca5cb937)
default parameters in the floorplan.tcl directory
![VirtualBox_VSD_20_05_2025_22_55_48](https://github.com/user-attachments/assets/51022e92-fcbe-443d-bb60-5e5112e1c920)

With the deafault settings, we will try to run the floorplan with the command run_floorplan
![VirtualBox_VSD_20_05_2025_12_55_43](https://github.com/user-attachments/assets/57240e44-e332-4aa0-97a0-2528727ca9a5)

# Reviewing Floorplan Files and Seeing the Floor Plan
lets go inside the runs directory in the picorv32a design to see and analyze the results.
![VirtualBox_VSD_20_05_2025_13_06_42](https://github.com/user-attachments/assets/db68c9f4-f6fc-4302-8b24-d0c3ab41f1c9)
seeing results of ioPLacer.log
![VirtualBox_VSD_20_05_2025_14_33_28](https://github.com/user-attachments/assets/75748d16-ea27-4dbf-ab8e-d1f7360d8255)
inside config.tcl
![VirtualBox_VSD_20_05_2025_14_40_18](https://github.com/user-attachments/assets/030956d3-35b3-4b3c-8266-3b2402d19137)

PDK specific config.tcl
![VirtualBox_VSD_20_05_2025_14_46_28](https://github.com/user-attachments/assets/4b7fe169-a36d-4cb2-8924-48b6ac649e0f)
core utilization of sky130A_sky130_fd_sc_hd_config.tcl has been considered for current floorplan and overwritten system default config.tcl
![VirtualBox_VSD_20_05_2025_23_18_17](https://github.com/user-attachments/assets/6ce6382b-baec-457f-af5b-81c143700f51)


def file inside the results
![VirtualBox_VSD_20_05_2025_14_50_42](https://github.com/user-attachments/assets/df7a0a71-0475-4014-872f-066d2a276880)
layout in the magic
![VirtualBox_VSD_20_05_2025_23_39_36](https://github.com/user-attachments/assets/c4b19450-f050-4e75-a973-f5ecb408006b)
vertical pins
![VirtualBox_VSD_20_05_2025_23_44_04](https://github.com/user-attachments/assets/8dd95b31-f797-4133-b43f-88de8ea1d92b)
tap cells are diagonically equidistant
![VirtualBox_VSD_20_05_2025_23_46_58](https://github.com/user-attachments/assets/4aa5f2d5-8220-4eaa-96d7-45c0a0cef533)
standard cells
![VirtualBox_VSD_20_05_2025_23_52_40](https://github.com/user-attachments/assets/606632c6-acbd-4c0e-abf5-9884ae4ff0cd)

# Placement using run_placement
here global placement is done with the motive to reduce wire length
![VirtualBox_VSD_21_05_2025_00_03_25](https://github.com/user-attachments/assets/ec7e5a74-55b4-4bf7-91ff-a20dd1927dce)
design in magic after placement is done.
![VirtualBox_VSD_21_05_2025_00_03_25](https://github.com/user-attachments/assets/2dc12a75-82fb-4c00-9dec-708a35c7cbf1)
placement ensures that standard cells are correctly placed.  
![VirtualBox_VSD_21_05_2025_00_11_10](https://github.com/user-attachments/assets/819d3f32-0ffa-4b3b-b6b0-f4ff7ae46408)
We can also do the changes in the run time. For example, we can set the distance between I/O pins as 2 and run the floor plan again.


















