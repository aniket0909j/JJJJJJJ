# practical1
Great! 👍 You’ve listed **20 important Python programs** related to searching, sorting, linked lists, stacks, queues, and string reversal.
Since it’s a big set, I’ll give you **clear and working Python programs** for each question in **simple style with functions and classes** wherever needed.

---

## **1. Linear Search using Function**

```python
def linear_search(arr, x):
    for i in range(len(arr)):
        if arr[i] == x:
            return i  # return index
    return -1

arr = list(map(int, input("Enter elements of array: ").split()))
x = int(input("Enter element to search: "))

pos = linear_search(arr, x)
if pos != -1:
    print(f"Element found at position {pos}")
else:
    print("Element not found")
```

---

## **2. Binary Search using Function**

```python
def binary_search(arr, x):
    low, high = 0, len(arr)-1
    while low <= high:
        mid = (low+high)//2
        if arr[mid] == x:
            return mid
        elif arr[mid] < x:
            low = mid + 1
        else:
            high = mid - 1
    return -1

arr = sorted(list(map(int, input("Enter elements: ").split())))
x = int(input("Enter element to search: "))

pos = binary_search(arr, x)
if pos != -1:
    print(f"Element found at position {pos}")
else:
    print("Element not found")
```

---

## **3. Bubble Sort**

```python
def bubble_sort(arr):
    n = len(arr)
    for i in range(n-1):
        for j in range(n-i-1):
            if arr[j] > arr[j+1]:
                arr[j], arr[j+1] = arr[j+1], arr[j]
    return arr

arr = list(map(int, input("Enter elements: ").split()))
print("Original List:", arr)
print("Sorted List:", bubble_sort(arr))
```

---

## **4. Insertion Sort**

```python
def insertion_sort(arr):
    for i in range(1, len(arr)):
        key = arr[i]
        j = i-1
        while j >= 0 and key < arr[j]:
            arr[j+1] = arr[j]
            j -= 1
        arr[j+1] = key
    return arr

arr = list(map(int, input("Enter elements: ").split()))
print("Original List:", arr)
print("Sorted List:", insertion_sort(arr))
```

---

## **5. Selection Sort**

```python
def selection_sort(arr):
    n = len(arr)
    for i in range(n):
        min_idx = i
        for j in range(i+1, n):
            if arr[j] < arr[min_idx]:
                min_idx = j
        arr[i], arr[min_idx] = arr[min_idx], arr[i]
    return arr

arr = list(map(int, input("Enter elements: ").split()))
print("Original List:", arr)
print("Sorted List:", selection_sort(arr))
```

---

## **6. Merge Sort**

```python
def merge_sort(arr):
    if len(arr) > 1:
        mid = len(arr)//2
        L = arr[:mid]
        R = arr[mid:]

        merge_sort(L)
        merge_sort(R)

        i = j = k = 0
        while i < len(L) and j < len(R):
            if L[i] < R[j]:
                arr[k] = L[i]
                i += 1
            else:
                arr[k] = R[j]
                j += 1
            k += 1

        while i < len(L):
            arr[k] = L[i]
            i += 1
            k += 1

        while j < len(R):
            arr[k] = R[j]
            j += 1
            k += 1
    return arr

arr = list(map(int, input("Enter elements: ").split()))
print("Sorted List:", merge_sort(arr))
```

---

## **7. Singly Linked List (Create, Insert, Display)**

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class SinglyLinkedList:
    def __init__(self):
        self.head = None
    
    def insert(self, data):
        new_node = Node(data)
        if self.head is None:
            self.head = new_node
        else:
            temp = self.head
            while temp.next:
                temp = temp.next
            temp.next = new_node
    
    def display(self):
        temp = self.head
        while temp:
            print(temp.data, end=" -> ")
            temp = temp.next
        print("None")

# Test
sll = SinglyLinkedList()
for i in [10, 20, 30]:
    sll.insert(i)
sll.display()
```

---

## **8. Singly Linked List (Create, Delete, Display)**

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class SinglyLinkedList:
    def __init__(self):
        self.head = None
    
    def insert(self, data):
        new_node = Node(data)
        if not self.head:
            self.head = new_node
        else:
            temp = self.head
            while temp.next:
                temp = temp.next
            temp.next = new_node
    
    def delete(self, key):
        temp = self.head
        if temp and temp.data == key:
            self.head = temp.next
            return
        prev = None
        while temp and temp.data != key:
            prev = temp
            temp = temp.next
        if temp:
            prev.next = temp.next
    
    def display(self):
        temp = self.head
        while temp:
            print(temp.data, end=" -> ")
            temp = temp.next
        print("None")

sll = SinglyLinkedList()
for i in [10, 20, 30]:
    sll.insert(i)
sll.display()
sll.delete(20)
sll.display()
```

---

👉 The remaining programs (**9 to 20**) are longer (Linked Lists, Circular LL, Doubly LL, Stack, Queue).
Perfect 👍 Thanks for confirming.
I’ll now continue with the **remaining programs (9–20)** step by step, in **simple Python with classes/functions**.

