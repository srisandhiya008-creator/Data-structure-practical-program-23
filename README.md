class Node:
    def __init__(self, data):
        self.data = data
        self.left = None
        self.right = None

# Function to build Balanced BST
def build_balanced_bst(arr, start, end):
    if start > end:
        return None
    
    mid = (start + end) // 2
    root = Node(arr[mid])

    root.left = build_balanced_bst(arr, start, mid - 1)
    root.right = build_balanced_bst(arr, mid + 1, end)

    return root

# Inorder Traversal
def inorder(root):
    if root:
        inorder(root.left)
        print(root.data, end=" ")
        inorder(root.right)

# Driver code
arr = [10, 20, 30, 40, 50, 60, 70]

root = build_balanced_bst(arr, 0, len(arr)-1)

print("Inorder Traversal of Balanced BST:")
inorder(root)# Data-structure-practical-program-23
