# Software Testing

Testing is intended to show that a program does what it is intended to do and to discover program defects before it is put into use.

Testing is part of a more general verification and validation process, which includes static validation techniques.

##### Testing Goals

1. To demonstrate to the developer and the customer that the software meets its requirements **(Validation testing)**.
2. To discover situations in which the behavior of the software is incorrect  **(Defect testing)**.

##### Verification vs. Validation

- *Verification*: The software should conform to its specification.
	- "Are we building the product right?"
- *Validation*: The software should do what the user really requires.
	- "Are we building the right product?"

##### Inspections and Testing

- Software Inspections: Concerned with analysis of the static system **(Static verification)**.
- Software Testing: Concerned with exercising and observing product behavior **(Dynamic verification)**.

##### Advantages of Software Inspections

- Inspection is a static process, not concerned with interactions.
- Incomplete versions of a system can be inspected without additional costs.
- Inspection can consider broader quality attributes of a program.

---
##### Stages of Testing

- Development Testing
- Release Testing
- User Testing

##### Development Testing

Development testing includes all testing activities.
- Unit Testing
- Component Testing
- System Testing

Unit testing is the process of testing individual components in isolation.

##### Testing Strategies

- Partition testing
- Guideline-based testing

##### Component Testing

Software components are often composite components that are made up of several interacting objects.

Interface types:

- Parameter interfaces
- Shared memory interfaces
- Procedural interfaces
- Message passing interfaces

Interface errors:

- Interface misuse
- Interface misunderstanding
- Timing errors

##### System Testing

System testing involves integrating components to create a version of the system and then testing the integrated system.

The focus in system testing is testing the interactions between components.

##### Test-Driven Development (TDD)

- An approach to program development in which you inter-leave testing and code development.

Benefits of test-driven development

- Code coverage
- Regression testing
- Simplified debugging
- System documentation

Testing types:
- Regression testing
	- Testing the system to check that changes have not 'broken' previously working code.
- Release testing
	- The process of testing a particular release of a system that is intended for use outside of the development team.
	- Known as black-box testing process
- Performance testing
	- Involves planning a series of tests where the load is steadily increased until the system performance becomes unacceptable.
	- Stress testing: a form of performance testing
- User testing
	- The customers provide input and advice on system testing
	- Alpha, beta, and acceptance

