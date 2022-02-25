# COSH-PLC-Project
Atoliic TrueStudio, STL Linker, STM32F407 Discovery Kit <br>
Project installation files - https://drive.google.com/drive/folders/1Qda3X5TBNdP7TIRw4iMCDkEmkc2ffdsa?usp=sharing 


<b>25.1.22</b> <br>
Open source H/W development<br>
PLC (Programmable logic controller) <br>
STM 32 - ARM 32 bit controller <br>
ARM single core -> multicore -> (multi stage boot processing?) -> integrate with real time OS -> design and dev of device drivers<br>
Industrial applications - GPIU, UART drivers, developing small library routines (test with STM devices)<br>
To-Do- <br>
Revise C <br>
bitwise, unions, fxn prototypes <br>
learn how to read datasheets <br>

Edit- <br>
STM32F407 pin structure, datasheet - go through<br>

<b>22.2.22</b> <br>
Call led APIs <br>
Call different leds for different tasks <br>
Suspend it for a few seconds 1000ms <br>
4 tasks - one by one using rtos <br>
To check if the scheduler is working fine <br>

Fix1: heap error <br>
Make a new folder and add these files : libs.ld; men.ld; sections.ld <br>
Project -> Properties -> C/C++ Build -> Settings -> Tool settings -> C Linker -> append by adding -T “location\of\the\3files” separately <br>
Fix2: calling stlmain(); in main<br>
Include this prototype -<br> 
extern void stlmain(void); <br>

<b>25.2.22</b><br>
Tasks: <br>
Offline - becomes active if event occurs for that; event driven task <br>
Periodic- becomes active when timer expires /timeout happens <br>
Online and background- cycle repeats automatically <br>
Offline class will work without timer by suspending for 1 sec. Similarly for periodic.   <br>
Note : this is not freeRTOS <br>
Edit -  read up on rtos scheduling <br>
