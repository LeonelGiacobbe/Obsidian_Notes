>[!tip] Extremely fast for data retrieval (O(1)), so they are widely used in database indexing 
 


Built using [[Containers and Arrays]], but the indexing of key value pairs is related to the data itself, allowing us to calculate the index where said key would be located.


### Insertion 
- Pass data through [[Hash Functions]] and make a `kvp` `{result of hash func: data}`
- Sometimes, two different keys will produce the same index after applying a hashing function to them.
	- Possible solutions:
		- [[Open addressing]]
		- [[Closed addressing]]
	- Avoiding Collisions
	- Make Hash Table bigger than needed to reduce displacement of keys.
		- ![[Pasted image 20240901152818.png]]
- 

### Search
- Best case scenario: O(1)
- May need to do linear probing if that was implemented

### Delete 
- Similar to search with an added delete at the end