---

## **9. Singly Linked List (Create, Display, Reverse)**

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class SinglyLinkedList:
    def __init__(self):
        self.head = None
    
    def insert(self, data):
        new_node = Node(data)
        if not self.head:
            self.head = new_node
        else:
            temp = self.head
            while temp.next:
                temp = temp.next
            temp.next = new_node
    
    def display(self):
        temp = self.head
        while temp:
            print(temp.data, end=" -> ")
            temp = temp.next
        print("None")
    
    def reverse(self):
        prev, curr = None, self.head
        while curr:
            nxt = curr.next
            curr.next = prev
            prev = curr
            curr = nxt
        self.head = prev

sll = SinglyLinkedList()
for i in [10, 20, 30, 40]:
    sll.insert(i)
sll.display()
sll.reverse()
sll.display()
```

---

## **10. Singly Linked List (Create, Search, Display)**

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class SinglyLinkedList:
    def __init__(self):
        self.head = None
    
    def insert(self, data):
        new_node = Node(data)
        if not self.head:
            self.head = new_node
        else:
            temp = self.head
            while temp.next:
                temp = temp.next
            temp.next = new_node
    
    def search(self, key):
        temp = self.head
        pos = 0
        while temp:
            if temp.data == key:
                return pos
            temp = temp.next
            pos += 1
        return -1
    
    def display(self):
        temp = self.head
        while temp:
            print(temp.data, end=" -> ")
            temp = temp.next
        print("None")

sll = SinglyLinkedList()
for i in [5, 15, 25, 35]:
    sll.insert(i)
sll.display()
print("Found at position:", sll.search(25))
```

---

## **11. Doubly Linked List (Insert End, Reverse, Display)**

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.prev = None
        self.next = None

class DoublyLinkedList:
    def __init__(self):
        self.head = None
    
    def insert_end(self, data):
        new_node = Node(data)
        if not self.head:
            self.head = new_node
            return
        temp = self.head
        while temp.next:
            temp = temp.next
        temp.next = new_node
        new_node.prev = temp
    
    def display(self):
        temp = self.head
        while temp:
            print(temp.data, end=" <-> ")
            temp = temp.next
        print("None")
    
    def reverse(self):
        temp = self.head
        prev = None
        while temp:
            prev = temp
            temp = temp.next
        while prev:
            print(prev.data, end=" <-> ")
            prev = prev.prev
        print("None")

dll = DoublyLinkedList()
for i in [10, 20, 30]:
    dll.insert_end(i)
dll.display()
dll.reverse()
```

---

## **12. Doubly Linked List (Insert End, Delete Position, Display)**

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.prev = None
        self.next = None

class DoublyLinkedList:
    def __init__(self):
        self.head = None
    
    def insert_end(self, data):
        new_node = Node(data)
        if not self.head:
            self.head = new_node
            return
        temp = self.head
        while temp.next:
            temp = temp.next
        temp.next = new_node
        new_node.prev = temp
    
    def delete_pos(self, pos):
        temp = self.head
        count = 0
        while temp and count != pos:
            temp = temp.next
            count += 1
        if temp:
            if temp.prev:
                temp.prev.next = temp.next
            if temp.next:
                temp.next.prev = temp.prev
            if pos == 0:
                self.head = temp.next
    
    def display(self):
        temp = self.head
        while temp:
            print(temp.data, end=" <-> ")
            temp = temp.next
        print("None")

dll = DoublyLinkedList()
for i in [10, 20, 30, 40]:
    dll.insert_end(i)
dll.display()
dll.delete_pos(2)
dll.display()
```

---

## **13. Singly Circular Linked List (Insert End, Display)**

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class CircularLinkedList:
    def __init__(self):
        self.head = None
    
    def insert_end(self, data):
        new_node = Node(data)
        if not self.head:
            self.head = new_node
            new_node.next = self.head
        else:
            temp = self.head
            while temp.next != self.head:
                temp = temp.next
            temp.next = new_node
            new_node.next = self.head
    
    def display(self):
        if not self.head:
            return
        temp = self.head
        while True:
            print(temp.data, end=" -> ")
            temp = temp.next
            if temp == self.head:
                break
        print("(Back to head)")

cll = CircularLinkedList()
for i in [1, 2, 3]:
    cll.insert_end(i)
cll.display()
```

---

## **14. Doubly Circular Linked List (Insert End, Display)**

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None
        self.prev = None

class DoublyCircularLinkedList:
    def __init__(self):
        self.head = None
    
    def insert_end(self, data):
        new_node = Node(data)
        if not self.head:
            self.head = new_node
            self.head.next = self.head
            self.head.prev = self.head
        else:
            last = self.head.prev
            last.next = new_node
            new_node.prev = last
            new_node.next = self.head
            self.head.prev = new_node
    
    def display(self):
        if not self.head:
            return
        temp = self.head
        while True:
            print(temp.data, end=" <-> ")
            temp = temp.next
            if temp == self.head:
                break
        print("(Back to head)")

dcll = DoublyCircularLinkedList()
for i in [5, 10, 15]:
    dcll.insert_end(i)
dcll.display()
```

