- Database that identifies data in relation to other data 
- Not as fast when accessing as [[NoSQL Databases]]
- Flexible queries
- Use this when having attribute restraints
- Emphasis on data integrity (handling query order)


- Many of these Databases use SQL
![[Pasted image 20240924110907.png]]

### Types of relations 
- Primary keys
	- Each tuple (row) has one column as its primary key 
	- Typically (not always) computer-generated integers. Unique to each tuple
- Foreign keys
	- Primary key of different relation on another table.
	- Reduces ambiguity in data. 
	- Not unique in table using them as foreign key (they _ARE_ when they are used as primary)
	- Reduces Redundancy
- Minor key types 
	- Natural keys
		- Used in external world (separate from database)
	- Alternate key
		- Present but not flagged in the table. Unique identifier but technically not a primary key (in MSU, primary key is 9-digit ID and netID is the alternate key. Both are unique).

### Relational operations 
- **Union**: combines tuples of two relations and removes duplicates
- **Intersection**: combines two tuples and only jeeps duplicates
- **Difference**: takes one relation and returns the items from it that are not present in another relation
- **Cartesian Product**: matches every tuple from one relation to another tuple from other relation. (every row in table A is matched to a row in table B)
- **Selection / restriction**: retrieves tuple from relation according to some Criteria. Limits how many rows we grab 
- **Projection**: retrieves specified attributes from tuple(s). Limits how many columns we grab
- **Join**: two relations are connected by their common attributes.
- **Relational** **Division**: Using tuples from one relation to partition a second relation

### Normalization
Structuring databases to reduce redundancy and improving data integrity.

### Programs
OracleDB, MySQL, PostgreSQL, SQLite, MariaDB, etc.