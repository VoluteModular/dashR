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
    <li>This input xpects a 5V trigger pulse to rotate the shift register. It is tolerant of higher voltages.</li>
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
  <li>4 LEDs:</li>
  <ul>
    <li>These LEDs are used as visual outputs when choosing a scale or setting the position of the shift register. They display the numbers 0 - 15 using binary notation, so going from right to left they represent 1,2,4,8</li>
  </ul>
  </ul>
  </ul>
  </ul>

     
