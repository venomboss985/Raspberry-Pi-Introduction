---
marp: true
theme: gaia
class: invert
paginate: true
style: |
  .columns {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 1rem;
  }
header: "*Python Introduction Pt. 1* :snake:"
---
<!-- _header: "" -->

# Introduction to Python :snake:

* Lists and Dictionaries
* File IO and Exceptions
* Modules and Libraries
* Object-Oriented Programming (OOP)

By: Hedron Hackerspace

![bg right w:600](https://quantumobile.com/static/0cddd58936ed9792f56f0da4b5c99b2d/5d2c5/1.png)
<!-- _footer: "Rev 1.0; Python ver. >=3.9.x" -->
---

# Lists, Dictionaries, Tuples, and Sets

* `list` - Ordered, mutable object that stores values
* `dict` - List of key-value pairs
* `tuple` - Ordered, immutable list of values
* `set` - Unordered, unchangeable, unindexed list of values (doesn't allow duplicate values)
* Ordered - Values are listed in a specific order and referred by index
* Mutable/Immutable - Something that can change/cannot change
* Unchangeable - Values cannot change after initialization
<!-- _footer: "Sets are not commonly used, so don't worry about those for now" -->
---

## Lists

`[]`

---

### Creating a `list` with Existing Values

```py
my_burrito = ["Flour tortilla", "Black beans", "Rice", "Hot sauce", "Cheese"]
print(my_burrito[0])
print(my_burrito[1])
>>> Flour tortilla
>>> Black beans
```

* Can be initialized with existing values
* Values in the list can be accessed by writing `list[index]`
  * Indexe values start at 0 and increment up by 1
  * Values can be added to, removed from, and changed in lists
* Lists can also be sorted or joined to other lists

---

### Accessing and Changing Values

...

---

### Adding and Removing Values

These functions can be used on any list object:

* `append(value: Any)` - Add a value to the end of the list
* `insert(index: int, value: Any)` - Adds a value at the indexed position
* `remove(value: Any)` - Removes the first occurrence of the value
* `pop(index: int)` - Removes a value at a specific index
