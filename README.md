# an_2565-toolchain-adaption
Modify an example from Atmels application note 2565 to a make/gcc based toolchain.

## Note ##
Atmels application note AN_2565 describes the usage of the *two wire interface* (TWI)
to implement the function of a i²c slave device, including some basic example code.
This examples have suitable configurations for the IDEs *Atmel Studio* and *IAR*.

## Purpose ##
To use it as a starting point for a project some work has to be done for building
with a linux make/gcc toolchain.

The code is taken from the subdirectory *Standard/Atmel Studio/TWI_Slave* and inititally
imported as it is.
