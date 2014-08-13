1. Reverse linked list (iterative and recursively.)
2. Find the loop/cycle in the linked list and remove the loop.
3. Perform zipping of linked list in-place.
input : <l0,l1,l2,l3,...,l(n-1)> 
output : <l0,l(n-1),l1,l(n-2),..,l(n/2-1),l(n/2)>
4. Perform even-odd merge of the linked list.
input : <l0,l1,l2,l3,l4,...,l(n-1)>
Output : <l0,l2,l4,...,l1,l3,l5,..>
5. Merge 2 sorted linked list.
6.Overlapping lists 
Given 2 LL share the same tail connecting with each other at arbitary node.
Find arbitary/first comman node W/O extra storage
Given a.LL W/O cycle.
      b.LL with cycle.
7. Check wheather linked list is palindrome or not.Assume linked list is mutable.
8. Find kth element from the last.
9. Delete kth element from the last.

10.print nodes a kth level


10. Given kth node delete (K-1)node from the linked list.
Find median from the sorted LL and sorted circular LL.Given input as address of any node.
circular ll : tail->next = head
11.return the copy of the posting list
Posting list  : list with 3 fields 
                (data,jump,next)
jump : points to any node in the LL.
next : points to next node.



Things to note in linked list.

Each allocated node is present in the heap with unique address.
Stack variables are copied by value there values remains the same 
till the lifetime of the program.
They remain unchanged untill the values inside the heap are intact

1.  pass by reference
2.  pass by value
3.  Local reference  (eg. remove_nth_node.cpp)

Basic Idea : 
    1. Use of derefernce operator (*) when update the value
        
    2. Use of (&) to locate the element in the HEAP.







