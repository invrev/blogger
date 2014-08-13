##### Tree traversal
* Tree can be traversed level-wise,this is a BFS/Bredth First Search.
* Its time-complexity O(V) + O(E) as we traverse all vertices and edges 
* and storage complexity O(V) as we store all vertices.
* Tree traversal is important in case of 
1. In graph,Identifying the connected component/connectivity.
2. In social networks,wheather A is friend of X.
3. Union-find problem
4. Find out shortest path given all path have same cost.


The basic idea to implement level-order traversal is to use the queue.

1. BFS traversal with DFS/recursive
    
    Use preorder or reverse-preorder traversal  

2. BFS traversal iterative

3. BFS traversal with levels
    Tweak the BFS routine or massage existing data structure 
    to store the level information.

    `typedef struct NodeLevel {
        int level;
        TreeNode *node;
        NodeLevel (int alevel,TreeNode *anode) : level(alevel) ,node (anode) {}
    } NodeLevel;`
    
    
4. BFS traversal with levels (reverse)

5. Zig-zag order traversal
    
    1. Use of 2 stacks  (store_stack and traverse_stack)
    2. Remove the content from one stack. (traverse_stack)
    3. Put the content on the other stack (store_stack)
       Decide the direction whether right->left or left->right.
    4. Alternatively swap the stack.  
       and direction .



