Learning Objectives
What is a binary tree
What is the difference between a binary tree and * a Binary Search Tree
What is the possible gain in terms of time * complexity compared to linked lists
What are the depth, the height, the size of a * binary tree
What are the different traversal methods to go * through a binary tree
What is a complete, a full, a perfect, a balanced * binary tree
Project Tests ✔️
tests: Folder of test files for all tasks.
Helper File ���
binary_tree_print.c: C function that prints binary trees in a pretty way.
Header File ���
binary_trees.h: Header file containing definitions and prototypes for all types and functions written for the project.
Data Structures

struct binary_tree_s
{
    int n;
    struct binary_tree_s *parent;
    struct binary_tree_s *left;
    struct binary_tree_s *right;
};

typedef struct binary_tree_s binary_tree_t;
typedef struct binary_tree_s bst_t;
typedef struct binary_tree_s avl_t;
typedef struct binary_tree_s heap_t;
Function Prototypes

File	Prototype
binary_tree_print.c	void binary_tree_print(const binary_tree_t *tree)
0-binary_tree_node.c	binary_tree_t *binary_tree_node(binary_tree_t *parent, int value);
1-binary_tree_insert_left.c	binary_tree_t *binary_tree_insert_left(binary_tree_t *parent, int value);
2-binary_tree_insert_right.c	binary_tree_t *binary_tree_insert_right(binary_tree_t *parent, int value);
3-binary_tree_delete.c	void binary_tree_delete(binary_tree_t *tree);
4-binary_tree_is_leaf.c	int binary_tree_is_leaf(const binary_tree_t *node);
5-binary_tree_is_root.c	int binary_tree_is_root(const binary_tree_t *node);
6-binary_tree_preorder.c	void binary_tree_preorder(const binary_tree_t *tree, void (*func)(int));
7-binary_tree_inorder.c	void binary_tree_inorder(const binary_tree_t *tree, void (*func)(int));
8-binary_tree_postorder.c	void binary_tree_postorder(const binary_tree_t *tree, void (*func)(int));
9-binary_tree_height.c	size_t binary_tree_height(const binary_tree_t *tree);
10-binary_tree_depth.c	size_t binary_tree_depth(const binary_tree_t *tree);
11-binary_tree_size.c	size_t binary_tree_size(const binary_tree_t *tree);
12-binary_tree_leaves.c	size_t binary_tree_leaves(const binary_tree_t *tree);
13-binary_tree_nodes.c	size_t binary_tree_nodes(const binary_tree_t *tree);
14-binary_tree_balance.c	int binary_tree_balance(const binary_tree_t *tree);
15-binary_tree_is_full.c	int binary_tree_is_full(const binary_tree_t *tree);
16-binary_tree_is_perfect.c	int binary_tree_is_perfect(const binary_tree_t *tree);
17-binary_tree_sibling.c	binary_tree_t *binary_tree_sibling(binary_tree_t *node);
18-binary_tree_uncle.c	binary_tree_t *binary_tree_uncle(binary_tree_t *node);
Tasks ���
0. New node

0-binary_tree_node.c: C function that creates a binary tree node with a given parent and value.
Returns a pointer to the new node, or NULL on failure.
alex@/tmp/binary_trees$ cat 0-main.c 
#include <stdlib.h>
#include "binary_trees.h"

/**
* main - Entry point
*
* Return: Always 0 (Success)
*/
int main(void)
{
    binary_tree_t *root;

    root = binary_tree_node(NULL, 98);

    root->left = binary_tree_node(root, 12);
    root->left->left = binary_tree_node(root->left, 6);
    root->left->right = binary_tree_node(root->left, 16);

    root->right = binary_tree_node(root, 402);
    root->right->left = binary_tree_node(root->right, 256);
    root->right->right = binary_tree_node(root->right, 512);

    binary_tree_print(root);
    return (0);
}
alex@/tmp/binary_trees$ gcc -Wall -Wextra -Werror -pedantic binary_tree_print.c 0-main.c 0-binary_tree_node.c -o 0-node
alex@/tmp/binary_trees$ ./0-node
      .-------(098)-------.
  .--(012)--.         .--(402)--.
(006)     (016)     (256)     (512)
alex@/tmp/binary_trees$
1. Insert left

1-binary_tree_insert.c: C function that inserts a node as the left-child of another.
Returns a pointer to the new node, or NULL on failure.
If the given parent already contains a left node, the new node takes its place and the old left-child becomes the left-child of the new node.
2. Insert right

2-binary_tree_insert_right.c: C function that inserts a node as the right-child of another.
Returns a pointer to the new node, or NULL on failure.
If the given parent already contains a right node, the new node takes its place and the old right-child becomes the right-child of the new node.
3. Delete

3-binary_tree_delete.c: C function that deletes an entire binary tree.
4. Is leaf

4-binary_tree_is_leaf.c: C function that checks if a given node is a leaf.
Returns 1 if the node is a leaf, 0 otherwise.
5. Is root

5-binary_tree_is_root.c: C function that checks if a given node is a root.
Returns 1 if the node is a root, 0 otherwise.
6. Pre-order traversal

6-binary_tree_preorder.c: C function that traverses a tree using pre-order traversal.
7. In-order traversal

7-binary_tree_inorder.c: C function that traverses a tree using in-order traversal.
8. Post-order traversal

8-binary_tree_postorder.c: C function that traverses a tree using post-order traversal.
9. Height

9-binary_tree_height.c: C function that returns the height of a binary tree.
10. Depth

10-binary_tree_depth.c: C function that returns the depth of a given node in a binary tree.
11. Size

11-binary_tree_size.c: C function that returns the size of a binary tree.
12. Leaves

12-binary_tree_leaves.c: C function that returns the number of leaves in a binary tree.
13. Nodes

13-binary_tree_nodes.c: C function that returns the number of nodes in a binary tree with at least one child.
14. Balance factor

14-binary_tree_balance.c: C function that returns the balance factor of a binary tree.
15. Is full

15-binary_tree_is_full.c: C function that checks if a binary tree is full.
Returns 1 if a tree is full, 0 otherwise.
16. Is perfect

16-binary_tree_is_perfect.c: C function that checks if a binary tree is perfect.
Returns 1 if a tree is perfect, 0 otherwise.
17. Sibling

17-binary_tree_sibling.c: C function that returns a pointer to the sibling of a given node in a binary tree.
Returns NULL if no sibling is found.
18. Uncle

18-binary_tree_uncle.c: C function that returns a pointer to the uncle of a given node in a binary tree.
Returns NULL if no uncle is found.
