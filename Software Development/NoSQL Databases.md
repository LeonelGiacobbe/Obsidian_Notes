- Store data differently than [[Relational Databases]] (not tabular)\
- Used in Big Data and Web Apps
- Some of these databases do not support SQL commands
- No conflicts when using OOP
- No rigid structure for data 
- _MUST_ have access pattern
- ACID Transactions: Data can't always be updated immediately, which can lead to wrong information retrieval.
- Low latency access (great efficiency)

### Storing Data 
- Wide-column:
	- Most likely to have SQL commands 
	- Uses rows and columns
		- Not every entry in a column stores the same type of data 
		- Amount of entries in each row varies.
		- One entry in the row may specify what the values in the rest of the entries represent 
		- No basis to access data. Each DB uses its own unique way 
- Document:
	- Similar to XML and JSON
	- Each document is treated like a table in [[Relational Databases]] with a unique ID associated with it.
	- Use parser to retrieve data.
- Key-value:
	- Like dictionaries in Python or maps in C++
	- Each data field is associated with a unique key 
	- Each pair may have unique attributes
	- No basis to access data. Each DB uses its own unique way 
- Graph:
	- Not really useful 
	- Graph theory to access data (for benchmarking access to data)
	- 

### Pros and Cons 
paste screenshot from slides here
### Examples 
- MongoDB
- Azure Cosmos
- Couchbase