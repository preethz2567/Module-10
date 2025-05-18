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

#  EX NO-03 Queue-Remove Two String Values from the Rear End in Python 🧵

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
