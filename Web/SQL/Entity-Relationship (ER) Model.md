The Entity-Relationship (ER) Model is a high-level conceptual data model used to define data elements and relationships for a specified system. It is often used in database design to visually represent data and their interconnections.

---

## Key Concepts

### 1. **Entity**

An entity is an object or thing in the real world with an independent existence. It can be a person, place, object, event, or concept.

- **Entity Set**: A collection of similar types of entities. E.g., Students, Courses.
    

### 2. **Attribute**

An attribute describes a property of an entity. For example, a Student entity might have attributes like StudentID, Name, and Birthdate.

### 3. **Relationship**

A relationship is an association among two or more entities. E.g., a Student _enrolls in_ a Course.

- **Relationship Set**: A set of relationships of the same type.
    

---

## Keys in ER Model

### 1. **Primary Key**

A primary key is an attribute (or a set of attributes) that uniquely identifies each entity in an entity set.

- Example: StudentID is the primary key in the Student entity set.
    

### 2. **Composite Key (Clave Compuesta)**

A composite key is a combination of two or more attributes that uniquely identify an entity or relationship.

- Example: In an Enrollment relationship between Student and Course, the combination of StudentID and CourseID can form a composite key.
    

### 3. **Foreign Key (Clave Foranea)**

A foreign key is an attribute in one entity that refers to the primary key of another entity.

- Example: CourseID in the Enrollment relationship is a foreign key that references the Course entity.
    

---

## Types of Relationships

### 1. **One-to-One (1:1)**

Each entity in Set A is related to at most one entity in Set B and vice versa.

- Example: A person has one passport, and each passport belongs to one person.
    

### 2. **One-to-Many (1****:N****)**

An entity in Set A can be related to many entities in Set B, but each entity in Set B is related to only one entity in Set A.

- Example: One department can have many employees, but each employee works in only one department.
    

### 3. **Many-to-Many (N****:N****)**

Entities in Set A can be related to many entities in Set B and vice versa.

- Example: Students enroll in many courses, and each course can have many students.
    

---

## Diagrammatic Representation

ER diagrams are used to visually represent the ER model. They include:

- Rectangles for entity sets
    
- Ellipses for attributes
    
- Diamonds for relationships
    
- Lines to connect attributes to entities and entities to relationships
    

---

