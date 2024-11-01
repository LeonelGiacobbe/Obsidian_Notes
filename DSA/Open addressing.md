
### Linear Probing
>[!caution] Extremely expensive to do. Need to find a new hash function and run all previous values through it again

 If a key value pair wants to be stored in an index that is already occupied, perform a linear search on the [[Containers and Arrays]] index until a free index is found.
		- If using this approach, linear probing will also be needed when retrieving values using a key. 

### Quadrating probing
>[!tip] `p(val,i) = (val mod TableSize + i^2) mod TableSize`
- Keep track of how many probing attempts we've done already 
- 