---

## **15. Stack using Fixed-Size List (Static)**

```python
class Stack:
    def __init__(self, size):
        self.stack = []
        self.size = size
    
    def push(self, item):
        if len(self.stack) == self.size:
            print("Stack Overflow")
        else:
            self.stack.append(item)
    
    def pop(self):
        if not self.stack:
            print("Stack Underflow")
        else:
            return self.stack.pop()
    
    def peek(self):
        if not self.stack:
            return None
        return self.stack[-1]
    
    def display(self):
        print(self.stack)

st = Stack(5)
st.push(10)
st.push(20)
st.display()
print("Popped:", st.pop())
st.display()
```

---

## **16. Stack using Linked List (Dynamic)**

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class Stack:
    def __init__(self):
        self.top = None
    
    def push(self, item):
        new_node = Node(item)
        new_node.next = self.top
        self.top = new_node
    
    def pop(self):
        if not self.top:
            print("Stack Underflow")
        else:
            data = self.top.data
            self.top = self.top.next
            return data
    
    def peek(self):
        if not self.top:
            return None
        return self.top.data
    
    def display(self):
        temp = self.top
        while temp:
            print(temp.data, end=" -> ")
            temp = temp.next
        print("None")

st = Stack()
st.push(10)
st.push(20)
st.display()
print("Popped:", st.pop())
st.display()
```

---

## **17. Queue using Array (Static)**

```python
class Queue:
    def __init__(self, size):
        self.queue = []
        self.size = size
    
    def enqueue(self, item):
        if len(self.queue) == self.size:
            print("Queue Overflow")
        else:
            self.queue.append(item)
    
    def dequeue(self):
        if not self.queue:
            print("Queue Underflow")
        else:
            return self.queue.pop(0)
    
    def display(self):
        print(self.queue)

q = Queue(5)
q.enqueue(10)
q.enqueue(20)
q.display()
print("Dequeued:", q.dequeue())
q.display()
```

---

## **18. Queue using Linked List (Dynamic)**

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class Queue:
    def __init__(self):
        self.front = self.rear = None
    
    def enqueue(self, item):
        new_node = Node(item)
        if not self.rear:
            self.front = self.rear = new_node
        else:
            self.rear.next = new_node
            self.rear = new_node
    
    def dequeue(self):
        if not self.front:
            print("Queue Underflow")
            return
        data = self.front.data
        self.front = self.front.next
        if not self.front:
            self.rear = None
        return data
    
    def display(self):
        temp = self.front
        while temp:
            print(temp.data, end=" -> ")
            temp = temp.next
        print("None")

q = Queue()
q.enqueue(10)
q.enqueue(20)
q.display()
print("Dequeued:", q.dequeue())
q.display()
```

---

## **19. Circular Queue (Static Implementation)**

```python
class CircularQueue:
    def __init__(self, size):
        self.size = size
        self.queue = [None]*size
        self.front = self.rear = -1
    
    def isEmpty(self):
        return self.front == -1
    
    def enqueue(self, item):
        if (self.rear+1) % self.size == self.front:
            print("Queue Overflow")
        elif self.front == -1:
            self.front = self.rear = 0
            self.queue[self.rear] = item
        else:
            self.rear = (self.rear+1) % self.size
            self.queue[self.rear] = item
    
    def dequeue(self):
        if self.isEmpty():
            print("Queue Underflow")
            return
        elif self.front == self.rear:
            data = self.queue[self.front]
            self.front = self.rear = -1
            return data
        else:
            data = self.queue[self.front]
            self.front = (self.front+1) % self.size
            return data
    
    def peek(self):
        if self.isEmpty():
            return None
        return self.queue[self.front]
    
    def display(self):
        if self.isEmpty():
            print("Queue is Empty")
            return
        i = self.front
        while True:
            print(self.queue[i], end=" ")
            if i == self.rear:
                break
            i = (i+1) % self.size
        print()

cq = CircularQueue(5)
cq.enqueue(10)
cq.enqueue(20)
cq.display()
print("Dequeued:", cq.dequeue())
cq.display()
```

---

## **20. Reverse String using Stack**

```python
def reverse_string(s):
    stack = []
    for ch in s:
        stack.append(ch)
    rev = ""
    while stack:
        rev += stack.pop()
    return rev

text = input("Enter a string: ")
print("Reversed String:", reverse_string(text))
```

---

✅ Now you have **all 20 programs solved with clean Python code**.
Do you also want me to prepare a **combined PDF/Word file** of all these programs (nicely formatted with headings) for your submission?

Do you want me to **continue and give all codes together in one message**, or should I **break them into smaller sets (like 9–12, 13–16, 17–20)** so it’s easier for you to copy and understand?
