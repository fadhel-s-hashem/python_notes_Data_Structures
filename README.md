# Python Data Structures for JavaScript Developers

A comprehensive study guide bridging JavaScript data types (Arrays and Objects) with Python's core data structures: **Lists**, **Dictionaries**, and **Tuples**.

---

## 📚 Section 1: Python Lists (Arrays)

Python **Lists** are ordered, mutable collections that accept duplicate elements and mixed data types. They are equivalent to JavaScript Arrays.

### 1. Creation & Length
```python
# Declaration
students = ["Ali", "Zainab", "Omar", "Sayed"]

# Length (Equivalent to JS array.length)
print(len(students))  # Output: 4
```

### 2. Indexing & Negative Slicing
Python supports negative indexing to count backward from the end.

```python
colors = ["red", "green", "blue", "yellow"]

print(colors[0])   # "red"
print(colors[-1])  # "yellow" (Last item)

# List Slicing [start:stop:step]
nums = [0, 1, 2, 3, 4, 5]
print(nums[1:4])   # [1, 2, 3] (Excludes index 4)
print(nums[::-1])  # [5, 4, 3, 2, 1, 0] (Reverses list)
```

### 3. Adding, Modifying, and Removing Items
```python
fruits = ["apple", "banana"]

# Append to end (JS .push)
fruits.append("cherry")

# Insert at specific index
fruits.insert(1, "mango")  # ['apple', 'mango', 'banana', 'cherry']

# Remove by value
fruits.remove("banana")

# Remove by index (JS .pop / .splice)
last_item = fruits.pop()    # Removes & returns last item
first_item = fruits.pop(0)   # Removes & returns item at index 0

# Clear entire list
fruits.clear()
```

---

## 📚 Section 2: Python Dictionaries (Objects / Hash Maps)

Python **Dictionaries** (`dict`) store data in `key: value` pairs. They are similar to JavaScript Objects or Maps.
* **Key Difference:** Python dictionary keys **must be quoted strings** (or immutable types) and are accessed using bracket notation `dict["key"]`, not dot notation (`dict.key`).

### 1. Creation & Key Access
```python
# Declaration
user = {
    "name": "Fadhel",
    "role": "Developer",
    "is_active": True
}

# Accessing Values
print(user["name"])  # Output: 'Fadhel'

# Safe Access with .get() (Prevents KeyError if key doesn't exist)
print(user.get("age"))          # Output: None
print(user.get("age", 25))      # Output: 25 (Fallback default)
```

### 2. Adding, Updating, and Deleting Entries
```python
student = {"name": "Ali", "score": 85}

# Add or Update key
student["score"] = 92           # Updates existing key
student["grade"] = "A"          # Adds new key

# Remove by key
del student["grade"]            # Deletes 'grade' key
score = student.pop("score")    # Deletes 'score' key and returns its value

# Merge dictionaries (Equivalent to JS Object.assign or spread {...obj})
student.update({"city": "Manama", "status": "Passed"})
```

### 3. Iterating Over Dictionaries
```python
person = {"name": "Omar", "age": 22, "city": "Barbar"}

# Loop through Keys
for key in person.keys():
    print(key)

# Loop through Values
for value in person.values():
    print(value)

# Loop through Key-Value Pairs (JS Object.entries)
for key, value in person.items():
    print(f"{key}: {value}")
```

---

## 📚 Section 3: Python Tuples (Immutable Lists)

A **Tuple** is an ordered, **immutable** collection enclosed in parentheses `()`. Once created, items inside a tuple **cannot** be added, changed, or removed.

### 1. Creation & Characteristics
```python
# Declaration
coordinates = (26.2285, 50.5860)  # Latitude, Longitude
single_item_tuple = ("Bahrain",)    # Note the trailing comma for single items

# Accessing Elements
print(coordinates[0])   # Output: 26.2285
print(coordinates[-1])  # Output: 50.5860
```

### 2. Tuple Unpacking
Extract tuple elements directly into variables (similar to Array Destructuring in JS).

```python
point = (10, 20, 30)

# Unpacking
x, y, z = point
print(x)  # 10
print(y)  # 20
print(z)  # 30
```

### 3. Why Use Tuples Instead of Lists?
* **Immutability:** Protects constant data from accidentally being overwritten or modified.
* **Performance:** Uses less memory and executes faster than lists.
* **Dictionary Keys:** Tuples can be used as keys in Python dictionaries because they are immutable (Lists cannot).

---

## ⚡ Quick Comparison Cheat Sheet for JS Developers

| Feature / Action | JavaScript Syntax | Python Equivalent |
| :--- | :--- | :--- |
| **List/Array Creation** | `const arr = [1, 2]` | `lst = [1, 2]` |
| **Object/Dict Creation** | `const obj = { a: 1 }` | `dct = {"a": 1}` |
| **Immutable Tuple** | *(No direct equivalent)* | `tpl = (1, 2)` |
| **Add to End** | `arr.push(x)` | `lst.append(x)` |
| **Check Key Exists** | `"key" in obj` | `"key" in dct` |
| **Check Value Exists** | `arr.includes(x)` | `x in lst` |
| **Length of Collection** | `collection.length` | `len(collection)` |
| **Get Dictionary Keys** | `Object.keys(obj)` | `list(dct.keys())` |
| **Get Dictionary Values** | `Object.values(obj)` | `list(dct.values())` |
| **Get Key-Value Pairs** | `Object.entries(obj)` | `list(dct.items())` |
