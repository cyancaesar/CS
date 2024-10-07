	Topic in this chapter
	- Context models
	- Interaction models
	- Structural models
	- Behavioral models
	- Model-driven engineering

---

System Modeling - the process of developing abstract models of a system.

System Perspectives
- External perspective
- Interaction perspective
- Structural perspective
- Behavioral perspective

UML Diagram Types:
- Activity diagram - shows activities involved in a process or in data processing
- Use case diagram - shows the interactions between the system and its environment
- Sequence diagram - shows interactions between actors and the system and between system component
- Class diagram - shows object classes in the system and the associations between these classes
- State diagram - shows how the system reacts to internal and external events


**CONTEXT MODELS**

- Shows what lies outside the system boundaries.
- Shows the system and its relationship with other systems

The Context of the MHC-PMS
![[Chapter 5-1686531554742.jpeg|450]]

Process models reveal how the system being developed is used in broader business processes - *activity diagram* may be used to describe it.
![[Chapter 5-1686531754163.jpeg|425]]

**INTERACTION MODELS**

- Modeling user interaction to identify user requirement
- Use case diagrams and sequence diagrams may be used for interaction

**STRUCTURAL MODELS**
- Displays the organization of a system in terms of the components that make up that system and their relationships
- Might be a *static models*, which show the structure of the system design
- Or *dynamic models*, which show the organization of the system when it is executing
- Class diagrams are used for that

**BEHAVIORAL MODELS**
- Models of the dynamic behavior of a system as it is executing. They show what happens.
- Stimuli
	- Data
	- Events

**DATA-DRIVEN MODELING**
- Systems that controlled by the data input to the system
- Shows sequence of actions involved in processing input data and generating an associated output

**EVENT-DRIVEN MODELING**
- Real-time systems are often event-driven, with minimal data processing
- Shows how the system responds to external or internal events
- Based that the system has a finite number of states

**STATE MACHINE MODELS**
- Models the behavior of the system in response to external or internal events

---

**MODEL-DRIVEN ENGINEERING**
- Model-driven engineering (MDE) is an approach to software development where models rather than programs are the principal outputs of the development process

**MODEL-DRIVEN ARCHITECTURE**
- Model-driven architecture (MDA) was the precursor of more general model-driven engineering

![[Chapter 5-1686536234158.jpeg|550]]