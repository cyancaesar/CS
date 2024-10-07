## Database System Concepts and Architecture

Chapter Overview
- Data models, schemas and instances
- Three-Schema Architecture and Data Independence
- Database Languages and Interfaces
- Database System Environment
- Centralized and Client-Server Architectures for DBMS
- Classification of Database Management Systems

---

### Data models, Schemas and Instances

**Data Abstraction**
- Referes to the suppression of details on how data is organized and storage mechanism and highlighting of the essential features for an improved understanding of data.

**Data model**
- Collection of concepts that describe the structure of a database.
	- Structure of a database means data types, relationships and constraints that apply to the data.
- Provides means to achieve data abstraction
- Basic operations such as retrievals and updates on the database provided by data model
- Dynamic aspect or behavior of a database application
	- Allows database designer to specify a set of valid user-defined operations such as COMPUTE_GPA . 

Categories of Data Models
- High-level or conceptual data model
	- Provide concepts that are close to the way many users percieve data
- Low-level or physical data model
	- Provide concepts that describes the detail how data is stored on the computer
- Representational/implementation data models
	- It resides between those two extremes
	- Hide many details of data storage on disk but can be implemented on a computer

Concepetual data model uses concept such as entity, attribute and relationships

- Entity
	- Represents a real-world object or concept
- Attribute
	- Represents some property of interest. Describes an entity
- Relationship
	- Represent an association among the connected entities
	- Entity-Relationship model: a popular high-level conceptual data model
- Relationship data model
	- Used most frequently in traditional commercial DBMSs
- Object data model
	- New in higher-level implementation data models (conceptual data models)
	- Closer to conceptual data models
- Physical data model
	- Describe how data is stored as files in the computer
	- Access path: Structure that makes the search for particular database records efficient; example: *Index*
	- Index: Allows direct access to data using an index

**Schemas, Instances and Database State**

- Database schema
	- Description of a database
	- Schema diagram: Displays selected aspects of schema
	- Schema construct: Each object/element in a schema
- Database State (snapshot)
	- Capture of the data in a database in a given time
- Database Definition State
	- Specify database shcema to the DBMS
- Initial State
	- Populated or loaded with an initial data
- Valid State
	- Satisfies the structure and constraints specified in the schema
- Schema evolution
	- Changes applied to schema as application requirements change

---

### Three-Schema Architecture and Data Independence

- Internal level
	- Describes physical storage structure of the database
- Conceptual level
	- Describes structure of the whole database
- External/View level
	- Describes part of the database for a specific user group to access it

**Data Independence**
- It defined as a capacity to change the schema at one level without having to change the next higher level schema
- Types: Logical & Physical

---

### DBMS Languages

- Data definition language (DDL)
	- Defines schemas
- Storage definition language (SDL)
	- Specifies the internal level/schema
- View definition language (VDL)
	- Specifies user views to a conceptual schema
- Data manipulation language (DML)
	- CRUD operations on database such as retrieval, insertion, deletion and modification
- Two main types of DML
	- High-level or nonprocedural DML
		- Used on its own to specify complex database operations concisely
		- Called *set-at-a-time* or *set-oriented*
	- Low-level or procedural DML
		- Must be embedded in a general-purpose programming language
		- Called *record-at-a-time*

### DBMS Interfaces

Easy interface of the for parametric users:
- Menu-based for web clients interface
- Forms-based interface
- Graphical user interface
- Natural language interfaces
- Interfaces for parametric users and DBAs

---

### The Database System Environment

DBMS component modules:
- Buffer management
- Stored data manager
- DDL compiler
- Interactive query inteface (high-level/nonprocedural DML)
	- Query compiler and query optimizer
- Precompiler
- Runtime database processor
- System catalog
- Concurrency control system
- Backup and recovery system

**Database System Utilities**
- Loading
- Backup
- Database storage reorganization
- Performance monitoring

Tools, application environments and communications facilites
- CASE Tools
- *Data dictionary* (data repository) system
	- Stores design decisions, usage standards, application program descriptions and user information
- Application development environments
- Communications software

---

### Centralized and Client-Server Architectures for DBMS

- Centralized DBMS (One-Tier)
	- All DBMS functionality, application program execution everything in a DBMS carried out on one machine; basicly like a *monolithic design*.

Client-Server Architectures (Two-Tier)

- Client
	- User machine that provides user interfave capabilities and local processing
- Server
	- Provides services to the client machine

Three-Tier and n-Tier Architectures for Web Applications

- Applilcation server or Web Server
	- Acts as a mediator layer between client and the database server
- N-Tier
	- Divide the layers between the user and the stored data into a finer components



### Classification of Database Management Systems

- Data Model
	- Relational
	- Object
	- Hierarchical and network
	- Native XML DBMS

