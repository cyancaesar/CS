## Databases and Database Users

Chapter Overview
- Introduction
- Characteristics of the Database Approach
- Actors on the Scene
- Workers behind the Scene
- Advantages of Using the DBMS Approach
- History of Database Applications
- When Not to Use a DBMS

---

Database Types
- Traditional DB applications: `store textual or numeric information`
- Multimedia DB: `store images and video streams`
- Geographic Information Systems (GIS): `store and analyze maps, weather data and satallite images`
- Data Warehouses and Online Analytical Processing (OLAP) systems: `extract and analyze useful business information from large db and it supports decision making`
- Real-time and active DB technology: `control industrial and manufacturing processes`

---
### Introduction

**Database**
- An organized collection of structured information or related data.
- It represents some aspects of real world. Which is called *Universe of Discourse* or *Miniworld*.

**Database Management System (DBMS)**
- A collection of inter-related data that contains programs to store and retrieve that data in an easy and effective manner.
- It enables users to create and maintain a database effeciently

**Defining a database**
- Specify the *data types*, *structures* and *constraints* of the data to be stored.

**Meta-data**
- Descriptive information of the database
- Stored by the DBMS in a form of a *database catalog* or *dictionary*

Manipulation operation on a database
- Query and Update
- Generate reports

**Sharing a database**
- Allow multiple users and programs to access the database simultaneously

**Application program**
- Accesses database by sending queries to DBMS

**Query**
- Causes some data to be retrieved

**Transaction**
- May cause some data to be retrieved and some data to be written into the database

**Types of protection**:
- System protection against hardware
- Security protection unauthorized access

**Maintainability of a database system**
- Easy for a system to be scaled as requirements change over time

**Phases of designing a database** (The core of the course)
- Requirements specification and analysis
- Conceptual design
- Logical design
- Physical design

---

### Characteristics of the Database Approach

Main characteristics
- Self-describing nature of the database system
- Data abstraction and insulation of data
- Multiple views of the data (Type of data abstraction)
- Multiuser transaction processing
- Database system contains complete definition of structure and constraints

Database Catalog
- DBMS
- Database users who need information about a given database structure

**Insulation** or **Data Abstraction**
- Program-data independence (Data Independence)
	- The seperation of metadata from the application programs that use the data
- Program-operation independence
	- Inteface includes operation name and data types of its arguments that can be invoked by external programs without worrying about implementation

**Data Abstraction**
- The characteristics that allows program-data independence and program-operation independence.

**Conceptual Representation** of data
- Provided by the DBMS to the users that does not include details how the data is stored or how operations are implemented.

**Data Model**
- A type of data abstraction used to provide conceptual representation.

**View**
- A subset of the database and contains **virtual data** derived from the database files but no explicitly stored

**Sharing of data and multiuser transaction processing**
- DBMS must provides *concurrency control software* to ensure that several users trying to update the same data do so in a controlled manner so that the result of the updates is correct. It includes the concept of transaction and its **ACID** properties.

**Transaction**
- Central to many database applications
- It has the four properties ACID
- Isolation property
	- Each transaction appears to execute in isolation from other transaction
- Atomicity property
	- Either all the database operations in a transaction are executed or not
- Consistency property
	- The database must be consistant before and after the transaction
- Durability property
	- Once a transaction occurs, the changed data persist even if a system fails

---

### Actors on the Scene