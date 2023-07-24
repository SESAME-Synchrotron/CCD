Data Collection and Analysis
============================
.. contents:: Table of Contents
   :depth: 2
Data Collection at SESAME
-------------------------

Data Collection and Analysis at SESAME is was activate begging of 2021 


There tasks 

- smooth and reliable data collection

- data analysis

- data storage

- provding essential pre and post processing tools

Experimental Data Management Policy of SESAME
---------------------------------------------

Policy Statement
................


The purpose of this Policy is to provide information and guidance to users conducting peer-reviewed and Director Discretionary time research on experimental data ownership, storage, access, and management. 

Coverage
.........

- This policy applies to raw data and metadata generated from peer-reviewed and Director Discretionary time research proposals and in-house experiments.
- It does not cover proprietary and industrial research conducted by Participatory Research Teams

General Principles
..................

- Acceptance of this Policy is a precondition for obtaining beam time for peer-reviewed and Director Discretionary time research proposals and in-house experiments.
- SESAME will strive to maximize long-term curation of data for a minimum of 5 years, with a target of 10 years.

Definitions
...........

- Experimental Data: Umbrella term for raw data and all associated metadata.
- Metadata: Information related to the experiment and experimental conditions.

Data Ownership and Access
..........................

- Raw data and associated metadata will become open access after a 3-year embargo period,
- Data and metadata will be curated in well-defined formats for long-term access.

Results
.......

- Ownership of results derived from data analysis will be determined by contractual obligations of individuals performing the analysis.
- SESAME will provide best effort curation of results and act as the long-term custodian.

Publication
...........

- Publications related to SESAME experiments must cite the persistent identifier of the experiment and data.
- References of related publications must be deposited in a publications database within 3 months of the publication date or during new beam time applications.

Compliance
...........
- Acceptance of the Experimental Data Management Policy is a precondition for obtaining beam time.
- Deliberate infringement may result in denial of data access and rejection of future beam time applications.

Tomoscan 
---------

it is a python based software for tomography data collection and analysis. 
which is used to collect data from SESAME tomography beamline.


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
- ``hi_lim``: The soft-coded higher limit on the position of the motor.
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
- ``change``: Used to change a preexisting motor in the JSON file.
    - Usage: ``change json_path motor_name pv_root lo_lim center hi_lim``
    - ``json_path``: The path to the JSON file containing the general and motor configurations.
    - ``motor_name``: The name of the motor to be changed.
    - ``pv_root``: The PV root name used to access the motor.
    - ``lo_lim``: The soft-coded lower positional limit for the motor.
    - ``center``: The center position for the motor where it will be directed after homing.
    - ``hi_lim``: The soft-coded higher positional limit for the motor.
- ``remove``: Used to remove a preexisting motor from the JSON file.
    - Usage: ``remove json_path motor_name``
    - ``json_path``: The path to the JSON file containing the general and motor configurations.
    - ``motor_name``: The name of the motor to be removed, or ``all`` to remove all available motors.
- ``home``: Used to begin homing for one or all of the motors.
    - Usage: ``home json_path motor_name homing_mode``
    - ``json_path``: The path to the JSON file containing the general and motor configurations.
    - ``motor_name``: The name of the motor to be homed, or ``all`` to home all available motors.
    - ``homing_mode``: The method to be used in homing, either ``hi`` to use the higher limit or ``lo`` to use the lower limit.

For example, in order to home all of the motors using the higher limit, navigate to the directory containing the Python script in the terminal and run:

.. code-block:: bash
    python3.9 test.py home test.json all hi
Where ``test.py`` is the Python script file name and ``test.json`` is the JSON file name.

Detector
........

EPICS-Qt-Based Client for Collection of Data from Testing Bench 
----------------------------------------------------------------

Motion Box
...........
A GUI was developed using Qt in order to more easily home the motors, as in Python-Based Client for Collection of Data from Testing Bench. This GUI consists of:
- A QComboBox (like a dropdown menu) for selecting one or all of the motors.
- Four QLineEdits (like textboxes) for viewing and modifying the ``pv_root``, ``lo_lim``, ``center``, and ``hi_lim`` for the selected motor in the JSON file (is blank when all motors are selected).
- A QPushButton for adding a new motor to the JSON file.
- A QPushButton for removing the selected motor(s).
- Two QPushButtons for homing the selected motor(s) using either the higher limit or the lower limit.

This GUI operates by sending commands to the Python script described in Python-Based Client for Collection of Data from Testing Bench via the terminal. It is therefore fairly finicky, as there isn't much feedback displayed in the GUI, and the directories for the Python script and the JSON file are hardcoded into the GUI.


Detector
........

Software and Hardware Synchronization
--------------------------------------