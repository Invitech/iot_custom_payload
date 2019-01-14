# Insights Platform Custom Payload definiton
This document contains the guidelines to specify a custom node for the Insights Platform. Nodes are defined in JSON format specifying the ports of the connected sensor and structure of the data coming on each port.

## Structure
On the top level the node contains the following elements:
- [name](#name)
- [transmit](#transmit)
- [receive](#receive)

## name
The name of the node.

## transmit
Contains the ports of the node. All nodes have detailed explanations of the data coming from them.
Required properties:
- [portNumber](#portNumber)
- [parts](#parts)

## receive
todo

### portNumber
The number of the port

### parts
These properties define how sensor data are organised to build a payload of hexadecimal data.
