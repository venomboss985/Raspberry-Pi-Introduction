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
header: "*Python Introduction Pt. 2* :snake:"
---
<!-- _header: "" -->

# Introduction to Python :snake:

* Lists and Dictionaries
* File IO
* Modules
* Libraries
* And more...

By: Hedron Hackerspace

![bg right w:600](https://quantumobile.com/static/0cddd58936ed9792f56f0da4b5c99b2d/5d2c5/1.png)
<!-- _footer: "Rev 1.0; Python ver. >=3.9.x" -->
---

# Lists, Dictionaries, Tuples, and Sets

* `list` - Ordered, mutable, subscriptable object that stores values
* `dict` - Ordered, mutable list of key-value pairs
* `tuple` - Ordered, immutable list of values
* `set` - Unordered, immutable list of values (doesn't allow duplicates)

</hr>

* Ordered - Values are listed in a specific order
* Mutable/Immutable - Something that can change/cannot change
* Subscriptable - Object is indexed
<!-- <!-- _footer: "Sets are not commonly used, so don't worry about those for now" --> -->
---

## TLDR Version

* `list` - Group of values
* `dict` - List of key-value pairs
* `tuple` - List, but you can't change anything after its initialized
* `set` - Tuple, but it doesn't allow duplicate values

</hr>

* There is also a `range`, but its just a list of stepped numbers
  * Ex. `range(10)` is `[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]`
  * Ranges will be covered more later (useful in `for` loops)
<!-- _footer: "We will not be extensively covering tuples or sets since they are pretty niche" -->
---

## Lists

```py
# Creating an empty list
empty_list = []

# Creating a list with pre-existing values
random_byte = 0x7F
random_list = ["Python is alright", -286.242, False, random_byte, False]
```

* Can include multiple data types (including more lists)
* Can be as long as you want (just watch out for memory usage)
* Objects can be added, changed, or removed from the list
* Lists can also be sorted, joined (to another list), and emptied

---

### Accessing and Changing Values

```py
burrito = ["Flour tortilla", "Cheese", "Black beans", "Rice", "Hot sauce"]
print(burrito[0], burrito[1])
>>> Flour tortilla Cheese

burrito[1] = "Shredded Cheese"
print(burrito[1])
>>> Shredded Cheese
```

* Values in the list can be accessed by specifying a specific index
  * Indices are the position in which the data is located
  * Indices start at 0 and increment by one
* Values can be changed by setting the index equal to something

---

#### Negative Indices and Slicing

```py
burrito = ["Flour tortilla", "Cheese", "Black beans", "Rice", "Hot sauce"]
# Prints the last value in the list
print(burrito[-1])
>>> Hot sauce

# Prints the first index to the fourth (excluding the last index)
print(burrito[1:4])
>>> ['Cheese', 'Black beans', 'Rice']
```

* Negative indices work in reverse order (and start at 1)
* Slicing refers to selecting a range of indices to use
  * Starting index is inclusive, the ending index is exclusive
  * Empty slice values default to `[beginning:end:step 1]`

---

### Adding and Removing Values

```py
# Add "Chicken" to the end of the list
burrito.append("Chicken")
print(burrito)
>>> ['Flour tortilla', 'Cheese', 'Black beans',
     'Rice', 'Hot sauce', 'Chicken']

# Remove the first instance of the value "Chicken"
burrito.remove("Chicken")
print(burrito)
>>> ['Flour tortilla', 'Cheese', 'Black beans', 'Rice', 'Hot sauce']
```

* `append(value: Any)` adds the given value to the end of the list
* `remove(value: Any)` removes the first occurrence of the value

---

### Adding and Removing Indices

```py
# Insert "Chicken" at the fourth index
burrito.insert(4, "Chicken")
print(burrito)
>>> ['Flour tortilla', 'Cheese', 'Black beans',
     'Rice', 'Chicken', 'Hot sauce']

# Remove the fourth value from the list
burrito.pop(4)
print(burrito)
>>> ['Flour tortilla', 'Cheese', 'Black beans', 'Rice', 'Hot sauce']
```

* `insert(index: int, value: Any)` adds a value at the indexed position
* `pop(index: int)` removes the value at the given index of a list

---

## Dictionaries

```py
dishwasher = {"Forks": 1, "Spoons": 7, "Cutting knife": 4,
              "Butter knife": 3, "Plates": 1, "Bowls": 7}
clean_items = {"Forks": 9, "Spoons": 3, "Cutting knife": 6,
               "Butter knife": 7, "Plates": 14, "Bowls": 8}

print(dishwasher["Plates"])
print(clean_items["Plates"])
>>> 1
>>> 14
```

* Use key-value pairs and are indexed by `str` values
  * Can also use `clean_items.get("Forks")`
* Values can also be anything (including more dictionaries)

---

### Getting Keys and Values

```py
print(clean_items.keys())   # Returns a <dict_keys> type
>>> ['Forks', 'Spoons', 'Cutting knife', 'Butter knife', 'Plates', 'Bowls']
print(clean_items.values()) # Returns a <dict_values> type
>>> [9, 3, 6, 7, 14, 8]
print(clean_items.items())  # Returns a <dict_items> type
>>> [["Forks", 9], ["Spoons", 3], ["Cutting knife", 6],
     ["Butter knife", 7], ["Plates", 14], ["Bowls", 8]]
```

* `keys()` returns a list* of keys in the dict
* `values()` returns a list* of values in the dict
* `items()` returns a list* of all key-value pair lists (a list of lists)
* *These will need to be type cast to a `list` to be subscriptable

---

### Adding and Removing Keys

```py
# Set "Pans" equal to 4
clean_items.update({"Pans": 4})
print(clean_items["Pans"])
>>> 4

# Remove "Pans" from the dictionary
clean_items.pop("Pans")
print(clean_items["Pans"])
>>> KeyError
```

* `update(entry: dict)` updates the dict entry's value
  * Can use `clean_items["Pans"] = 4`, even if that key doesn't exist
* `pop(entry: str)` deletes an entry in the dict
