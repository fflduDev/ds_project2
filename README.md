# 232L Milestone 2 – Phonebook Application

## Overview

Implement a phonebook application using the provided template. This project covers maps, generics, sorting, searching, aggregation, hashing, collision demonstration, and optionally recursion.

A phonebook stores contacts, where each contact has one or more phone numbers with associated types (e.g., Boris / Work).

---

## Required Components

### `PhonebookEntry.java`
Stores a phone number and number type (e.g., `203.403.3322 / Work`).

### `Contact.java`
Stores a contact name and their associated `PhonebookEntry` list. A contact will typically have multiple entries.
- Override `hashCode()` and `equals()`
- Implement a `hashCode()` that demonstrates collision in **some but not all** cases

### `PhonebookHandler.java`
Implements the `iPhonebookHandler` interface. Handles sorting, searching, and displaying contacts and entries.
- **No built-in JDK/collection sort or search support** — you must implement your own:
  - Sorting: Bubble Sort or Merge Sort
  - Searching: Binary Search (key: contact name)
- Do **not** use `Map.containsKey()`

### `TestHarness.java`
Exercises the full application. Update the template as needed to produce the expected output below.

---

## Expected Output

```
Building Contacts ....
Building Phonebook Entries ....
Adding Entries to the phonebook ....

Checking r1.equals(r2) for:
Name: Jan, Phone Number(s): [2034032233 Home, 5532233322 Cell, 1120092829 Work]
Name: Stan, Phone Number(s): [1034032233 Home, 2532233322 Cell, 3120092829 Work]
false

Checking r1.equals(r2) for:
Name: Juan, Phone Number(s): [4034032233 Home, 5532233322 Cell, 6120092829 Work]
Name: Juan, Phone Number(s): [4034032233 Home, 5532233322 Cell, 6120092829 Work]
true

Checking r1.hashcode = r2.hashcode for:
Name: Jan, Phone Number(s): [2034032233 Home, 5532233322 Cell, 1120092829 Work]
Name: Juan, Phone Number(s): [4034032233 Home, 5532233322 Cell, 6120092829 Work]
NO hash match: 0 / 1

Checking r1.hashcode = r2.hashcode for:
Name: Stan, Phone Number(s): [1034032233 Home, 2532233322 Cell, 3120092829 Work]
Name: Juan, Phone Number(s): [4034032233 Home, 5532233322 Cell, 6120092829 Work]
Hash matches - we're in the same bucket ( collision!): 1

Sorted Phonebook (Bubble Sort):
Jan
Juan
Mun
Ran
Stan

-- Search results for Juan --
Entries for Juan Home 4034032233
Entries for Juan Cell 5532233322
Entries for Juan Work 6120092829
```
