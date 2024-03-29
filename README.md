date: 14/02/2024
GPIO(General Purpose Input Output) :
   It's generally used for readings digital signals,issuing interrupts,generating triggers for external coponents.


GPIO pin:
     * Generic pin whose value consists of one of two voltage settings (high or low).
     * Behavior can be programmed through software.


GPIO port :
     *Platform-defined grouping of GPIO pins (STM32 16 pins).


GPIO input mode with high impedance state :
      *After reset MCU default GPIO pins are Input Mode
      *Default GPIO pins will be in High Z state or Floating state
      *Neither high state or ground state
      *Keeping the pin in floating state lead to leakage current, more power consumption


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




15/02/24
   
    GPIO REGISTERS :
       This section gives a detailed description of the GPIO registers, for a summary of registrs address offsets and reset values.

GPIO port  Moder register(GPIO×MODER)(×=A..H)
       address offset : 0×00
    
 1) 0×A800 0000 for port A
 2) 0×0000 0280 for port B
 3) 0×0000 0000 for other ports
bits MODER[1:0]
    00- Input
    01- General purpose output mode
    10- Alternate function mode
    11- Analog mode

  GPIO PORTS ARE: 

- GPIO ×_OTYPER
- GPIO ×_OSPEEDR
- GPIO ×_ PUPDR
- GPIO ×_BSRR


Using bus AHPB1 peripheral starting address is 0×4002 0000 to 0×4002 03ff
   
 Registers name are given same address value. 
 these Address are not same .
In register have 10 register
 allocating byte have 8 bit in one byte
 
In Memory mapping,
     Bus are: 
    Cortex- M4 
    AHB3
    AHB2
    AHB1
    APB2
    APB1
    

16/02/24
   
   GPIO PORT(GPIO×_ ODR)
     
   Address offset: 0×14
   reset value : 0×0000 0000


These bits can be read and written by software. 
    
 GPIO PORT ( GPIO×_ IDR)
  
   Address offset:0× 10
   reset value: 0× 0000 XXXX
  
      These bits are read only and can be accessed in word mode only. they contain the input value of the corresponding I/O port. 

RCC and Clock control (RCC): 
  
       These are 3 types, system reset, software reset, low power management reset. 
  
   In given RCC register can be given value accessed by allocating bus values and address, then peripherals.

21/02/24
 
       USART 

Serial communication 
    
   Sender--------->Reciver
    
    MSB- most significant bit
    LSB- Least significant bit
  
In 16- bit msb, lsb can be in protocal.
using same frequency clock registers.


SYNCHRONOUS:
    A clock is transmitted with data.
ASYNCHRONOUS: 
     A clock is not transmitted with data.

Parallel Communication : 
   
   Reciver --------> transmitter
   
   in universal and Asynchronous.
   
 synchronous: 
---------------
    
    It is a full duplex.

transmitter ---------> Receiver

Receiver -------------> transmitter

Simplex : 
  
  data- transmitted only not receiver.
  only one direction.

Half Duplex: 
   
     only one way to at a time data can be transmitted.

 Full duplex: 
    
     both they are at a time data can be transmitted.


ASCII 
  
    Serial connection going to start bit and stop bit depend upon clock cycle.

- Mode
- Word length
- Hardware Flow Control
  
22/02/24
  
   Sudo minicom - s using this command 
       open the terminal last can be used to run the complie code in stm32cubeide, that are used in same minicom command to run the code.

    serial port--- Shift + A --- add one new file name ---  Shift + E --- change the hardware and software --- save as default --- then exit ---- automatically code can be complie --- output will be executed.

   
   using commands are ls /,ls/ dev , ls-l/dev
   
In rugged board,
   
      core --> Architecture (ARM)
      |
     SOC----> system on chip 
      |
     SOM----> system on module
      |
     SBC----> single board computer


SOC ----> ×= 7
A5D2X
  
  SOM ----> PYCORE A5D2X P2X
  
  SBC------> RUGGED BOARD A5D2X
   
  TO LEARN, 
    
  -Flash
  -Ram
  -boot/ sram 
  

Flash : 
 
   in mapping , ATA base strap , U boot, Dtb, Zimage ( kernel) , RFS .
 
   ATA base strap can be load a data in SRAM. 

FINALLY , 
  
 DTB --> it can be solving a problems 
  
expanding, DTSC ----> Device Tree Source File
           DTB ------> Device Tree Binary
           RFS ------> Root file System 

 RFS ___ Mount the data values in RAM... 