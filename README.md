# Quiz7
Polling Inputs
Connect two (2) active high push button to PORTB. Connect two (2) active low LEDs on PORTD. If the first push button is pressed,
the first LED on PORTD should light up. If the second button is pressed, the second LED should light up. Other than that, all LEDs
should turn off. 

#include<p18f4550.inc>

	org 0x00
	goto start
	org 0x08
	retfie
	org 0x18
	retfie
			
;Start program (DE96498)
start	CLRF TRISD,A
        SETF TRISB,A
        SETF PORTD,A

check	BTFSC PORTB,0,A
        BCF PORTD,0,A
        BTFSC PORTB,1,A
        BCF PORTD,1,A
        BRA check

	END
