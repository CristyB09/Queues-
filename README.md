              Data Structures and Algorithms
              
    3# Queues
    
    A queue is another name for a waiting line
    • Used within operating systems and to simulate realworld events
    • Come into play whenever processes or events must wait
    • Entries organized first-in, first-out (chronologically)
    Queues
    • Sometimes more flexibility is needed:
    • A double-ended queue permits operations on both oldest and newest entries (known as a
    deque)
    • When the importance of an object depends on criteria other than its arrival time, you can
     assign it a priority (known as a priority queue)
    
    Queue Operations

    Like a stack the queue ADT organizes entries in the order in which they were added
    • The behaviour of a queue is also known as: FIFO (First In, First Out)
    Queue Operations
    • In the queue all additions are to the back of the queue (the entry at the
    back is the latest item added to the queue)
    • The item that was added earliest is at the front of the queue
    • The operation that adds an entry to the queue is traditionally called
    enqueue
    • The operation that removes an entry from the queue is traditionally
    called dequeue
    
    Like the stack, the queue also restricts access to its entries (can only look at or the earliest
    entry)
    • In addition to enqueue and dequeue, the operation to retrieve the top entry without
    removing it is called getFront
    Queue Operations
    • Typically you cannot search a queue for a specific entry
    • The only way to look at an entry not at the front of the queue is to repeatedly remove
    items from the stack until the desired item reaches the front

      Java Interface for the Queue ADT
      
      public interface QueueInterface<T> {
          public void enqueue(T newEntry);
          public T dequeue();
          public T getFront();
          public boolean isEmpty();
          public void clear();
       }
       Add new entry to back of the queue
       Remove entry from front of the queue
       Return entry from front of the queue
       Check for no entries in queue
       Remove all entries from the queue   

        Adding to Priority Queue
        
        Algorithm add(newEntry)
            // Add a new entry into a linked pQueue in its priority position
        create new node
        if queue is empty set front pointer to point to the new node // add to empty
        else if priority of node at front < priority of new node // add at front
                set newNode next pointer to front
                set front to newNode
             else set currentNode pointer to front // add after existing
                  while currentNode.getNext() is not null and
                        priority of currentNode.getNext() > priority of newNode
                        set currentNode to curentNode.getNext()
                  set newNode next pointer to currentNode next pointer
                  set currentNode next pointer to newNode
             end if
         end if

