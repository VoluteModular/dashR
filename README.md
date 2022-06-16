# dash-R
<h2>Digital Analog Shift Register</h2>
<br>
<p>
The Digital Analog Shift Register is a module that mimics the functionality of a standard Analog Shift Register, but it uses 4 inexpensive DAC modules along with an ATMega 328 processor. Thus the "digital" part. Because it is digital, it comes with some interesting options. For one, the outputs can be quantized according to one of 15 scales (along with free running). These scales can be modified in software if the user is able to flash the ATMega 328. Also, because this module is digital, it can emulate a larger shift register. In this case it is set up as a 16 stage shift register. By default the outputs correspond with stages 0-3, but each output can be moved to a different stage using the selection buttons and position knob. Another benefit of the digital version is that each stage will hold the voltage indefinately, so the incoming triggers can be as slow as you like
  
<ul>
  <li>2 3.5mm inputs:</li>
  <ul>
    <li>CV-In:
    <ul>
      <li>Expects 0-5V, but is tolerant of -12 to 12V</li>
      <li>When a shift pulse is recieved, the voltage at CV-In is stored in register 0</li>
    </ul> 
  <li>Shift In:
    <ul>
    <li>This input expects a 5V trigger pulse to rotate the shift register. It is tolerant of higher voltages.</li>
    </ul>
  </ul>
  <li>5 3.5mm outputs:</li>
  <ul>
    <li>Pulse Out:</li>
    <ul>
      <li>This output is a duplicate of the rotate input. When a trigger is received on the input, a pulse is sent on the pulse out. The length is a default of 5ms, but can be changed in software</li>
    </ul>
    <li>Shift Register Outputs 1-4:</li>
    <ul>
    <li>The voltages that are recieved at the CV-In are shifted out to register 0, then 1,2,3 as a shift trigger is received at the shift input.
    By default, the outputs are mapped to the 0,1,2,3 registers. This can be changed by using the buttons and the position knob.</li>
    </ul>
  </ul>
  <li>Knobs:</li>
  <ul>
    <li>Scale Knob:</li>
    <ul>
      <li>This knob changes the quantization of the outputs. Here are the default options:</li>
      <ul>
        <li> 0 MAJOR(IONIAN)</li>
        <li> 1 DORIAN
        <li> 2 PHRYGIAN
        <li> 3 LYDIAN
        <li> 4 MIXOLYDIAN
        <li> 5 AEOLIAN
        <li> 6 CHROMATIC
        <li> 7 OCTAVE
        <li> 8 POWER CHORD
        <li> 9 MAJ PENT
        <li> 10 MIN PENT
        <li> 11 BLUES
        <li> 12 MAJ 7th
        <li> 13 MIN 7th
        <li> 14 WHOLE TONE
        <li> 15 FREE RUNNING (no quantization)
      </ul>
    </ul>
    <li>Position Knob:</li>
    <ul>
      <li>This knob is used to change the position of each shift register outputs. Each shift register can take the position of 0-15 </li>
    </ul>
  </ul>
  <li>4 Buttons</li>
  <ul>
    <li> There are four buttons. Each selects the corresponding shift register output in order to change its position in the 16 stage shift register.</li>
  </ul>
    
  <li>4 LEDs:</li>
  <ul>
    <li>These LEDs are used as visual outputs when choosing a scale or setting the position of the shift register. They display the numbers 0 - 15 using binary notation, so going from right to left they represent 1,2,4,8</li>
  </ul>
  </ul>
  </ul>
  </ul>
<h2>Usage</h2>
<p>
  Connect a CV source to the CV-In Input Jack. Ideally, this CV source will be 0-5V, but voltages less than 0V will be treated as 0V and voltages over 5V will be treated as 5V.<br><br>
  
  Connect a trigger to the Shift Input Jack. This could be a trigger from a clock generator for example.
  <br><br>
  By default, the output jacks correspond with the first four stages of the shift register. For example, if there is 1V at the CV In jack and the shift input is triggered, 1V will be present at output jack 0. After another trigger, the 1V will move to output jack 1, then 2, then 3.
  <br><br>
  By default, the quantization is set to scale 0 which is the Major scale. In order to change the scale, you must first move the knob to the 0 position (fully counter-clock wise) before it will change. Once you reach the current scale value, you can change to a new one. The scale is indicated by the binary LEDs. So 0111 represents scale 7 with 0 meaning the LED is off and 1 meaning the LED is on. A binary table can be found at the bottom of this page.
  <br><br>
  In order to change the position of a shift register output, you first press the button for the shift register output. The current position of the register output will be displayed in binary notation on the LEDs. In order to change it, you must first turn the knob to the position of the current shift regiser output. 0 is totally counter clock wise and 15 is clock wise. Once you hit the current position, you can then change the position. You can exit this editing mode by hitting the same button again or pushing one of the other buttons. Each shift register can be in any position from 0-15. This means one or more shift register can be in the same position, in which case they will always have the same voltage present. It also means they do not need to be in order. For example, shift register output 0 could be in position 7 while shift register output 1 could be in position 5.
  
Here is an example of how chords can be created using the shift register:
  <table>
    <tr>
      <td> </td> <td>Trig 1</td><td>Trig 2</td><td>Trig 3</td><td>Trig 4</td><td>Trig 5</td>
    <tr>
      <td>Register 0</td><td>C</td><td>G</td><td>E</td><td>A</td><td>D</td> 
    </tr>
    <tr>
      <td>Register 1</td><td> </td><td>C</td><td>G</td><td>E</td><td>A</td>
    </tr>
    <tr>
      <td>Register 2</td><td> </td><td></td><td>C</td><td>G</td><td>E</td>
    </tr>
    <tr>
      <td>Register 3</td><td> </td><td></td><td></td><td>C</td><td>G</td>
    </tr>
  </table>

        
