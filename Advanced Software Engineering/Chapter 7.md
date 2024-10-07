### Design and Implementation

Oct 5, 2024

Outlines
- Object-oriented design using UML
- Design patterns
- Implementation issues
- Open source development

###### Design and Implementation

- The stage in the software engineering process at which an executable software system is developed.
- Commercial-off-the-shelf systems (COTS)


###### Process Stages

- Common activities in these processes:
	- Define the context and modes.
	- Design the system architecture.
	- Identify the principal system objects.
	- Develop design models.
	- Specify object interfaces.


A *system context model* is a structural model that demonstrates the other systems in the environment.

An *interaction model* is a dynamic model that shows how the system interact with its environment as it is used.

After understanding the interaction between the system and its environment, you use this information for designing the system architecture.

You identify the major components that make up the system and their interactions. Then you organize the components using *architectural patterns*

###### Object class identification and Approaches

- Difficult part of object-oriented design
- It is an iterative process
- Grammatical approach
- Behavioral approach
- Scenario-based analysis

###### Design Models

- Design models show the objects and object classes and relationships between entities.
- *Static models* describe the structure of the system.
- *Dynamic models* describe the interactions between objects.

###### Model 1: Subsystem Model

- Shows how the design is organized into logically related groups of objects

###### Model 2: Sequence Model

- Shows the sequence of object interactions that take place

###### Model 3: State Diagram Model

- Shows how objects responds to different events and the state transitions triggered by these events.
- Useful for high-level models of a system or an object's run-time behavior.

Key points

- Software design and implementation are inter-leaved activities.
- Process of object-oriented design include activities to design the system architecture, identifying objects in the system, describe the design using different object models.
- Static models: class models, generalization model, association model
- Dynamic models: sequence model, state diagram model

---

###### Design Patterns

- Design pattern is a way of reusing abstract knowledge about a problem and its solution.
- A pattern is a description of the problem and the essence of its solution.

###### Pattern Elements

- Name
- Problem description
- Solution description
- Consequences


###### Design Patterns

- Observer Pattern
- Façade Pattern
- Iterator Pattern
- Decorator Pattern

###### Implementation Issues

- Reuse
- Configuration Management
- Host-Target Development

###### Reuse Levels

- Abstraction level
- The object level
- The component level
- The system level

###### Configuration Management Activities

- Version management
- System integration
- Problem tracking

###### Integrated Development Environment

- A set of software tools that supports different aspects of software development.

###### Open Source Development

- An approach to software development in which the source code of a software system is published and volunteers are invited to participate in the development process.

###### License Models

- GNU General Public License (GPL)
- GNU Lesser General Public License (LGPL)
- Berkley Standard Distribution (BSD)

Key points

- When developing software, consider the possibility of reusing existing software.
- Config management is the process of managing changes to an evolving software system.
- Most software development is host-target development.