## The Relational Data Model and Relational Database Constraints

#### Relational Model Concepts

It represents data as a collection of relations

Relation is thought as a **table of values**
- Row
	- Represents a collection of related data values
	- Also represents a fact that corresponds to an entity
	- *Tuple*
- Table name and column name
	- Helps to interpret the values in each row
	- *Attribute*

Relation name: table name
Tuples: records
Attributes: columns

- Domain D
	- Set of atomic values
- Atomic
	- Value cannot be divided
- Data type specified for each domain
- Relation schema R
	- $R(A_1, A_2,...,A_n)$
- Attribute $A_i$
	- Name of a role played by domain D in a relation schema R
- Degree or Arity
	- Number of attributes in a relation schema
- Relation or relation state
	- Set of n-tuples $r={t_1, t_2, ..., t_m}$
- Mathematical relation of degree n
	- which is a subset of a cartesian product
- Cardinality
	- Total number of tuples in domain

**Characteristics of Relations**
- Ordering of tuples in a relation
	- Ordering is not mandatory
- Values and NULLs in tuples
	- Values in a tuple is atomic
	- Flat relational model: not support for composite and multivalued attributes
	- Composite attributes
		- Represented only by simple component attributes in basic relational model
	- Multivalued attributes
		- Represented by a seperate relations

Notations
- Relation schema R of degree n
	- Denoted by $R(A_1, A_2, ..., A_n)$
- Uppercase letters: relation names
- Lowercase letter: relation state
- Letters: tuples

**Relation Model Constraints**
- Constraints
	- Restrictions on the actual values in db state
- Schema-based constraints (explicit constraints)
	- Expressed in schemata of the data model
- Application-based (semantic constraints or business rules)
	- Expressed by application program

Domain Constraints
- Numeric data type
- Characters
- Booleans
- Fixed-length and variable length strings
- Date, time and timestamp
- Money

Key Constraints
- No two tuples can have the same combination of values for all their attributes
- Candidate key
	- Relation schema may have more than one key
- Primary key of the relation
	- Designated among candidate keys
	- Underline attribute
- Unique key

**Relational Databases and Relational Database Schemas**

- Relational database schema S
	- Set of relation schemas $S=\{R_1,R_2,...,R_m\}$
	- Set of integrity constraints *IC*
- Relational database state
	- Set of relation states $DB=\{r_1,r_2,...,r_m\}$
- Invalid state
	- Does not satisfies the IC
- Valid state
	- Satifies all the constraints that are defined in IC

Integrity, Referential Integrity and Foreign keys
- Entity integrity constraint
	- No primary key value can be NULL
- Referential integrity constraint
	- Specified between two relations
	- Consistency among tuples in two relations
- Foreign key rules
	- Attributes in FK have the same domain as the primary key attributes PK

Basic operations that changes the state of relations in the database:
- Insert
- Delete
- Update

Insert operation
- Provides a list of attribute values for a new tuple t that is to be inserted into a relation R

Delete operation
- Can violate only *referential integrity*

Update operation
- Necessary to specify a condition on attributes of relation

