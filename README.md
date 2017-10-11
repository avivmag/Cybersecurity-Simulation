# Cyber-Security-Simulation

This program simulates a battle over a computer network between computer worms which spreads through all available routes and a team of cyber veterans which swore to do their best againt this malicious insects.

A detailed description for how to play this game can be found in the assignment desciption attached.

The development of this simulation was done in pairs as part of an assignment in "Systems Programming" course at Ben-Gurion University in the begining of 2016.

## Getting Started
### Prerequisites

1. Kubuntu - tested only on kubuntu, probably can be ran on any other known gcc compatible operating systems.
	https://kubuntu.org/getkubuntu/
2. GNU make
	https://www.gnu.org/software/make/
3. g++ compiler
	via ```sudo apt-get install g++``` on ubuntu based os (kubuntu included).
4. boost library
	via ```sudo apt-get install libboost-all-dev``` on ubuntu based os (kubuntu included).
Note: those softwares are the ones I used to build and run the program, I am sure there are many well-known compilers to compile this c++ files for other types of operating systems.

There are three xml files out there for simulator configuration, I left a full working example for them in the repository - feel free to edit any of them for your needs on the given structure:
1. computer.xml: This xml will declare all the computers in our network and the type of their operating system.
The structure of every computer record is as followes:
<computer>
	<name>[computer name goes here]</name>
	<os>[operating system goes here]</os>
</computer>
2. network.xml: This xml will declare the connection between two computers (if there is one).
The structure of every wire record is as followes:
<wire>
	<pointA>[first computer name goes here]</pointA>
	<pointB>[second computer name goes here]</pointB>
</wire>
3. events.xml: This xml is a little more complicated then the ones above,
Its main focus is to form the chain of events in the simulations.
It holds three types of sub-configurations:
a. Hack event: this event signifies that a hacker hacked his/her way into the network and planted a worm on a computer.
The structure of every hack record is as followes:
<hack>
	<computer>[hacked computer name goes here]</computer>
	<wormName>[worm name goes here]</wormName>
	<wormDormancy>[worm dormant time goes here]</wormDormancy>
	<wormOs>[worm favorite os goes here]</wormOs>
</hack>
b. Clock-In event: this event signifies that an Admin clocked-in and is now starting his/her workday
<clock-in>
	<name>[admin name goes here]</name>
	<workTime>[admin work time goes here]</workTime>
	<restTime>[admin rest time goes here]</restTime>
	<efficiency>[admin efficient setting goes here]</efficiency>
</clock-in>
c. Termination event: This event signifies the end time of our simulation, once this event is read, the simulation will continue until the specified time unit listed in the termination event.
<termination>
	<time>[time unit to terminate at goes here]</time>
</termination>

### Installing

1. open terminal and navigate to the program directory
2. type `make` and press enter.
3. type `./bin/cyber` and press enter.
4. enjoy :D.

## Built With

* [GNU make](https://www.gnu.org/software/make/) - A framework used for simple code compilation.
* [gcc](https://gcc.gnu.org/) - The compiler itself.
* [boost library](http://www.boost.org/) - Used known already implemented data structures.

## Useful links

* The actual assignment: TBA.
