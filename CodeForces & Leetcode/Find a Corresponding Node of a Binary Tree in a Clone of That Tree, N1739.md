Link: https://leetcode.com/problems/find-a-corresponding-node-of-a-binary-tree-in-a-clone-of-that-tree/

Topics: [[DSA/Trees|Trees]]

Keys to solve: DFS
Solution:
```c++
/**

 * Definition for a binary tree node.

 * struct TreeNode {

 *     int val;

 *     TreeNode *left;

 *     TreeNode *right;

 *     TreeNode(int x) : val(x), left(NULL), right(NULL) {}

 * };

 */

  

class Solution {

public:

    TreeNode* getTargetCopy(TreeNode* original, TreeNode* cloned, TreeNode* target) {

        if (original == nullptr){

            return nullptr;

        }

  

        if(original == target){

            return cloned;

        }

  

        TreeNode* left = getTargetCopy(original->left, cloned->left, target);

        TreeNode* right = getTargetCopy(original->right, cloned->right, target);

  

        if (left != nullptr){

            return left;

        }

  

        if (right != nullptr){

            return right;

        }

  

        return nullptr;

    }

};
```