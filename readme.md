# 🔑 Hashing

Hashing is a technique used to **store, retrieve, and search data efficiently** by mapping keys to values using a hash function. It is widely used in databases, caching, cryptography, and data structures like hash tables.

## 📌 Table of Contents
- [Introduction](#introduction)
- [How Hashing Works](#how-hashing-works)
- [Types of Hashing](#types-of-hashing)
- [Collision Handling Techniques](#collision-handling-techniques)
- [Applications of Hashing](#applications-of-hashing)
- [Common Hashing Functions](#common-hashing-functions)
- [Advantages and Disadvantages](#advantages-and-disadvantages)
- [Resources for Learning](#resources-for-learning)
---

## 🚀 Introduction
Hashing is a process that converts an **input (key)** into a **fixed-size numerical value (hash)**. This hash value determines the index where data is stored in a hash table, enabling **O(1) average time complexity** for search, insert, and delete operations.

---

## 🔄 How Hashing Works
1. **Hash Function**: Computes a unique hash value for each input.
2. **Index Mapping**: The hash value determines the index in the data structure.
3. **Collision Handling**: If two keys generate the same hash, a technique is used to resolve conflicts.

### 🎯 Example:
```python
hash_function(key) = key % table_size
```
For a table of size 10:
```
Key = 25 → Hash = 25 % 10 = 5
Key = 42 → Hash = 42 % 10 = 2
```

---

## 🔹 Types of Hashing
### 📌 **1. Static Hashing**
- Fixed-size table.
- The mapping remains unchanged.
- Used in applications where data size is known.

### 📌 **2. Dynamic Hashing**
- Adjusts the table size dynamically.
- Useful for databases and distributed systems.
- Examples: Extendible Hashing, Consistent Hashing.

---

## 🔀 Collision Handling Techniques
When two different keys generate the same hash (collision), we handle it using:
1. **Chaining (Separate Chaining)** – Store collided keys in a linked list.
2. **Open Addressing** – Find another available slot using techniques like:
   - **Linear Probing** – Search the next available slot sequentially.
   - **Quadratic Probing** – Search at intervals of `i^2`.
   - **Double Hashing** – Use a second hash function.

---

## 🌟 Applications of Hashing
- **Data Structures**: Hash Tables, Hash Maps, Bloom Filters.
- **Databases**: Indexing, Caching, Query Optimization.
- **Cryptography**: Password hashing (SHA-256, MD5).
- **Networking**: Load balancing, IP Address hashing.
- **Compiler Design**: Symbol tables in programming languages.

---

## 🔢 Common Hashing Functions
- **Modulo Division** – `hash(key) = key % table_size`
- **Multiplication Method** – Uses a constant multiplier.
- **Universal Hashing** – Uses a randomly chosen hash function.
- **Cryptographic Hash Functions**:
  - MD5 (Message Digest Algorithm 5)
  - SHA (Secure Hash Algorithm)
  - HMAC (Hash-based Message Authentication Code)

---

## ✅ Advantages and Disadvantages

### ✔️ Advantages:
- **Fast Lookups**: O(1) average case complexity.
- **Efficient Storage**: Stores large datasets efficiently.
- **Flexible**: Supports dynamic resizing.

### ❌ Disadvantages:
- **Collisions**: Can slow down operations if not handled properly.
- **Space Complexity**: Wastes memory due to unused slots.
- **Not Order-Preserving**: Does not maintain order of elements.

---

## 📚 Resources for Learning
### 🎥 Video Tutorials
- **[Hashing Explained – GeeksforGeeks](https://www.geeksforgeeks.org/hashing-data-structure/)**
- **[NeetCode – Hashing Problems](https://www.youtube.com/@NeetCode)**
- **[MIT OpenCourseWare – Hash Tables](https://ocw.mit.edu/)**

### 📖 Books
- pdfs given

---

## 🎯 Practice Problems
- **[LeetCode Hashing Problems](https://leetcode.com/tag/hash-table/)**
- **[GeeksforGeeks Hashing Practice](https://www.geeksforgeeks.org/hashing-data-structure/)**
- **[Codeforces Hashing Challenges](https://codeforces.com/)**

---

## 🤝 Contributing
Contributions are welcome! If you want to add more problems or optimizations, follow these steps:

1. Fork the repository 🍴
2. Create a new branch 🌿
3. Make your changes and commit 📌
4. Open a pull request 🔃

---

Happy Coding! 🚀💻✨
