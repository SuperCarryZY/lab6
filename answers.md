# CMPS 6610 Lab 06
## Answers

**Name:**__________Yan Zhu__________
**Name:**__________Yongbo Chen__________


Place all written answers from `lab-06.md` here for easier grading.



- **1)**
  - **deleteMin Work**:
    - To delete the minimum element, we need to retrieve the minimum element in the list/sequence, which requires us to iterate every element from the list, which takes $O(n)$ times.
    - After find the minimum element, we need to remove it from the list. Although the remove operate can be done in constant time, in the worst case we may have to shift all element from the list after removing the element, which also takes $O(n)$ times.
    - Overall, the work of deleteMin takes $O(n) + O(n)$, which is $O(n)$.  
  - **deleteMin Span**:
    - Since the operations of finding the minimum element and remove it from the list should be done sequentially, so the minimum finding operation is sequential because we need to check each element.
    - Therefore, the span of deleteMin also takes as same as its work, which is $O(n)$.
  - **insert(x) Work**:
    - From the concept of Python list, inserting an element $x$ into the list refers to appending the element at the end of the list, which takes a constant time $O(1)$.
    - Therefore, the work of insert(x) takes $O(1)$. 
  - **insert(x) Span**:
    - The operation of inserting an element into the list is done sequentially, so the span of inert(x) also is $O(1)$.

- **2a)**
  - For a complete binary tree, the depth of the tree is defined as the number of edges on the longest path from the root to the leaf node. Therefore, for a complete binary tree with $n$ nodes, each level $k$ can hold up to $2^k$ nodes. Therefore, the depth of the tree is hold as $\log_{2} n$.
  - For the case of almost-complete binary tree, the concept of tree depth also applies because it fills all levels completely except the last level, which doesn't affect the calculation of the tree depth. Therefore, the depth of the associated almost-complete binary tree is similar to the complete binary tree, which is $\log_{2} n$. 

- **2b)**
  - In our case, we are going to implement the min-heap, so the minimum element in the heap will be the root of the heap, since the min-heap requires the value of the node is less than or equal to the values of the children.
  - For the maximum element, it will be located among the leaf nodes. However, we can't guarantee the exact position since it will not be higher than the values in the internal nodes, especially when we are using an unordered list as the input.

- **4)**
  - **reHeapUp**:
    - **Work**: 
      - In the worst case, the algorithm may need to move the leaf node all the way up to the root, which may requires $O(\log_{2} n)$ times since it's an almost-complete binary tree.
      - So the work of the `reHeapUp` is $O(\log_{2} n) \in O(\log n)$.
    - **Span**:
      - Since each swap operation is done sequentially according to the algorithm, so the span is same as the work, which is determined by the depth $O(\log n)$.
  - **reHeapDown**:
    - **Work**: 
      - Similar to the algorithm `reHeapUp`, in the worst case this algorithm still need to traverse from the root to the leaf.
      - Therefore, the total work of `reHeapDown` is determined by the maximum height of the tree, which is $O(\log n)$.
    - **Span**:
      - Similar to the algorithm `reHeapUp`, each operation is done sequentially according to the algorithm, so the span is determined by the depth as well, which is $O(\log n)$.

- **6)**
  - The algorithm `heapsort` can be divided into two steps: inserting all elements into the heap and then keep deleting the minimum element from the heap until the heap becomes empty.
  - Therefore, the work and span of `heapsort` is as followed:
  - **Work**:
    - According to the implemented insert operation, also appending the new element take constant time, it requires an additional operation involves the `reHeapUp` algorithm, which takes $O(\log n)$ as mentioned above. Therefore, each insert operation takes $O(\log n)$. Since there are $n$ elements in the heap, we need to insert $n$ elements into the heap, so the total work of inserting all elements into the heap takes $O(n\log n)$.
    - The next step of repeatedly deleting the minimum element involves the algorithm of `deleteMin`, which takes $O(\log n)$ as well because it requires the algorithm `reHeapDown`. Since we need to delete the minimum element until the heap empty, so we need to repeat $n$ times, so the total work of deleting minimum elements takes $O(n\log n)$.
    - Overall, the total work of `heapsort` takes $O(n\log n) + O(n\log n) \in O(n\log n)$.
  - **Span**:
    - From the algorithm, each operation, either insert or delete, is done sequentially, and each of the operation span actually refers to the highest depth of the tree. Therefore, the total span is dominated by the number of levels times two, so the total span is $O(\log n) + O(\log n) \in O(\log n)$.
