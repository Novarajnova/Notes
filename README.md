date: 14/02/2024
GPIO(General Purpose Input Output) :
   >> It's generally used for readings digital signals,issuing interrupts,generating triggers for external coponents.


GPIO pin:
     >> Generic pin whose value consists of one of two voltage settings (high or low).
     >> Behavior can be programmed through software.


GPIO port :
     >> Platform-defined grouping of GPIO pins (STM32 16 pins).


GPIO input mode with high impedance state :
      -After reset MCU default GPIO pins are Input Mode
      -Default GPIO pins will be in High Z state or Floating state
      -Neither high state or ground state
      -Keeping the pin in floating state lead to leakage current, more power consumption


GPIO input mode :
    1.pull- up state
    2.pull- down state


GPIO output mode with open drain state:
      1.Open-drain output configuration is nothing but the top PMOS transistor is deactivated
      2.When the transistor is ON, the pin pulled to the ground.
      3.When the transistor is OFF, the drain of the transistor will be floating or open.
      4.That’s the reason it is called an open drain.


GPIO output mode with push pull state :
     1.Default configuration of any GPIO pin in output mode.
     2.Enable GPIO port by default, its pin will be in input mode.
     3.Set any pin as the output mode, then by default it will be in push-pull configuration.
     4.Push-pull output uses two transistors. Each will be on to drive the output to the appropriate level.
