# dash-R
<h1>dash-R is a Digital Analog Shift Register</h1>

2 3.5mm inputs:
  CV-In:
    Expects 0-5V, but is tolerant of -12 to 12V 
    When a shift pulse is recieved, the voltage at CV-In is stored in register 0
  Shift:
    This input xpects a 5V trigger pulse to rotate the shift register. It is tolerant of higher voltages.
5 3.5mm outputs:
  Pulse Out:
    This output is a duplicate of the rotate input. When a trigger is received on the input, a pulse is sent on the pulse out. The length is a default of       5ms, but chan be changed in software
  Shift Register Outputs 1-4:
    The voltages that are recieved at the CV-In are shifted out to register 0, then 1,2,3 as a shift trigger is received at the shift input.
    By default, the outputs are mapped to the 0,1,2,3 registers. This can be changed by using the buttons and the position knob.
2 Knobs:
  Scale Knob:
    This knob changes the quantization of the outputs. Here are the default options:
     
