---
~
---
	
 # Database entries:
 - Each column has a specified data type 
	 - Adding a tuple with a wrong data type will not throw an error but will cause unexpected behavior
 - Can specify if NULL values are allowed or not
### Queries 
- Table and row names are case sensitive
- Table name specified like `FROM table_name`

### Creating Table 
- Using keyword `CREATE TABLE`
- Specify:
	- Table name,
	- columns & their data types 
	- primary/ foreign keys and `null` acceptance
- Can create a copy table with `CREATE TABLE copytable AS SELECT column1, column2 FROM originaltable`
	- Empty table using original as template: `CREATE TABLE template AS SELECT * FROM original WHERE 0=1`
```SQL
CREATE TABLE table_name (

	column_name datatype NOT NULL,
	column_name datatype, // YES NULL by default
	column_name datatype,
	...
	PRIMARY KEY (column name),
	FOREIGN KEY (column name)
REFERENCES table_name(column_name)
)
```


### Viewing Data 
- Done through `SELECT` command
- Can view entire content of table using `*` or specific columns (mind the case sensitivity)
- DO NOT combine `*` and `column_name`
```SQL
SELECT * FROM Table // Displays everything in table
SELECT FirstName, LastName FROM Customer 
SELECT Total FROM Order
```
### Math 
- Able to select minimums and maximums with `MIN` and `MAX`
- `COUNT` returns amount of rows in the table
- `AVG` displays average price of unique elements in table 
- `SUM` displays sum of entries in column
```sql
SELECT MIN(Price) FROM Books
SELECT MAX(UnitsSold) FROM Books WHERE Genre="Fiction"
SELECT COUNT(ISBN)
SELECT SUM(UnitsSold)
```

### Specific Data 
- Using `WHERE` keyword
- Can combine with equality, `AND`, `OR`.
- To be safe, always use quotes when listing data values
- Can look for approximations with `%` -> `"Hello%"` could match to `"Hello World"`
	- Position matters. If `%` is at the end, then it will look for data that starts exactly like the query up to `%`, then has other values
- the `IN` selector allows you to create a list of values to compare the query against
	- Essentially a way of compounding `OR` selectors.
	- List of CSVs can be filled with a different query (as long as it selects only one column)
- `BETWEEN` allows you to establish a range of values to select from. 
	- Inclusive range 
	- List values in ascending order (`1 AND 2`, not `2 AND 1`)
- Symbol Meanings:
	- `_` Represents a single unknown character. `C_S` matches to `COS`, `CES`, etc.
	- `[]` matches to characters inside bracket. `C[au]t` matches to `Cut` and `Cat`
	- `^` used in brackets (see above). Excludes a character. `C[^au]t` matches to every character instead a and u.
	- `-` (not underscore) represents range of chars. `C[a-c]t` matches `Cat`, `Cbt`, `Cct`.

```SQL
SELECT * FROM Customer WHERE CustomerID = "0001"

SELECT * FROM Customer WHERE CustomerID > "0001" and LastName = "Starkey"

SELECT * FROM Customer WHERE CustomerID LIKE "000%" # returns all customer IDs that start with 000, like 0001, 00002, etc.

SELECT * FROM Books WHERE author IN ("name1", "name2")

	SELECT * FROM Books WHERE ISBN IN (SELECT ISBN FROM Cart WHERE UserID="1000")

SELECT ISBN FROM Books WHERE Price BETWEEN 10 AND 50

```

### View Unique Columns 
- Select row to only return unique values 

```SQL
SELECT DISTINCT CustomerID FROM Order
```

### View Ordered Data 
- By Alpha Numerical order 
- Defaults to ascending order but can be reversed with `DESC`
```SQL
SELECT * FROM Customer ORDER BY LastName, FirstName
```


### Inserting into Table 
- Done with keyword `INSERT`
	- `INSERT INTO TableName (DataNames) VALUES (valuesForData)`
```SQL
INSERT INTO Customer (CustomerID, Address) VALUES ('0003', '351 Avenue')
```

### Deleting from Table 
- Using keyword `DELETE`
- Permanent (only recoverable through backups)

### Delete Entire table 
```SQL
DROP TABLE customer 
TRUNCATE TABLE Customer
```

### Updating Data 
- Done with UPDATE and SET keywords
```SQL
UPDATE Customer SET FirstName='John', LastName='Doe' WHERE CustomerID='0001'

UPDATE Customer SET FirstName='jane'
```

### Aliasing
- Give columns an alias with a query 
- Only lasts for the duration of the query. Not permanent 
- Uses keyword `AS` 
- Can also be done on tables 
	- `tableAlias.columnName` to refer to a column 
		- Done to eliminate redundancy in column naming 
```SQL 
SELECT Quantity as number FROM Books 
SELECT ISBN AS Book, UserID AS person FROM Cart 
```


### Joins
- Inner
	- Returns all records that have matches in both tables 
- Left Outer Join 
	- Returns all values from left table and matching records from right table 
	- Grab only columns from right table that are in left table
- Right Outer Join 
	- Returns all values from right table and matching records from left table 
	- Grab only columns from left table that are in right table
- Full Outer Join
```SQL
SELECT * FROM Books INNER JOIN Cart ON Books.ISBN = Cart.ISBN
# Returns all books in books table that are present in any users shopping cart
```

### Unions 
- Returns all values two `SELECT` queries have in common 
	- As long as `SELECT` query statements have the same:
		- number of columns
		- ordering of columns 
		- data types 
```SQL
SELECT City, State FROM Students 
UNION 
SELECT City, State FROM Universities
```