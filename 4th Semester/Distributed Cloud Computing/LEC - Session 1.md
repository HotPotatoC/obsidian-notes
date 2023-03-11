# LEC - Session 1
Class: [[COMP6710001 - Distributed Cloud Computing]]
Session: 1
Topics: Introduction to Distributed System Models
Date: 2023-02-15
Lecturer: [[D6667 - SAID ACHMAD, S.Kom., M.Kom]]

## The objective

1. How cloud computing works?
2. How do we use it?

# What is a Distributed System?

A distributed system is a type of computer system in which multiple independent computers, often referred as nodes or processors, work together to provide a common set of servicess or solve a problem.

As an example, It has a few purposes such as decreasing load on a single server, parallel processing, fault tolerance and scalability.

# Distributed system models

Model: *"**a simplified representation of a system** or phenomenon, as in the sciences or economics, with any hypotheses required to describe the system or explain the phenomenon, often mathematically."*

## System Models

There are two distributed system models that is Architectural Model and The Fundamental Models

### Architectural model

This model defines the way in which the components of the system are placed and how they interact with one another and the way in which they are mapped onto the underlying network of computers.

It concerns with the placement of its parts and relationship among them or similiarly close to an ERD and usually called an Architecture/Infrastructure Diagram.

Examples:
- Client-server Model
- Peer-to-Peer model

Example diagrams:

AWS Architecture diagram
![[Pasted image 20230215140428.png]]

GCP
![[Pasted image 20230215140633.png]]

### Fundamental models

- **Interaction model**: handles communication between components and their timing and performance details.
- **Failure model**: provides faults specifications and defines reliable communication and correct processes.
- **Security model**: specifies possible threats and risks and defines the concept of secure channels.

# Software and hardware service layers in distributed systems

![[Pasted image 20230215141337.png]]