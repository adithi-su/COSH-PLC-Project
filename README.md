# COSH-PLC-Project
Atoliic TrueStudio, STL Linker, STM32F407 Discovery Kit <br>
Project installation files - https://drive.google.com/drive/folders/1Qda3X5TBNdP7TIRw4iMCDkEmkc2ffdsa?usp=sharing 


<b>25.1.22</b> <br>
Open source H/W development<br>
PLC (Programmable logic controller) <br>
STM 32 - ARM 32 bit controller <br>
ARM single core -> multicore -> (multi stage boot processing?) -> integrate with real time OS -> design and dev of device drivers<br>
Industrial applications - GPIU, UART drivers, developing small library routines (test with STM devices)<br>
To-Do: <br>
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
suspend works, millisec delay doesn't. why??

<b>1.3.22</b> <br>
task to be done - write a timer function. <br>
Go through the datasheet and understand timers. Timer #2. <br>
Implement for periodic functions.

<b>Online: </b><br>
T1 Blue LED ON <br>
T2 Red LED ON <br>
T3 Green LED ON <br>
T4 Yellow LED ON <br>
<b>Offline:</b> T5 Blue LED OFF <br>
<b>PRDC: </b>T6 Red LED OFF <br>
<b>BGND: </b>T7 all LEDs OFF <br>
Assignments: 
1. Test all the task functions 
2. Learn how timer software is coded
3. Start UART concept in STM32 

write UART driver ( printf statements) <br>
learn how to make GPIO connections to RS232 serial cable <br>
HAL interface <br>
GPIO based drivers 

<b>25.4.22</b> <br>
Tera Term setup - <br>
Receive tab - Auto <br>
Transmit tab - CR + LF <br>
rest - default <br>
need to write IRQ interrupts (GPIO based) <br>
whenever the pin is high/low, interrupt s/w is needed <br>
interrupts - asynchronous time<br>
periodic task - configure period and print <br>
IRQ - only for offline tasks <br>

