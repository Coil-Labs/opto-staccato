# opto-staccato

## Introduction
This is a pair of circuit boards (PCBs), known as the Opto-Staccato Controller and Receiver, which are a mains frequency synchronized interrupter for Tesla coils, primarily vacuum tube Tesla coils (VTTCs).

This circuit is based on the original Staccato Controller, created by Steve Ward https://www.stevehv.4hv.org/staccato.htm

This circuit is featured on the Coil Labs YouTube channel and is used to interrupt a large VTTC (https://youtu.be/IDOrxT_r8TY). This project was sponsored in part by PCBgogo (https://www.pcbgogo.com/), who provided the PCBs for this video.

The KiCad source files for both boards are available in this repository and the gerber files for both boards are available as .zip files in the Releases.

## Description

The Controller PCB detects the mains frequency zero crossing and then sends a pulse to the Receiver (with a controllable delay based on potentiometer RV1), signaling when to let the Tesla coil primary circuit to begin conducting. This signal is sent over a fiber optic link to protect the user from coming into contact with high voltage and enabling them to maintain a safe distance from the Tesla coil. The other controllable parameter (set by potentiometer RV2) of the Controller is the interrupter hold-off time, which enables the Tesla coil to be driven at integer factors of the mains frequency (e.g., 60 Hz, 30 Hz, 15 Hz, etc. in North America).

## Safety
WARNING! High voltage electricity and Tesla coils are dangerous and should not be handled or operated by anyone other than trained experts! 

## Usage
Jumpers J5 and J6 on the Controller and J7 and J8 on the Receiver enable using the PCBs in either 120V or 240V mains regions. Place two jumpers across pins 1 and 2 of both jumpers for 120V use or a single jumper across pin 2 of the two jumpers for 240V use, as indicated on the silk screen.

On the Controller, switch SW1 is the "phase-select" choosing to trigger the circuit on either the rising or falling mains zero crossing. Switch Sw2 is the "output-enable" switch, allowing the user to control when the Tesla coil interrupter is "turned on". Switch Sw3 selects the source of the signal being sent out via the fiber optic link; either the Staccato signal, "always on" for continuous wave operation, or an optional external 0-12V digital signal that can be provided via screw terminal J2.

The SCR or TRIAC used for Staccato operation is not included on the Receiver PCB as the choice of this component is specific to each Tesla coil. A screw terminal block J4 is provided to connect to the gate and cathode terminals for triggering. The selection of resistor R22 may need to be changed, depending on the gate voltage and current requirements of the SCR/TRIAC being used.

The fiber optic transmitter and receiver use standard 1000um core, 2.2mm jacket plastic fiber cable. The fuses are 500mA, 250V, fast blow, glass cartridge, 5mm x 20mm.

## License
These design files are published under the CERN Open Hardware License Version 2 - Weakly Reciprocal variant (CERN-OHL-W). Read more here (https://cern.ch/cern-ohl).

This is a copyleft, share-alike, open-source license. This means that you are free to redistribute, modify, or make derivatives these designs, and even commercialize them. But you MUST keep the redistributed, modified, or derivative designs open-source and under this or a compatible license. You CANNOT make modified or derivative designs proprietary; they MUST be kept open-source. This is different than a "permissive" open-source license, where you can make modifications or derivatives proprietary and then commercialize and profit off of your proprietary modification. You are absolutely free to commercialize and profit from modifications of this design, however, it must remain open-source and accessible to the public. Copyleft, share-alike is a philosophy. Scientific and engineering knowledge should not be kept as trade secrets and locked down under patents, owned by the wealthy, to only benefit the wealthy. Knowledge should be freely shared, always. Publishing scientific and engineering works under copyleft, share-alike licenses helps to create a more fair and democratic future where the hoarding of trade secrets is not a way to gain a competitive advantage. Please consider publishing your own works under such a license.

## Controller Schematic
![Controller Schematic](/opto_staccato_controller/opto_staccato_controller_schematic.jpg)

## Receiver Schematic
![Receiver Schematic](/opto_staccato_receiver/opto_staccato_receiver_schematic.jpg)
