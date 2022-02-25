# COSH-PLC-Project
Atoliic TrueStudio, STL Linker, STM32F407 Discovery Kit 

22.2.22 <br>
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

25.2.22<br>
Tasks: <br>
Offline - becomes active if event occurs for that; event driven task <br>
Periodic- becomes active when timer expires /timeout happens <br>
Online and background- cycle repeats automatically <br>
Offline class will work without timer by suspending for 1 sec. Similarly for periodic.   <br>
Note : this is not freeRTOS <br>
%------ read up on rtos scheduling -----------%
