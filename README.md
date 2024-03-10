# Assignment


1) Explain the relationship between the "Product" and "Product_Category" entities from the above diagram.

Answer:  In the diagram, the "Product" and "Product_Category" entities are connected through a relationship called "has many." This means that a "Product" can belong to multiple "Product_Category" entities, and a "Product_Category" can have multiple "Product" entities associated with it. This relationship is represented by the arrow pointing from "Product" to "Product_Category" and the arrow pointing from "Product_Category" to "Product." This type of relationship is commonly used in database design to establish a many-to-many connection between two entities.


2) How could you ensure that each product in the "Product" table has a valid category assigned to it?

To ensure that each product in the "Product" table has a valid category assigned to it, you can implement a foreign key constraint in the database design. A foreign key constraint is a rule that enforces referential integrity between two tables, ensuring that the values in the foreign key column of one table match the primary key values in another table.
In this case, you would create a foreign key column in the "Product" table that references the primary key column in the "Product_Category" table. This would ensure that each product is associated with a valid category, preventing any orphaned products without a category.
For example, you could create a foreign key column named "category_id" in the "Product" table, which references the primary key column "id" in the "Product_Category" table. This would enforce that each product has a valid category assigned to it, maintaining the integrity of the data in the database.


3) Create schema in any Database script or any ORM (Object Relational Mapping) ?

answer : 
CREATE TABLE Product (
 id INT PRIMARY KEY,
 name VARCHAR(255) NOT NULL,
 description TEXT,
 price DECIMAL(10, 2) NOT NULL,
 category_id INT NOT NULL,
 FOREIGN KEY (category_id) REFERENCES Product_Category(id)
);

CREATE TABLE Product_Category (
 id INT PRIMARY KEY,
 name VARCHAR(255) NOT NULL,
 description TEXT
);
