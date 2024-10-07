### Relational Database Design by ER

Designing a relational database schema is based on a conceptual schema design.

Seven-step algorithm to convert from basic ER model constructs to relational database schema; additional steps for EER model.

1. Mapping a Regular/Strong Entity Type
2. Mapping a Weak Entity Type
3. Mapping of Binary $1:1$ Relationship Types
4. Mapping of Binary $1:N$ Relationship Types
5. Mapping of Binary $M:N$ Relationship Types
6. Mapping of Multivalued Attributes
7. Mapping of $\text{N-ary}$ Relationship Types

|       E-R Model       |     Relational Model     |
|:---------------------:|:------------------------:|
|      Entity Type      |     Entity relation      |
| $1:1$ or $1:N$ R-type |       Foreign key        |
|     $M:N$ R-type      |     Two foreign keys     |
| $\text{N-ary}$ R-type |     *n* foreign keys     |
|      Simple Attr      |        Attribute         |
|    Composite Attr     |    Set of simple attr    |
|   Multivalued Attr    | Relation and foreign key |
|       Value set       |          Domain          |
|       Key Attr        |       Primary key        |

**Mapping EER Model Constructs to Relations**

8. Options for mapping *Specialization* or *Generalization*


**Mapping of Categories (Union Types)**

9. Mapping of Union Types (Categories)
