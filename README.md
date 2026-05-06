# Solenoid-Driver-PCB

This project is a component of a piano-playing robot. The solenoid driver drives 6 solenoid actuators, which press the piano keys. 


Inputs: Powered by 12V and 1A. This generates a sufficient amount of force on the keys without breaking the MOSFET or any other components. The MOSFET Gate is controlled by a 3.3V MCU GPIO pin.


Design Decisions:

- MOSFET: I chose to use a low-side NFET for simplicity and a lower RDS.
  
- Diodes: The rectifier diode in series with a zener diode clamps down the current produced by a back EMF from the inductive solenoid upon switching off the MOSFET. The zener diode clamps down the current faster than just using a rectifier diode, to ensure fast switching capabilities.
  
- Pull-down resistors: Used to prevent floating voltages when there is no MCU signal.
  
- Decoupling capacitor: Used to stabilize ripple voltage upon switching, acting as a charge reservoir.


<img width="438" height="343" alt="image" src="https://github.com/user-attachments/assets/f0f7b508-d623-4b49-b7db-2c6fd8dd0ba6" />
