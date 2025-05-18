# 🔄 Types of Queue-Circular Queue in Python

This project demonstrates the implementation of a **Circular Queue** in Python. The queue accepts 3 user values, performs enqueue and dequeue operations, and displays the removed values.

---

## 🎯 Aim

To develop a Python program that implements a Circular Queue:
- Accepts 3 values from the user
- Removes the 3 values from the queue
- Displays the removed values

---

## 🧠 Algorithm

1. **Initialize** a circular queue of fixed size (e.g., 5).
2. **Define the following functions**:
   - `enqueue()`: Inserts an element into the queue.
   - `dequeue()`: Removes an element from the queue.
   - `display()`: Shows the queue contents.
3. Accept 3 values from the user using the `enqueue()` method.
4. Remove 3 values using the `dequeue()` method.
5. Print the removed values.

---

## 💻 Program:
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
