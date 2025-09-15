# Simplified Secure Water Treatment (SSWaT) system testbed with a Python physical process simulator

## Description
This testbed has been specifically designed to evaluate a SciPy-based physical process simulator, developed to replace the heavyweight MATLAB Simulink simulator within the HoneyICS honeynet, created by Marco Lucchese et al. It replicates an Industrial Control System (ICS) up to the Supervisory level of the Purdue model for a three-tank water treatment system. The architecture, technologies, and tools of this testbed are inspired by the HoneyICS honeynet. The simulated physical process is a simplified version of the Secure Water Treatment (SWaT) testbed, originally developed by iTrust, and it is designed to assess the SciPy-based simulator in a hydraulic context with a relatively slow system.

The testbed consists of five Docker containers, which are as follows:
- Three Virtual PLC containers: Each container runs a virtual PLC implemented through OpenPLC. These PLCs monitor sensors and control actuators within the simulated tank system. Additionally, the PLC-2 container includes a Python broker to simulate communication between PLC-2 and PLC-1.
- Physical process simulator container: This container runs a Python physical process simulator that uses the SciPy library and first-order differential equations to model the physical processes occurring in the water treatment tank system.

## Main file descriptions
- build_system.sh: A Bash script that builds docker images and runs the docker containers of the system (PLCs, SCADA HMI and Python-based simulator).
- start_system.sh: A Bash script that starts docker containers of the system.
- stop_system.sh: A Bash script that stops docker containers of the system.

## Docker images building and containers running

```bash
  sh ./build_system.sh
```

## Starting the system

```bash
  sh ./start_system.sh
```

## Stopping the system

```bash
  sh ./stop_system.sh
```

## Important note about OpenPLC instances
When you start the system for the first time you have to click on "Save changes" button in the "Hardware" page for each OpenPLC istance. Then you have to restart the system.
