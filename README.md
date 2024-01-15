# FrequentlyContacted

## LRU (Least Recently Used) Cache

### Cache
- Stores data to speed up future requests
- May be a previous computation or redundant copy of the data

### LRU Cache
- Most recent element is brought to the top
- Element that exceeds the limit is dropped out

### Data Structures
- Doubly Linked List
- Binary Search Tree

### Time Complexity
- Searching element in BST - O(log n)
- Inserting new element in linked list - O(1)
- Deleting last element in linked list - O(1)

### Space Complexity
O(n)

### Applications
- WhatsApp Chat history
- Recently used apps on smartphone
- Notification Panel

## Logic for LRU Cache

The logic for the LRU cache is implemented using a combination of a doubly linked list and a binary search tree (BST).

### Doubly Linked List
The doubly linked list is used to maintain the order of the elements in the cache. When a new element is accessed or added, it is moved to the head of the list. When the cache exceeds its maximum length, the last element in the list (tail) is dropped out.

### Binary Search Tree
The binary search tree is used to store the elements of the cache along with their corresponding addresses in the doubly linked list. This allows for efficient searching and deletion of elements in the cache. The BST is sorted based on the names of the elements.

### Insertion
When a new element is added to the cache, it is first checked if it already exists in the BST. If it does not exist, it is inserted at the head of the doubly linked list and added to the BST. If the cache exceeds its maximum length, the last element in the list is deleted from both the list and the BST.

### Accessing Existing Element
When an existing element is accessed, its corresponding node in the doubly linked list is moved to the head of the list to indicate that it is the most recently used element.

### Deletion
When an element is deleted from the cache, it is removed from both the doubly linked list and the BST. If the element to be deleted is the last element in the list, it is simply removed. If the element has children in the BST, the element with the highest height in the left subtree or the element with the lowest height in the right subtree is selected as the replacement. The name and address of the replacement element are copied to the node to be deleted, and the replacement element is then deleted from the BST.

### Searching
Searching for an element in the cache is done by performing a binary search in the BST based on the name of the element. If the element is found, its corresponding node in the doubly linked list is returned.

### Example Usage
The code provided demonstrates the usage of the LRU cache logic for managing a chat history. The user can add new contacts, display the chat history, and exit the program.

Note: The code provided is written in C programming language.
