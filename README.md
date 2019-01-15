# Insights Platform Custom Payload definiton
This document contains the guidelines to specify a custom node for the Insights Platform. Nodes are defined in JSON format specifying the ports of the connected sensor and structure of the data coming on each port.

## Structure
On the top level the node contains the following elements:
- [name](#name)
- [transmit](#transmit)
- [receive](#receive)

## name
The name of the node.
type: String

## transmit
Contains the ports of the node along with detailed explanations of the data coming from them.
Required properties:
- [portNumber](#portNumber)
- [parts](#parts)

## receive
todo

### portNumber
The number of the port.
Type: integer

### parts
Sensors connected to a port are sending a payload made from the hexadecimal value of their data combined. The platform then parses the payload retriving the data. These properties define how sensor data are organised to build the payload.
Required properties:
 - [start](#start)
 - [length](#length)
 - [type](#type)
 - [sensor](#sensor)

Optional properties:
 - [expiry](#expiry)
 - [regex](#regex)
 - [min](#min)
 - [max](#max)
 - [divisor](#divisor)
 
#### start
Implies the index where the hexadecimal value of the sensor data starts in the payload.
 
#### length
Implies the length of the hexadecimal value of the sensor data.
For example: a sensor value with the start index of 2 and the length of 5 will reach from the 2nd index of the payload to the 7th.
 
#### type
todo
 
#### sensor
todo
 
#### expiry
todo
 
#### regex
todo
 
#### min
todo
 
#### max
todo
 
#### divisor
todo
