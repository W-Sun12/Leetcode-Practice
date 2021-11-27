# 94 Binary Tree Inorder Traversal


要點
* By recursion
    * helper function 直接呼叫
        * 定義：輸入資料、輸出儲存物件(root,res)
        * 過程：先left, 再right
        * 存入：過程處理到盡頭, 存到輸出物件
            
    * helper叫完, 把result(res) 輸出return
* By iteration
    * stack裡要存Node(不是Node value,是Node)




recursive(簡單)
```python=
# Definition for a binary tree node.
# class TreeNode(object):
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution(object):
    def inorderTraversal(self, root):
        """
        :type root: TreeNode
        :rtype: List[int]
        
        """
        #####code start#########
        res = []                            #儲存物件
        if root == None:                    #有值
            return res
        def helper(root,res):
            if root.left:
                helper(root.left,res)
            res.append(root.val)
            if root.right:
                helper(root.right,res)
            #res.append(root.val)
            return res

        return helper(root, res)
```


iterative (稍難)
```python=
# Definition for a binary tree node.
# class TreeNode(object):
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
# iteratively       
class Solution(object):
    def inorderTraversal(self, root):
        """
        :type root: TreeNode
        :rtype: List[int]
        
        """
        #####code start#########
def inorderTraversal(self, root):
    res, stack = [], []
    while True:
        while root:                    #有東西
            stack.append(root)
            root = root.left
        if not stack:                  #if stack空了 = 走完
        #次序不可換到下面 不然node會pop empty stack 
            return res
        node = stack.pop()
        res.append(node.val)
        root = node.right
```