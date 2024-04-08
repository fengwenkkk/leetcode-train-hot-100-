

# 链表和二叉树
# 目录


- [二叉树的遍历](##二叉树的遍历)
- [翻转二叉树](##翻转二叉树)
- [二叉树层序遍历](##二叉树层序遍历)
- [有序数组构造二叉树](#有序数组构造二叉树)






















## 二叉树的遍历


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


## 翻转二叉树


给你一棵二叉树的根节点 root ，翻转这棵二叉树，并返回其根节点。




## 二叉树层序遍历


思路:使用队列


1.将二叉树根节点放入队列，记录该层节点大小


2.依次弹出值，放入一维数组，终止条件为节点大小为0


3.一维数组放入二维数组


4.将左右节点放入队列，记录该层节点大小


5.继续2步骤




## 有序数组构造二叉树


思路：使用递归


单层递归逻辑：


输入：数组，数组左右下标


终止条件：下标左>右


1.根据左右数组下标取中值为节点


2.处理左区间


3.处理右区间


//构造二叉树的时候尽量不要重新定义左右区间数组，而是用下标来操作原数组。


//二分时使用 int mid = left + ((right - left) / 2);来防止越界
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjA2ODQ4OTMyNV19
-->