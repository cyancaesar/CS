### Architectural Design

Oct 5, 2024


Outlines
- Architectural design decisions
- Architectural views
- Architectural patterns
- Application architectures

###### Terminology

Architectural design — the process of identifying the sub-systems making up a system and the framework for sub-system control and communication.

Software architecture — the output of this design process.

###### Architectural Design

- The early stage of the system design process.
- Represents the link between specification and design processes.
- Identifies major system components and their communications

###### Architectural Abstraction

- *Architecture in the small*
	- Concerned with the architecture of individual programs
	- How individual program is decomposed into components
- *Architecture in the large*
	- Concerned with the architecture of complex enterprise systems that include other systems.

###### Advantages of Explicit Architecture

- Stakeholder communication
- System analysis
- Large-scale reuse

###### Architectural Models

- A way to facilitate discussion about the system design
- A way of documenting an architecture that has been designed.

###### Architectural Design Decisions

- Is there a generic application architecture that be used?
- How will the system be distributed?
- What architectural styles are appropriate?
- What approach will be used to structure the system?
- How will the system be decomposed into modules?
- What control strategy should be used?

###### Reusing Architecture

- Systems in the same domain have similar architecture thus reflects domain concepts.

###### Architecture and System Characteristics

- Performance
- Security
- Safety
- Availability
- Maintainability

4 + 1 view model:
- Logical view
- Process view
- Development view
- Physical view
- Use cases

###### Architectural Patterns

- Stylized description of good design practice.
- Should include information about *when they are and when they are not useful*.
- Represented by *tabular and graphical descriptions*.
- Like MVC pattern.

###### Layered Architecture

- To model the *interfacing of sub-systems*.
- Organizes a system into a set of layers.
- Incremental development of sub-systems.

Key points
- Software architecture is a description of how a software system is organized and it is the output of architectural design.
- Decisions include type of application, the distribution of the system and the architectural styles to be used.

---

###### Repository Architecture

- Sub-systems must exchange data. Two ways to achieve that
	- Shared data
	- Per sub-system database

Repository architecture is useful when a large amount of data are to be shared.


###### Client-Server Architecture

- Distributed system model on how data and processing is distributed.
- Set of servers each provide specific service.
- Set of clients each call on these services.

###### Pipe and Filter Architecture

- Functional transformations process their inputs to produce outputs.
- Provide sequential transformations. which is batch sequential model.
- Not suitable for interactive systems.

###### Application Architectures

- Generic application architecture is an architecture for a type of software system that may be configured and adapted to create a system that meets specific requirements.

###### Application Types

- Data processing applications.
- Transaction processing applications.
- Event processing applications.
- Language processing applications.

###### Information Systems Architecture

- Generic architecture which is organized into a layers

Key points
- Models of application systems architecture help us understand and compare applications.
- Transaction processing systems are interactive systems.
- Language processing systems are used to translate texts from one language into another.