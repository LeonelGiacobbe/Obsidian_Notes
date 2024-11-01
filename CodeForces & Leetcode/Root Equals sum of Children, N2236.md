Link: https://leetcode.com/problems/root-equals-sum-of-children/
Topics: [[DSA/Trees|Trees]]

Keys to solve: [[C++/Recursion|Recursion]]

Solution:

```cpp

class Solution {

public:

    bool checkTree(TreeNode* root) {

        if(root->left->val + root->right->val == root->val){

            return true;

        }

  

        return false;

    }

};


/**

 * Definition for a binary tree node.

 * struct TreeNode {

 *     int val;

 *     TreeNode *left;

 *     TreeNode *right;

 *     TreeNode() : val(0), left(nullptr), right(nullptr) {}

 *     TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}

 *     TreeNode(int x, TreeNode *left, TreeNode *right) : val(x), left(left), right(right) {}

 * };

 */

```