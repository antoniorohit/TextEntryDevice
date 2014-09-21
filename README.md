VIEW THIS FILE IN RAW!!

TextEntryDevice
===============
Text Entry Device created within a week for the Interactive Device Design Course at Berkeley, Fall '14

Objectives:
 - Create an innovative text entry device using less than 10 push buttons
 - Get familiar with the Freescale KL25Z M0+ board and mbed development environment
 - Have fun!
 
Description:
 - This device consists of a 3x3 array of LDRs and 3 buttons below them (see figure below)
  _________
 |-O--O--O-|\
 |-O--O--O-| |>  Character grid (LDRs)
 |-O--O--O-|/
 |_________|
 |-o--o--o-|
 |_________|
   ^  ^  ^
   |  |  |______ TBD button
   |  |_________ Backspace button
   |____________ Space button
   
   - The user draws the character s/he wants by using a flashlight as a stylus. The input pattern is sent to the PC over
     serial. The PC decodes the pattern (into an ASCII character) and sends it back to the board. The character is then played
     on a speaker by the microcontroller using the onboard DAC.

eg. A                
  _________
 |-X--X--X-|
 |-X--X--X-|
 |-X--.--X-|
 |_________|
 |-o--o--o-|
 |_________|
 
 O
  ________
 |-X--X--X-|
 |-X--.--X-|
 |-X--X--X-|
 |_________|
 |-o--o--o-|
 |_________|
 
 C
  ________
 |-X--X--X-|
 |-X--.--.-|
 |-X--X--X-|
 |_________|
 |-o--o--o-|
 |_________|
 
 Challenges:
 - This keyboard needs 9 LDRs but KL25Z has only 6 analog inputs. Solution: Use digital inputs and an appropriate resistor
   circuit
 - Playing sounds using the DAC - the sounds need to be saved on the microcontroller somehow. Solution: Get recordings of the
   alphabet from the web, clip them short, use WAVtoCode software to convert to C array, save it in the micro (Flash). Turns out 
   there's just enough memory for the 26 letters!
 - Decoding the pattern - a LUT is required. Solution: Create it, and store this in the PC. 
 - GUI would be nice. Solution: Use Processing to draw a 3x3 grid of squares. 
