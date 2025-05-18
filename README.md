# PYTHON PROGRAMMING MODULE 10
## NAME : PREETHI D
## REGISTER NUMBER : 212224040250
# EX 01- Queue-Queue Values in Descending Order Using Python 

This Python program simulates a queue using a list, removes the first two elements (FIFO order), and displays the remaining values in descending order.

## Aim

To write a Python program to:
- Accept user inputs into a list (queue)
- Remove the first two elements (simulating dequeue)
- Display the remaining values in **descending order**

##  Algorithm

1. Create an empty list `q`.
2. Read an integer `n` to determine how many elements will be added.
3. Loop `n` times:
   - Read an input value.
   - Append it to the list `q`.
4. Remove the first element using `pop(0)`.
5. Remove the second element using `pop(0)` again.
6. Sort the list in descending order.
7. Print the updated list.

##  Program: 
```
q = []
n = int(input("Enter number of elements: "))
for i in range(n):
    val = int(input(f"Enter element {i+1}: "))
    q.append(val)

if len(q) >= 2:
    q.pop(0)
    q.pop(0)
elif len(q) == 1:
    q.pop(0)

q.sort(reverse=True)
print("Remaining elements in descending order:", q)
```
### Output:
![image](https://github.com/user-attachments/assets/85eae175-0766-4f55-90ae-63d7afc74eda)

## Result:
Therefore the given Python Program has been executed successfully and the output has been verified.

#  EX NO-02 Queue-Remove Two String Values from the Rear End in Python 🧵

This Python program demonstrates how to manage a list of strings and remove the last two elements (i.e., from the rear of the list).

##  Aim

To write a Python program to:
- Accept `n` string values from the user
- Remove the last two values (rear end of the list)
- Display the updated list

##  Algorithm

1. Create an empty list `q`.
2. Read an integer `n` from the user (number of strings).
3. Loop `n` times:
   - Read a string input.
   - Append it to the list `q`.
4. Remove the last element using `pop()`.
5. Remove the next last element using `pop()` again.
6. Display the updated list.

##  Program:
```
q = []
n = int(input("Enter number of strings: "))
for i in range(n):
    val = input(f"Enter string {i+1}: ")
    q.append(val)

if len(q) >= 2:
    q.pop()
    q.pop()
elif len(q) == 1:
    q.pop()

print("Updated list:", q)

```
### Output:
![image](https://github.com/user-attachments/assets/7ce9646f-e13c-4e63-9ba4-33d6d71267ba)

## Result:
Therefore the given Python Program has been executed successfully and the output has been verified.

#  EX 03-Stack Implementation Using `LifoQueue` (Max Size 7) 

This Python program demonstrates a stack implemented using the `LifoQueue` class from the `queue` module. It allows up to 7 elements, checks if the stack is full, and then prints the elements in reverse (LIFO) order.

##  Aim

To create a Python program that:
- Implements a stack using `LifoQueue` with a maximum size of 7
- Adds user-inputted values to the stack
- Checks whether the stack is full
- Prints the stack elements in reverse order (LIFO)

##  Algorithm

1. Import the `LifoQueue` class from the `queue` module.
2. Create a stack with a maximum size of 7.
3. Read the number of elements (`n`) to be added to the stack.
4. Loop `n` times:
   - Read a value from the user.
   - Use `put()` to push it onto the stack if it's not full.
5. Use `full()` to check if the stack is full and print the result.
6. Use `get()` repeatedly to pop and print elements in reverse order.

## Program
```
from queue import LifoQueue

stack = LifoQueue(maxsize=7)
n = int(input("Enter number of elements to push (max 7): "))

for i in range(n):
    if not stack.full():
        val = input(f"Enter value {i+1}: ")
        stack.put(val)
    else:
        print("Stack is full. Cannot push more elements.")
        break

print("Is the stack full?", stack.full())
print("Stack elements in LIFO order:")
while not stack.empty():
    print(stack.get())

```

##  Sample Input and Output
![image](https://github.com/user-attachments/assets/b5cc30c5-85ed-4be5-82b2-c4bcbb99c3f5)

## Result:
Therefore the given Python Program has been executed successfully and the output has been verified.

# EX 04- Stack-Stack Reversal Program 🔁

This Python program demonstrates how to reverse the values in a stack using basic stack operations like push and pop.

##  Aim

To write a Python program that reverses the values in a stack using standard stack operations.

##  Algorithm

1. Create an empty stack.
2. Read an integer `n` from the user (number of elements to push).
3. Loop `n` times:
   - Read an integer from the user.
   - Push it onto the stack.
4. Create an empty list called `reverse`.
5. While the stack is not empty:
   - Pop the top element.
   - Append it to `reverse`.
6. Print the reversed list.


### Program:
```
stack = []
n = int(input("Enter number of elements to push: "))

for i in range(n):
    val = int(input(f"Enter element {i+1}: "))
    stack.append(val)

reverse = []
while stack:
    reverse.append(stack.pop())

print("Reversed stack elements:", reverse)

```
##  Sample Input and Output
![image](https://github.com/user-attachments/assets/3f647449-dca8-4ca0-a4d6-3ef45fb0dd4c)

## Result
Therefore the given Python Program has been executed successfully and the output has been verified.

# EX 05- Types of Queue-Circular Queue in Python

This project demonstrates the implementation of a **Circular Queue** in Python. The queue accepts 3 user values, performs enqueue and dequeue operations, and displays the removed values.

---

##  Aim

To develop a Python program that implements a Circular Queue:
- Accepts 3 values from the user
- Removes the 3 values from the queue
- Displays the removed values

---

##  Algorithm

1. **Initialize** a circular queue of fixed size (e.g., 5).
2. **Define the following functions**:
   - `enqueue()`: Inserts an element into the queue.
   - `dequeue()`: Removes an element from the queue.
   - `display()`: Shows the queue contents.
3. Accept 3 values from the user using the `enqueue()` method.
4. Remove 3 values using the `dequeue()` method.
5. Print the removed values.

---

##  Program:
```
class CircularQueue:
    def __init__(self, size):
        self.size = size
        self.queue = [None] * size
        self.front = self.rear = -1

    def enqueue(self, value):
        if ((self.rear + 1) % self.size == self.front):
            print("Queue is full!")
        elif self.front == -1:  # Queue is empty
            self.front = self.rear = 0
            self.queue[self.rear] = value
        else:
            self.rear = (self.rear + 1) % self.size
            self.queue[self.rear] = value

    def dequeue(self):
        if self.front == -1:
            print("Queue is empty!")
            return None
        removed = self.queue[self.front]
        if self.front == self.rear:  # Only one element was present
            self.front = self.rear = -1
        else:
            self.front = (self.front + 1) % self.size
        return removed

# Create CircularQueue object with size 5
cq = CircularQueue(5)

# Accept 3 values from user and enqueue
for i in range(3):
    val = input(f"Enter value {i+1}: ")
    cq.enqueue(val)

# Dequeue 3 values and print them
print("\nRemoved values:")
for i in range(3):
    removed = cq.dequeue()
    if removed is not None:
        print(removed)

```

### Output:
![image](https://github.com/user-attachments/assets/dae6677e-8093-433d-bb25-fbffade1fbaa)

## Result:
Therefore the given Python Program has been executed successfully and the output has been verified.
