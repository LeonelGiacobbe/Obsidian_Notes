Link: https://leetcode.com/problems/linked-list-cycle/
Topics: [[Hash Tables]]
Keys to solve: 
- Use of two pointers. One iterates one node at a time, the other iterates two at a time.
- If at any moment the two pointers are equal, that means there is a loop (if there wasn't, the fast pointer would get further and further away from the slow pointer).
- Mind constraints: iterating while both pointers are not `nullptr`, and since fast iterates over two nodes at a time, `fast->next` also cannot be `nullptr`

Solution:

```c++

class Solution {

public:

    bool hasCycle(ListNode *head) {

        ListNode* slow {head};

        ListNode* fast {head};

  

        while (slow != nullptr && fast != nullptr && fast->next != nullptr){

            slow = slow->next;

            fast = fast->next->next;

  

            if (slow == fast){

                return true;

            }

        }

  

        return false;

    }

};


/**

 * Definition for singly-linked list.

 * struct ListNode {

 *     int val;

 *     ListNode *next;

 *     ListNode(int x) : val(x), next(NULL) {}

 * };

 */
```