
# Drosophibot II PCBs
Power and signal PCBs for the biomimetic fruit fly robot Drosophibot II. More information about Drosophibot II can be found in [Goldsmith et al. 2024](https://iopscience.iop.org/article/10.1088/1748-3190/ad80ec) and [Goldsmith 2025](https://researchrepository.wvu.edu/etd/12842/). CAD files for the robot can be found in the [`Drosophibot-II-CAD`](https://github.com/CAGoldsmith/Drosophibot-II-CAD) repository.

This repository contains:
- ZIP files of the Gerber and drill files necessary to manufacture each board
- PDFs with renders and schematics of the boards
- A `.f3z` file of each board containing the design files from Fusion

## Board functions
### 18 Position OpenCM MUX
An 18 position demultiplexer (routing 18 signals into 6 analog ports) for the Robotis OpenCM9.04 microcontroller. Designed to sit on top of the microcontroller as a shield.

### 36 Position OpenCM MUX
A 36 position demultiplexer (routing 36 signals into 6 analog ports, one for each robot leg) for the Robotis OpenCM9.04 microcontroller. Designed to sit on top of the microcontroller as a shield. Additionally includes multiplexing of the board's I2C ports to route the signal to each leg.

### Six Strain Amplifier
Board intended to amplify and route six analog strain signals, as well as digitally calibrate the rest level of each signal. It contains a Wheatstone bridge circuit for each signal with a digital-potentiometer (digipot) included for bridge balancing via I2C connection from the robot's microcontroller. Each strain signal is then routed into an instrumentation amplifier for amplification before being output. Analog switches are used to multiplex the I2C signal to one half of the board at a time (necessitated by the limited possible unique digipot IDs).  

### Drosophibot Power Board
Board to supply power from the offboard power supply and route the Serial control signal from the robot's computer to all of the robot's actuators. Includes power indicator LEDs as well as removable shunts to easily add/remove power to each leg.

## Editing in Autodesk Fusion 360
Download the relevant board's `.f3z` file and open it in Fusion to import the design files. 

## Manufacturing
Download the "<board name>_CamFiles" zip file for the desired board in the board's "CAMOutputs" folder. For example, for the 36 Position OpenCM MUX, the required file would be "36PosMUX_CamFiles.zip." All boards were designed with professional PCB manufacturing in mind, so the Design Rules may need to be changed in Autodesk for places with less capability (e.g., campus makerspaces).
