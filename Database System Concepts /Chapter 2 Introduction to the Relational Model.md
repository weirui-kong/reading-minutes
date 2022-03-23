# Database System Concepts 
Database Theory and Application, 2022 Spring.

W Kong,

Software Engineering 2002,

Xi'an Univercity of Science and Technology.

Textbook: `Database System Concepts`

## Chapter 2 Introduction to the Relational Model

The relational model remains the primary data model for commercial data-processing applications because of its simplicity, which eases the job of the programmer, compared to earlier data models such as the network model or the hierarchical model.

### 2.1 Structure of Relational Databases

A relational database consists of a collection of `tables`, each of which is assigned a unique name.

In general, a row in a `table` represents a `relationship` among a set of values and a table is a collection of such `relationships`.

> A relationship, in the context of databases, is a situation that exists between two relational database tables when one table has a foreign key that references the primary key of the other table.

In mathematical terminology, a `tuple` is simply a sequence (or list) of values. A relationship between n values is represented mathematically by an `n-tuple` of values, that is, a tuple with n values, which corresponds to a row in a table.

Thus, in the relational model the term relation is used to refer to a table, while the term tuple is used to refer to a row. Similarly, the term `attribute` refers to a column of a table.

We use the term `relation instance` to refer to a specific instance of a relation.

For each attribute of a relation, there is a set of permitted values, called the `domain` of that attribute.

A domain is atomic if elements of the `domain` are considered to be indivisible units.

> For example, suppose the table instructor had an attribute phone number, which can store a set of phone numbers corresponding to the instructor. Then the domain of phone number would not be atomic, since an element of the domain is a set of phone numbers, and it has subparts, namely, the individual phone numbers in the set.

The `null value` is a special value that signifies that the value is unknown or does not
exist.

When you try to describe a schema of a relation:

|dept_name|building|budget|
|-|-|-|
|Biology|Watson|90000|
|Comp. Sci.|Taylor|100000|
*Figure: the department relation*

The schema is:
```
department(dept_name, building, budget)
```

### 2.3 Keys
A `superkey` is a set of one or more attributes that, taken collectively, allow us to identify **uniquely** a tuple in the relation.

A superkey may contain extraneous attributes. 

>For example, the combination of ID and name is a superkey for the relation instructor. If K is a superkey, then so is any superset of K. 

>即`superkey`的任何超集都是唯一辨识符

We are often interested in superkeys **for which no proper subset is a superkey**. Such minimal superkeys are called `candidate keys`.

>`superkey`可以有子集，我们更关心`superkey`最小子集作为唯一辨识符的情况，叫做`candidate keys`

We shall use the term `primary key` to denote a candidate key that is chosen by the database designer as the principal means of identifying tuples within a relation.

> A key (whether primary, candidate, or super) is a property of the entire relation, rather than of the individual tuples. Any two individual tuples in the relation are prohibited from having the same value on the key attributes at the same time. The designation of a key represents a constraint in the real-world enterprise being modeled. Thus, primary keys are also referred to as **primary key constraints**.

Difference between Primary and Candidate Key: 
|Primary Key |Candidate Key|
|-|-|
|Primary key is a ***minimal super key***. So there is one and ***only one primary key*** in a relation. |While in a relation there can be ***more than one candidate key***.|
|Any attribute of Primary key can not contain NULL value. |While in Candidate key any attribute can contain NULL value.|
| Primary key can be ***optional*** to specify any relation.| But without candidate key there can’t be specified any relation.|
|***Primary key specifies the important attribute for the relation.*** |***Candidate specifies the key which can qualify for primary key.***|
|Its confirmed that a primary key is a candidate key. |But Its not confirmed that a candidate key can be a primary key.|

*from [GeeksforGeeks](https://www.geeksforgeeks.org/difference-between-primary-and-candidate-key/)*

>简而言之，`primary key`是最小唯一标识符，有且只能有一个，不可能为空值。因为它是来确定每一个`tuple`的关键元素，比如学生学号；`candidate key`可以有多个，甚至有的`attribute`可以是空值，大多数情况可以用 student(class, name,gender) 确定一个学生（因为同班同名同姓的情况几乎很$$少），`candidate key`还可以扩充集合。

