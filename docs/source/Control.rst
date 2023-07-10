Control Engineering
===================

Control Systems and Introduction to the EPICS Toolkit
-----------------------------------------------------
**Accelerator Control System:** connects the Operator in the control room with the accelerator hardware. The control room might not be near the accelerator.

*For example:* SESAME has N Computers, N magnets, N vacuum pumps, 5 beamlines, a cooling system, RF system, power supply system, ... etc. which all need to be closely and heavily controlled.

PICTURE slide 4

**Experimental Physics and Industrial Control System (EPICS)**: is a collaboration software tool kit, that provides a control system architecture suitable for research and industrial facilities such as accelerators. EPICS uses a Client/Server and Publish/Subscribe methods and a Channel Access network protocol (3-tier architecture or 3 layer model). 

PICTURE slide 10

EPICS is an *open-sourced* project assembeled by multiple collaborators in the accelerator industry, 12+ accelerators around the world have provided assistance in its development and still use it to this day. 


**Channel Access:** A protocol to transfer data over network, a single data unit is called a **Process Variable**. The entire set of Process Variables establish a Distributed Real-time Database of machine statis, information and control parameters.

PICTURE Slide 11

**Channel Access Network Flow:**

1) Query: broadcast and connection request.
2) Answer: direct connection
3) All further queries and answers work directly (Point-To-Point)

Picture Slide 12

**Main Access Commands in EPICS:**

- ``caget``: returns the value of the PV or any sub-fields in the PV. 
- ``caput``: sets a value of a PV or a sub-field in a PV to a desired value and displays the old and newly assigned values.
- ``camonitor``: sets up a monitor and continuously prints incoming changing values for PVs.
- ``cainfo``: Prints all available channel status and information for a PV.

PICTURE slide 14


EPICS Installation on Rocky Linux
---------------------------------

Packages installation and there purpose 
......................

.. Make list for  GCC ,GCC-C++ , GCC-Toolset-9-make , Readlline-Devel

- **gcc**: GCC stands for GNU Compiler Collection. It is a collection of programming language compilers and tools, primarily used for compiling and linking C, C++, and Fortran programs. GCC supports multiple platforms and is widely used in the development of software applications.

- **gcc-C++**:This package is an extension of GCC and specifically includes the C++ compiler. It is required if you want to compile and build C++ programs using GCC. The package provides the necessary libraries and headers for C++ development.


- **make** : Make is a utility used for building and managing software projects. It is used to automate the process of building executable programs and libraries from source code. The "make" utility uses a "Makefile" to define the build process. It is a text file that contains instructions for the "make" utility to execute. The "make" utility is often used in conjunction with the GCC compiler to build software projects. The "make" utility is included in the "Development Tools" package group. If you have already installed the "Development Tools" package group, you do not need to install the "make" utility separately.


- **gcc-toolset-9-make**: This package is a part of the GCC Toolset, which is a collection of development tools and libraries. It includes the "make" utility, which is used to manage and build software projects. The version number "9" in the package name refers to the specific version of the GCC Toolset. It is likely that this package includes GCC version 9 and the associated "make" utility.


- **readline-devel**: The readline library is used for line editing during command-line input. It provides features like command history, editing capabilities, and tab completion. The "readline-devel" package contains the development files and headers needed to compile programs that use the readline library. If you are building a program that requires readline functionality, you would need this package.
 

- **perl-ExtUtils-Install**: Perl is a popular scripting language used for various purposes, including system administration and web development. The "perl-ExtUtils-Install" package is a Perl module used for installing Perl extensions and modules. It provides tools and utilities to simplify the installation process of Perl packages.



.. code-block:: bash

    sudo yum install perl-ExtUtils-Install





EPICS IOC Creation
------------------

IOC Database
............

IOC Hypotenuse Project Exercise
...............................

IOC Python-Based Scripting
..........................

IOC Qt-Based Scripting (C++)
............................

EPICS IOC Creation and Running (SIEMENS PLC)
--------------------------------------------

Programmable Logic Controllers (PLCs) EPICS Interface
-----------------------------------------------------

EPICS-Qt (GUI design and Implementation)
----------------------------------------

