# Python Cheatsheet

---

## 1. Data Structures
- List: `[1,2,3]`, append/pop.
- Dict: `{'a':1}`, keys(), items().

---

## 2. Comprehensions
- List: `[x*2 for x in seq if x>0]`
- Dict: `{k:v for k,v in items}`

---

## 3. Functions
```python
def func(a, b=2):
    return a + b
```

---

## 4. Modules & Packages
- Install: `pip install package`
- Import: `import numpy as np`

---

## 5. File I/O
```python
with open('file.txt') as f:
    data = f.read()
```

---

## 6. Virtual Envs
- Create: `python -m venv env`
- Activate: `source env/bin/activate`

---
