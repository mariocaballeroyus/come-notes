An iterator in [[Python]] is an object that allows you to iterate through a sequence of elements, one at a time. It remembers its position during iteration and produced items only when requested (lazy evaluation), making it memory efficient. 

The `StopIteration` is a special exception in Python that signals the end of an iteration. It's what tells a `for` loop that there are no more values left to get. 
## Built-in Iterators

- Files: `open("file.txt.")`
- Enumerate: `enumerate(sequence)`
- Zip: `zip(a, b)`
- Map / Filter

## Lists

A **list** is an ordered, mutable collection that can store elements of any type. Lists are ideal when you need to add, remove or reorder elements dynamically. 

```python
fruits = ["apple", "banana", "cherry"]
print(fruits[0])  # apple

fruits.append("orange")  # add element
fruits.remove("banana")  # remove element
fruits[1] = "grape"      # modify element

print(fruits)            # ["apple", "grape", "orange"]
```

## Tuples

A **tuple** is an ordered, immutable sequence. Once created, its elements cannot be modified, which makes tuples safer and faster for fixed data.

```python
point = (3, 4)
print(point[0])  # 3

# point[0] = 10  -> TypeError: `tuple` object does not support item assignment
```

Tuples are great for representing fixed collections of related data, and they can also be easily unpacked:

```python
person = ("Mario", 23, "Engineer)
name, age, job = person
```

## Sets

A set is an unordered, mutable collection of unique elements. It's mainly used for membership testing and mathematical set operations (union, intersection, difference).

```python
numbers = {1, 2, 3, 3}
print(numbers)  # {1, 2, 3}, duplicates removed

numbers.add(4)
numbers.remove(2)
print(numbers)  # {1, 3, 4}
```

Some common set operations include:

```python
a = {1, 2, 3}
b = {3, 4, 5}

print(a | b)  # Union → {1, 2, 3, 4, 5}
print(a & b)  # Intersection → {3}
print(a - b)  # Difference → {1, 2}
print(a ^ b)  # Symmetric difference → {1, 2, 4, 5}
```

## Dictionaries



## Generators

When you create a  list, tuple or set in Python, all elements are stored in memory at once. A **generator** is a special kind of iterator that produces a sequence of values lazily, meaning it remembers where it left off and continues from there. 

There are two ways to create a generator:

1. Using a **generator function** with `yield`:

```python
def count_to(n: int):
	count = 1
	while count <= n:
		yield count
		count += 1
		
gen = count_up_to(3)
print(next(gen))

for x in count_up_to(3):
	print(x)
```

2. Using a **generator expression**, just like comprehensions but with parenthesis:

```python
gen = (x**2 for x in range(5))    # lazy evaluation, more efficient!
comp = [x**2 for x in range (5)]  # precomputed, less efficient!
print(next(gen))
```

Generators can also use `return` to send a final result when the iteration ends. 

```python
def accumulate(n: int):
	total = 0
	for i in range(1, n+1):
		total += 1
		yield total
	return total  # final result
	
gen = accumulate(3)
try:
    while True:
        next(gen)
except StopIteration as e:
    print("Returned:", e.value)  # returned: 6
```

Besides yielding values out, generators can also **receive values in** using the `.send()` method:

```python
def greeter():
	name = yield "What's your name?"
	yield f"Hello, {name}!"
	
g = greeter()
print(next(g))          # output: "What`s your name?"
print(g.send("Mario"))  # output: "Hello, Diego!"
```

For generators, Python automatically raises the `StopIteration` exception when:

- The function's code reaches the end, or
- A a `return` statement is executed inside the generator, or
- The generator is resumed (via `next()` or `.send()`) after it has already completed.
## The `typing` library

The `typing` module provides tools to express **type hints** for functions, classes and variables. When working with **iterators** and **generators**, this helps make the flow of data more explicit. 

Python distinguishes between:

- **Iterables**, objects you can iterate over.
- **Iterators**, objects that yield elements one by one.

```python
from typing import Iterable, Iterator

def square_all(values: Iterable[int]) -> Iterator[int]:
	for v in values:
		yield v * v
```

Generator functions are iterators, but sometimes we want to be more specific about:

- what they `yield`, 
- what value they `return` when exhausted, 
- what they can `send()` in via `generator.send()`. 

For this, we use `Generator[yield_type, send_type, return_type]` from `typing`:

```python
from typing import Generator

def count(start: int = 0) -> Generator[int, int | None, str]:
	count = start
	while count < 5:
		new_value = yield count
		if new_value is not None:
			count = new_value
		else:
			count += 1
	return "Done counting!"
	

```