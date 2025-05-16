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
Add Code Here
```
class CircularQueue:
    def __init__(self, size):
        self.queue = [None] * size
        self.size = size
        self.front = self.rear = -1

    def enqueue(self, value):
        if (self.rear + 1) % self.size == self.front:
            print("Queue is full!")
            return
        if self.front == -1:
            self.front = self.rear = 0
        else:
            self.rear = (self.rear + 1) % self.size
        self.queue[self.rear] = value
    def dequeue(self):
        if self.front == -1:
            print("Queue is empty!")
            return None
        removed = self.queue[self.front]
        if self.front == self.rear:
            self.front = self.rear = -1
        else:
            self.front = (self.front + 1) % self.size
        return removed
cq = CircularQueue(3)
print("Enter 3 values for the Circular Queue:")
for i in range(3):
    val = input(f"Enter value {i + 1}: ")
    cq.enqueue(val)
removed_values = []
for _ in range(3):
    removed = cq.dequeue()
    if removed is not None:
        removed_values.append(removed)
print("\nRemoved values from the Circular Queue:")
print(removed_values)
```
### Output:
![image](https://github.com/user-attachments/assets/c9b9d30a-5613-4604-94ab-11b5204a65c6)

## Result:
Thus the program has been executed successfully.
