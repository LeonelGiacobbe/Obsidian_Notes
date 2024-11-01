---
Created: 2024-03-20T19:59
---

## Singly linked lists

- An implementation of a list where each node contains contains data and a pointer to the next node
- ==Head node:== the first node of a linked list
- ==Tail node:== the last node of a linked list

  

# Operations

`Append`: inserts a new node after the original list’s tail node

```C++
ListAppend(list, newNode) {
   if (list⇢head == null) { // List empty
      list⇢head = newNode
      list⇢tail = newNode
   }
   else{
      list⇢tail⇢next = newNode
      list⇢tail = newNode
   }
}
ListAppend(myList, node someVal); // Appends node someVal to tail of myList
```

Steps to append:

1. Create new node _temp_. Has data and its _next_ points to _nullptr_
2. Point tail’s next [[Pointers]] to the new node. `tail->next = temp;`
3. `tail = temp;` Set the tail node to temp;
4. Add one to size

---

`Prepend`:inserts a new node before the list’s head node.

```C++
ListPrepend(list, newNode) {
   if (list⇢head == null) { // list empty
      list⇢head = newNode
      list⇢tail = newNode
   }
   else {
      newNode⇢next = list⇢head
      list⇢head = newNode
   }
}


ListPrepend(myList, node someVal); // Prepends node someVal to tail of myList
```

Steps to prepend:

1. [[Pointers]]node
2. Assign _head_ to the new node (also assign _tail_ if the list was empty). `head = temp;`
3. Assign new node’s _next_ to the old _head_ node. `newNode-> next = list-> head;`
4. Increase size by 1

---

`Display`: display the linked list’s existing nodes

Pseudocode:

```C++
temp = head;
while temp is not nullptr
{
	display temp
	temp = temp -> next
}
```

---

`Insert`: inserts a new node after a given node.

```C++
ListInsertAfter(list, curNode, newNode) {
   if (list⇢head == null) { // List empty
      list⇢head = newNode
      list⇢tail = newNode
	   }
   else if (curNode == list⇢tail) { // Insert after tail
      list⇢tail⇢next = newNode
      list⇢tail = newNode
   }
   else {
      newNode⇢next = curNode⇢next
      curNode⇢next = newNode
   }
}

ListInsertAfter(myList, currNode, newNode);
```

`Remove`: operation removes the node after the specified list node.

```C++
ListRemoveNodeAfter(list, curNode) {
   // Special case, remove head
   if (curNode is null && list⇢head is not null) {
      sucNode = list⇢head⇢next
      list⇢head = sucNode

      if (sucNode is null) { // Removed last item
         list⇢tail = null
      }
   }
   else if (curNode⇢next is not null) {
      sucNode = curNode⇢next⇢next
      curNode⇢next = sucNode

      if (sucNode is null) { // Removed tail
         list⇢tail = curNode
      }
   }
}

ListRemoveNodeAfter(myList, currNode);
```

==Removing from list of size 1:==

1. Make [[Pointers]]to the node in the list
2. Point _head_ and _tail_ to nullptr
3. [[Pointers]] the node
4. Decrease size by 1

==Removing from head==

1. Set _head_ to `_head→next_`
2. [[Pointers]]previous _head_ node
3. Decrease size by 1

==Removing from tail (singly-linked list)==

Need to figure out what node is previous to the original list’s tail node (so `temp-> next == tail`)

1. After that, set _tail_ to the node we found
2. [[Pointers]]the original tail
3. Set _`temp→next`_ to nullptr

---

`search`: search algorithm returns the first node whose data matches that key, or returns null if a matching node was not found.

```C++
ListSearch(list, key) {
   curNode = list⇢head
   while (curNode is not null) {
      if (curNode⇢data == key) {
         return curNode
      }
      curNode = curNode⇢next
   }
   return null
}

ListSearch (list, key);
```

- `ListTraversal`: goes through all nodes in a list and applies an operation to them.

```C++
ListTraverse(list) {
   curNode = list⇢head // Start at head

   while (curNode is not null) { 
      Print curNode's data        
      curNode = curNode⇢next
   }
}
```

- `ReverseTraversal`: same as before but starting from the tail node

```C++
ListTraverseReverse(list) {
   curNode = list⇢tail // Start at tail

   while (curNode is not null) { 
      Print curNode's data        
      curNode = curNode⇢prev
   }
}
```

- `Sorting`: a linked list may use a dummy node, which contains no data, sits at the head node of the list and cannot be removed.
    - If using a dummy node and we want to remove the first item, we would do `ListRemoveAfter(list, list-> head)` and not `ListRemoveAfter(list, null)`
- Doubly linked list with dummy node:
    
    ```C++
    ListAppend(list, newNode) {
       list⇢tail⇢next = newNode
       newNode⇢prev = list⇢tail
       list⇢tail = newNode
    }
    
    
    ListPrepend(list, newNode) {
       firstNode = list⇢head⇢next
    
       // Set the next and prev pointers for newNode
       newNode⇢next = list⇢head⇢next
       newNode⇢prev = list⇢head
    
       // Set the dummy node's next pointer
       list⇢head⇢next = newNode
    
       // Set prev on former first node
       if (firstNode is not null) {
          firstNode⇢prev = newNode
       }
    }
    
    
    ListInsertAfter(list, curNode, newNode) {
       if (curNode == list⇢tail) { // Insert after tail
          list⇢tail⇢next = newNode
          newNode⇢prev = list⇢tail
          list⇢tail = newNode
       }
       else {
          sucNode = curNode⇢next
          newNode⇢next = sucNode
          newNode⇢prev = curNode
          curNode⇢next = newNode
          sucNode⇢prev = newNode
       }
    }
    
    
    ListRemove(list, curNode) {
       if (curNode == list⇢head) {
          // Dummy node cannot be removed
          return
       }
    
       sucNode = curNode⇢next 
       predNode = curNode⇢prev 
      
       if (sucNode is not null) {
          sucNode⇢prev = predNode   
       }
      
       // Predecessor node is always non-null
       predNode⇢next = sucNode
      
       if (curNode == list⇢tail) { // Removed tail
          list⇢tail = predNode
       }
    }
    ```
    
    - Doubly linked list with dummy nodes (removes conditionals and simplifies code)
    
    ```C++
    ListAppend(list, newNode) {
       newNode⇢prev = list⇢tail⇢prev
       newNode⇢next = list⇢tail
       list⇢tail⇢prev⇢next = newNode
       list⇢tail⇢prev = newNode
    }
    
    ListPrepend(list, newNode) {
       firstNode = list⇢head⇢next
       newNode⇢next = list⇢head⇢next
       newNode⇢prev = list⇢head
       list⇢head⇢next = newNode
       firstNode⇢prev = newNode
    }
    ```