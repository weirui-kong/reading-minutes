# Database System Concepts 
Database Theory and Application, 2022 Spring.

W Kong,

Software Engineering 2002,

Xi'an Univercity of Science and Technology.

Textbook: ***Database System Concepts***

## Chapter 2 Introduction to the Relational Model

The relational model remains the primary data model for commercial data-processing applications because of its simplicity, which eases the job of the programmer, compared to earlier data models such as the network model or the hierarchical model.

### 2.1 Structure of Relational Databases

A relational database consists of a collection of **tables**, each of which is assigned a unique name.

In general, a row in a *table* represents a *relationship* among a set of values and a table is a collection of such *relationships*.

In mathematical terminology, a **tuple** is simply a sequence (or list) of values. A relationship between n values is represented mathematically by an **n-tuple** of values, that is, a tuple with n values, which corresponds to a row in a table.

Thus, in the relational model the term relation is used to refer to a table, while the term tuple is used to refer to a row. Similarly, the term **attribute** refers to a column of a table.

We use the term **relation instance** to refer to a specific instance of a relation.

For each attribute of a relation, there is a set of permitted values, called the **domain** of that attribute.