Debouning in Mechanical Switches:
  Electrical switches have mechanical parts which act as a ‘spring’, this causes
  bouncing of contacts and a series of on/offs instead of one clean transition.

**Debouncing using Polling** -- Check how long the signal has been low. If low continuously for
required time then the switch is pressed and stable. 

1. Setup a counter variable, and initialize to zero.
2. Setup a regular sampling window. Use a period of about 1ms.
3. On a sample window:
    4. if switch_signal is high then
        5. Reset the counter variable to zero
        6. Set internal_switch_state to released
    7. else
        8. Increment the counter variable to a maximum of 10
    9. end if
10. if counter = 10 then
    11. Set internal_switch_state to pressed
12. end if
13. system_delay(1)

**Debouncing using interrupts**
1. Setup a previous_time variable, and initialize to zero.
2. Setup a rising edge interrupt connected to the switch.
3. In the Interrupt Service Routine (ISR):
    4. if (current_system_time – previous_time) > 10 then
        5. if switch_signal is high then
            6. Set internal_switch_state to released
        7. else
            8. Set internal_switch_state to pressed
        9. end if
    10. end if
11. previous_time = current_system_time

**What's the difference between polling vs interrupts?**
Polling: You pick up the phone every few seconds to check whether you are getting a call
Interrupt: Do whatever you should do and pick up the phone when it rings

**General Purpose Input Output**
Pins on the STM32F4 must be configured as one of the following:
 * Input, Output, Interrupt or Alternate function (i.e., PWM, USART...)
 * Each of these pins must be configured as a pull up/down or an open drain output. 
    * Pull-Up Resistor: Ensures default high state (logic 1).
    * Pull-Down Resistor: Ensures default low state (logic 0).
    * Open-Drain Output: The pin can pull the line low or leave it floating, with an external pull-up to ensure a high state.

Registers for each pin:
  * Output Data (ODR)
  * Input Data (IDR)
  * Mode (MODER)
  * Alternate Function (AFR)
  * Pull up/down (PUPDR)
  * Speed (OSPEEDR)
