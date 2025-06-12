# Automated test framework (UART test)

This project is a modular, automated device test platform that supports users to enter device serial numbers, select test plans, and automatically complete all steps.

## Usage(Methods)

1. Run 'GUI.py', enter serial numbers and select test items

2. The program will automatically start testing according to the plans and commands defined in YAML

3. After the test is completed, test statistics and response records will be output

## File description

- 'library/*.yml': command data and test plan

- 'core/*.py': test main control logic and verification

- 'comm/*.py': UART serial communication processing

- 'gui/*.py': interface operation module

## Dependent modules

## System module architecture

# GUI.py

User interface, input the test machine serial number, select the test project

Execute the control process to start

# Process_Control.py

Core main control logic

Load the test plan, execute the command item by item

Drive the communication and data comparison module

# Command_Line.yml

Define various testable commands, expected responses and conditional verification

# Test_Case.yml / Test_Plan_List.yml

Define test combinations, such as Smoke Test, Regression Test, etc.

List of command steps for each test plan

# UART_communication.py

Serial UART transmission and reception of packets

Encapsulate send/receive basic operations

# Serial_Port_Monitoring.py

Background continuous monitoring of UART receiving data

Support for asynchronous events and delayed responses

# Conditional.py

Verify the response data (format, comparison, range) according to the command setting conditions

# Statistic.py

Record test steps and statistical results

Extensible output report format (CSV / TXT)
