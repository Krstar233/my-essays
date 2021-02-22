---
title: 【题解】leetcode-968.监控二叉树
tags:
- leetcode
---
### 题目描述
给定一个二叉树，我们在树的节点上安装摄像头。

节点上的每个摄影头都可以监视其父对象、自身及其直接子对象。

计算监控树的所有节点所需的最小摄像头数量。

示例1：

![image](https://s1.ax1x.com/2020/10/08/0BK4Cd.png)

示例2：

![image](https://s1.ax1x.com/2020/10/08/0BKX5Q.png)

### 解题思路
本题的思路是递归+贪心。对于树中的每个节点，要判断其是否放置摄像头，可以先看它左右孩子的状态。

- 节点的状态：

    a. 没有被监测到

    b. 被检测到但是没有放置摄像头

    c. 放置了摄像头

我们采用贪心的思想，对于每个节点能不放摄像头就不放摄像头。而从左右孩子的状态，我们可以判断该节点是否放摄像头：

1. 左右孩子有没被监测到，则没办法，只能在该节点放置摄像头。
2. 左右孩子都被检监测了，但是都没有放置摄像头，则在该节点可以不放置摄像头，等着被其父节点监测。
3. 左右孩子中至少有一个放置了摄像头，那么该节点一定被监测到了，不用放置摄像头。

而如果一个节点是空节点，那么它应该被判断成状态b。因为其父节点没有必要为了监测空节点而放置摄像头，而如果空节点的状态为a的话，根据上述规则就必须在其父节点放置摄像头了。

如此，对于一颗树，只需对其后序遍历，然后递归地判断每颗节点是否应该放置摄像头，然后再返回其状态，就可以啦~


### 代码

```cpp
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode(int x) : val(x), left(NULL), right(NULL) {}
 * };
 */
class Solution {
public:
    int sum;
    // 0: 无覆盖
    // 1: 有覆盖
    // 2: 有摄像头
    int dfs(TreeNode* root){
        if (root == NULL)
            return 1;
        int left_top = dfs(root->left);
        int right_top = dfs(root->right);
        if (left_top == 0 || right_top == 0){
            sum++;
            return 2;
        }
        if (left_top == 2 || right_top == 2){
            return 1;
        }
        return 0;
    }
    int minCameraCover(TreeNode* root) {
        sum = 0;
        int top = dfs(root);
        if (top == 0)
            sum++;
        return sum;
    }
};
```