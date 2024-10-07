## Data Modeling using ER model

Overview of the chapter
- High-level conceptual data models for database design
- Entity Types, Entity Sets, Attributes and Keys
- Relationship Types, Relationship Sets, Roles and Structural Constraints
- Weak Entity Types
- ER Diagrams
- UML Class Diagrams

---

- Entity-Relationship (ER) model
	- A popular high-level conceptual data model
- ER diagrams
	- Diagrammatic notation associated with the ER model
- Unified Modeling Language (UML)
	- A popular object modeling methodology

Database Design Process Phases

- Requirements collection and analysis (phase 1)
	- Database designers interview prospective database user to understand and document data requirement
	- Functional requirements of the application
- Conceptual schema (phase 2)
	- Conceptual design
	- Description of data requirements
	- Detailed descriptions of entity types, relationships and constraints
- Logical design or data model mapping
	- Result in a database schema
- Physical design phase
	- Internal storage structures indexes and access paths

---

#### Entity Types, Entity Sets, Attributes and Keys

- ER model describes data as:
	- Entities
	- Relationships
	- Attributes

- Entity
	- An object that represent a fact in a real-world with independent existence
- Attributes
	- Properties that describe entity
	- Types
		- Composite vs. atomic attributes
		- Single-valued vs. multi-valued
		- Stored vs. derived attribute
		- NULL value
		- Complex attribute
- Entity type
	- Collection of entities that has a common attribute

#### Relationships Types, Relationship Set, Roles and Structural Constraints

- Relationship
	- When an attibute of one entity type associates with another entity type

Relationship Degree Type
- Binary, ternary
- Number of participating entity types

Recursive relationships
- An entity type can have more than one relationship type
- Must specify role name for that

Constraints on Binary Relationship Types
- Cardinality ratio for a binary relationship: maximum number of relationship instances that entity can have
- Participation constraint: total and partial types

Attributes of Relationships Types
- Attributes of 1:1 or 1:N relationship types
	- Can be converted to one entity type
	- For 1:N only converted on N-side of relationship
- M:N relationship types
	- Must be specified as relationship attributes

Weak Entity Types
- Identified by being related to specific entities from another entity type
- Do not have key attributes of their own
- Always total participation constraint

![[Chapter 7-1674686480163.jpeg|350]]
![[Chapter 7-1674686500682.jpeg|350]]

Initial Conceptual Design of COMPANY Database

![[Chapter 7-1674687316768.jpeg|600]]

1. Model concept first as an attribute
2. Refine the design into a relationship if attribute is an attribute references to another entity type
3. Specify structural constraints on relationships
4. Replaces cardinality ratios (1:1, 1:N, M:N) with (min, max) notation pairs

![[Chapter 7-1674691887616.jpeg|600]]


---

#### UML Class Diagrams

Entity in ER corresponds to an object in UML.

![[Chapter 7-1674687838570.jpeg|525]]

- Class
	- Top section: class name
	- Middle section: attributes
	- Bottom section: operations applied to objects
- Associations: One of the relationship types in UML
- Relationship instances: link
- Binary association
	- Represented as a line connecting participating classes
	- name is optional
- Link attribute
	- Placed in a box connected to the association's line by a *dashed line* line MANAGES box above
- Multiplicities: $min..max$
	- Asterisk indicates no maximum limit on participation
- Aggregation/Composition: One of the relationship types in UML
- Unidirectional (ONE WAY) and bidirectional (TWO WAY/DEFAULT) associations
- Weak entities are modeled using *qualified association*

**Degree** of a relationship type defined as a number of participating entity types.
- Binary relationship is a degree two
- Ternary relationship is a degree three

Ternary relationships must be represeted as a weak entity type; to represent it as a strong entity type, a surrogate or artificial key must be introduced.

