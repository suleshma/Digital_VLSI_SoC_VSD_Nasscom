# Digital_VLSI_SoC_VSD_Nasscom
Exploring OpenLane
# Day:OpenLane Directory Structure
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




