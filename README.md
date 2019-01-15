# Insights Platform Custom Payload definiton
This document contains the guidelines to specify a custom node for the Insights Platform. Nodes are defined in JSON format specifying the ports of the connected sensor and structure of the data coming on each port.

## Structure
On the top level the node contains the following elements:
- [name](#name)
- [transmit](#transmit)
- [receive](#receive)

## name
The name of the node.
type: string

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
Type: integer
 
#### length
Implies the length of the hexadecimal value of the sensor data.
For example: a sensor value with the start index of 2 and the length of 5 will reach from the 2nd index of the payload to the 7th.
Type: integer
 
#### type
Implies the type of information the sensor is forwarding.
Can be one of the following:
 - integer
 - double
 - float
 - boolean
 - ascii
 - [numeric](#numeric)
Type: string
 
#### sensor
Name of the sensor.
Type: string
 
#### expiry
How many days before the data expires.
Type: integer
 
#### regex
Implies the regular expression of validity.
Type: string
 
#### min
Implies the minimum valid value of the data.
Type: number
 
#### max
Implies the maximum valid value of the data.
Type: number
 
#### divisor
This property implies the number the sensor data should be divided with.
For example a numeric type value of 101 with the divisor property of 10 means that the sensor measured 10.1. Only used with [numeric](#numeric) type.
Type: number

##### numeric
This type is used when the sensor data value is intended to be divided by a number. Using numeric type requires the use of the divisor property.
