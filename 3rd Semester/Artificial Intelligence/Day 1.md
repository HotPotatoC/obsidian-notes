# Day 1
Class: [[COMP6065001 - Artificial Intelligence]]
Session: 1 & 2
Topics: 
	- Introduction to Artificial Intelligence
	- Intelligent Agents
Date: 2022-09-29
Lecturer: [[D6416 - PUTI ANDAM SURI, S.Kom, M.TI]]

# Score distribution

![[Pasted image 20220929115432.png]]

# Assignment & AoL

Student will **create a proposal** for *"Program Kreativitas Mahasiswa - Riset Eksata"* or *"Program Kreativitas Mahasiswa - Karsa Cipta"*

### Focused Topics
- Healthcare
- Energy
- Food and Agriculture
- Transportation
- Humaniora, Education, Art and Culture
- Maritime
- Security

**Create groups of 5**

## Final Product

**PKM-RE**
Focus on improving methods or methodology in Artificial Intelligent
- Modelling
- Proposal with PKM-RE template

**PKM-KC**
Focus on creating a good prototype using Artificial Intelligent approach
- Prototype
- Proposal with PKM-KC template

## Example Product

https://simbelmawa.kemdikbud.go.id/portal/wp-content/uploads/2021/10/Pengumuman-PIMNAS-ke-34..pdf

# What is AI?

## Thinking Humanly

- The cognitive modelling
- Once we have a sufficiently **precise theory** of the mind, it becomes possible to **express the theory** as **a computer program**

## Thinking Rationally

The **"Laws of thought"** or **Logic**

Example:
1. He is a boy; All boys are handsome;
2. Therefore, he is handsome

## Acting Rationally

- **Rational Behavior**: doing the right thing
- **The right thing**: that which is expected to maximize goal achievement given the available information

## Rational Agent

- **An agent**: just something that acts
- **A rational agent**: one that acts as to **achieve the best (expected) outcome**

### The rational-agent approach has two advantages
- It is **more general** than the "laws of thought" approach
- it is **more amenable** to scientific development

# AI Applications

## Speech Recognition

- Virtual assistants
They help us to arrange meetings, check weather, do a phone call, etc.

#### Examples
- Siri (apple)
- Google
- Cortana

## Machine Translation

No more bringing dictionary when travelling

#### Examples
- Google Translate

## Robotics

#### EXAMPLES
- Robots sent to Fukushima nuclear tragedy to perform various tasks
- Hubo: a KAIST robot who wins the DARPA robot challenge

## Recommendation Systems

Helps to provide items / photos / various things based on our social activities and interests

#### Examples
- Instagram explore
- Netflix
- Youtube
- TikTok FYP
- E-Commerce product recommendations
- Spotify discover weekly

## Search Engines

 Web-based tool that enables users to locate information on the World Wide Web
 
#### Examples
- Google search
- Duckduckgo
- Bing
- Yahoo search

## Email

Spam/junk email detection

## Face Detection

Used to find and identify human faces in digital images

#### Examples
- Instagram filters
- Snapchat filters
- Snapcam

## Face Recognition

#### Examples
- China's facial recognition technology

## Games

#### Examples
- Chess IBM Deepblue, Stockfish
- Google AlphaGo
- OpenAI Dota 2

## Self-driving cars

#### EXAMPLES
- NuTonomy
- Waymo

# Foundations of AI

### Philosophy

Logic, methods of reasoning. Foundations of learning, language and rationality.

### Mathematics

- Logic
- Algorithms, computations, (un)decidability, (in)tracibility
- Probability

### Economics

Formal Theory of rational Decisions

### Neuroscience

Plastic physical substrate for mental activity

### Psychology

- Adaptation
- Phenomena of perception and motor control
- Experimental techniques (psychophysics, etc.)

### Computer Engineering

Building an efficient computer to build AI program

### Control Theory and Cybernetics

Simple optimal agent designs

### Linguistics

- Knowledge representation
- Grammar

# Agent

an **Agent** is anything that can be viewed as **perceiving its environment** through **sensors** and acting upon that environment through **actuators**.

![[Pasted image 20220929125205.png]]

### Example
![[Pasted image 20220929125305.png]]
A vacuum-cleaner world with just two locations
**Percept**: location and contents, i.e. [A, Dirty]
**Actions**: Left, Right, Suck, NoOp (No Operation)

Pseudocode:
```haskell
function REFLEX-VACUUM-AGENT([location, status]) returns an action
	if status = Dirty then return Suck
	else if location = A then return Right
	else if location = B then return Left
```

## Concept of Rationality

A rational agent must select an action that is expected **to maximize its performance measure**.

Task environments **PEAS**
- P (Performance)
- E (Environment)
- A (Actuators)
- S (Sensors)

## Agent Types

- **Simple** reflex agents
- **Modal**-based reflex agents
- **Goal**-based agents
- **Utility**-based agents

### Simple reflex agents
An action is done based on current state only. Ignore the sensors history

### Modal-based reflex agents
The sensors and actions history is used to model the world / environment. An Action is done based on the world model.

### Goal-based agents
An action is done based on the combined information from the world model and goal information.

### Utility-based agents
An action is done based on the agent happiness (utility). It is the agent's performance measure.
