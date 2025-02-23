class Solution:
    def constructFromPrePost(self, preorder: List[int], postorder: List[int]) -> Optional[TreeNode]:
        # preorder = root, left, right
        # postorder = left, right, root

        def makeTree():            
            node = TreeNode(postorder.pop()) # take root from postorder, now is [left, right]

            if node.val != preorder[-1]: # post = [left, right], pre = [root, left, right]
                node.right = makeTree() # postorder node isn't right leaf, build right subtree

            if node.val != preorder[-1]: # post = [left], pre = [root, left]
                node.left = makeTree() # postorder node isn't left leaf, build left subtree

            preorder.pop() # post = [], pre = [root], root already used for node.val
            return node

        return makeTree() # makeTree returns root of tree
