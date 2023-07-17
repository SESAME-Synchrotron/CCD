Data Collection and Analysis
============================

Data Collection at SESAME
-------------------------

Data Acquisition Testing Bench
------------------------------
The testing bench consists of five motors, from A to E, that can be controlled using EPICS. These motors are used to test various control programs that are to be used at SESAME beamlines.

Python-Based Client for Collection of Data from Testing Bench 
--------------------------------------------------------------

Motion Box
...........
A Python script was developed in order to home each of the motors in the testing bench. This is necessary in order to ensure the motors are calibrated correctly. 

The script works using a JSON file containing parameters for each motor in the testing bench. Specifically, these parameters are:

- ``pv_root``: The root of all of the PVs associated with the motor.
- ``lo_lim``: The soft-coded lower limit on the position of the motor.
- ``hi_lim``: The soft-coded upper limit on the position of the motor.
- ``center``: The "default" position of the motor, where it will be taken after the homing is complete (often takes on the value of 0).

Additionally, the JSON file contains general configuration parameters. For now, the only parameter is the tolerance, which is the difference between the hard limits and the soft limits on the motor positions.

This script is controlled via the terminal, and has five commands that can be executed:

- ``help``: Used to get usage information regarding a given command.
    - Usage: ``help command_name``
    - ``command_name``: The name of the command that the user would like help with.
- ``add``: Used to add a new motor to the JSON file.
    - Usage: ``add json_path motor_name pv_root lo_lim center hi_lim``
    - ``json_path``: The path to the JSON file containing the general and motor configurations.
    - ``motor_name``: The name of the motor to be added.
    - ``pv_root``: The PV root name used to access the motor.
    - ``lo_lim``: The soft-coded lower positional limit for the motor.
    - ``center``: The center position for the motor where it will be directed after homing.
    - ``hi_lim``: The soft-coded higher positional limit for the motor.


Detector
........

EPICS-Qt-Based Client for Collection of Data from Testing Bench 
----------------------------------------------------------------

Motion Box
...........


Detector
........

Software and Hardware Synchronization
--------------------------------------