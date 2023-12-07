# Verilog_FGPA_Digital Clock

Design description: 
A digital clock has been designed with Verilog and DE10 Lite. This clock has four(4) functionalities and the ‘mode’ module helps to select between these functionalities as described below: 

A base clock: Right after starting the program, HH (HEX5 and HEX4) will start blinking indicating the user needs to input time. Users can use SW[5:0] to input time. KEY[0] will be used to lock in time for HH, and MM(HEX3 and HEX2) will blink and same procedure for SS(HEX1 and HEX0) with KEY[0] locking in each time.  SW[7] will lock-in the time in HH:MM:SS format (24 h format) and SW[9] will initiate the clock mode. KEY[1] button will be used for start-pause-resume. 

Alarm clock: The same time can be used for the alarm clock or the user can reset the time turning of SW[9] (sw[9] will be low) and pressing KEY[1]. After a new time has been set, lock-in the time using SW[6], and start the alarm clock mode turning on SW[8] and it will start counting down. Once it reaches 00:00:00 (HH:MM:SS), it will keep blinking until resetting (KEY[1]).

A stop-watch: This design limits stop-watch to one hour and  it starts from milliseconds (HEX0 and HEX1), moving towards seconds(HEX2 and HEX3) and minutes(HEX4 and HEX5) and goes up to 59 minutes and 59 seconds. To turn on the stop-watch mode SW[9] and SW[8] will be on high, and SW[5] will pause and resume the stop-watch. KEY[0] can detect upto three lap-sessions and the time difference can be shown using SW[2:0].

A timer: Designs  default mode has been set to timer. SW[0] and SW[1] will be on high for the timer. SW[9] will start the timer (counting upto 23 hours 59 minutes and 59 seconds) and SW[8] will be used to pause and resume the timer. 
