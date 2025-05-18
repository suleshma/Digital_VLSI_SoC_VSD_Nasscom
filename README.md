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
Having seens PDKs, Now lets work inside openLane 
