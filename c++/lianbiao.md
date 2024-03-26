# 链表

## 链表的遍历

代码
```
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode() : val(0), left(nullptr), right(nullptr) {}
 *     TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
 *     TreeNode(int x, TreeNode *left, TreeNode *right) : val(x), left(left), right(right) {}
 * };
 */


class Solution {
public:
    vector<int> preorderTraversal(TreeNode* root)
    {
        vector<int> res;        //存放结果
        inorder(root, res);     //递归
        return res;            //返回值
    }

    //递归函数
    void inorder(TreeNode* root, vector<int>& res) 
    {
        //结束条件没有节点了
        if (!root)
        {
            return;
        }
    
        res.push_back(root->val);//什么顺序遍历该行就在什么位置，这里是前序遍历
        inorder(root->left, res);//转节点
        inorder(root->right, res);
    }
};
```
