# HW 4: Classes and Objects
## QMSS G5072 Modern Data Structures

You're collaborating with a local animal shelter to modernize their animal management and adoption tracking system. They need a foundational system for managing their animals and facilitating adoptions effectively.

## 1. Animal Class

### a) Create `Animal` class

Create a class called `Animal`. Initialize it with:

- `name` (string)
- `species` (string)
- `age` (integer: the animal’s age in years)

Demonstrate the initialization of a single `Animal` object and print the object's attributes.

### b) Add `__str__` method to the `Animal` class

Add a method to `Animal` that returns a string with the following format:

```plaintext
"<name> the <species> is <age> years old."
```

Create an `Animal` object and print its string representation using the `__str__` method.

### c) Create `Animal` objects

Create 6 `Animal` objects using the following data and print their string representations:

```json
animals_data = [
    {"name": "Buddy", "species": "Dog", "age": 3},
    {"name": "Whiskers", "species": "Cat", "age": 2},
    {"name": "Chirpy", "species": "Bird", "age": 1},
    {"name": "Nibbles", "species": "Rabbit", "age": 4},
    {"name": "Goldie", "species": "Fish", "age": 1},
    {"name": "Spike", "species": "Lizard", "age": 5}
]
```

### d) Add Adoption Status

Add a method to `Animal` called `adopt` that marks the animal as adopted. Ensure that an animal cannot be adopted more than once.

```python
def adopt(self):
    # Mark the animal as adopted if it isn’t already
```

Demonstrate this method by adopting "Whiskers" and printing the updated string representation.

## 2. Shelter Class

### a) Create `Shelter` class

Create a class called `Shelter` that takes a list of `Animal` objects as an argument during initialization.

Demonstrate the initialization by creating a `Shelter` object using the animals created in 1c) and print the object's attributes.

### b) Check Animal Availability

Add a method to `Shelter` called `check_availability` that takes an animal species as an argument and returns a boolean indicating whether there is an available animal of that species.

Demonstrate this method by checking the availability for "Dog" and print the result.

### c) List Available Animals by Species

Add a method to `Shelter` called `list_by_species` that takes a species name as an argument and returns a list of all available (i.e., not yet adopted) animals of that species.

Demonstrate this method by listing all available "Cat" species.

## Bonus Question (for additional points): Implementing a Weight Monitoring System

- Modify the `Animal` class to include a `weight` attribute (float) and an `update_weight` method to change the animal's weight. Ensure the weight cannot be negative.

- Add a method `average_weight_by_species` to the `Shelter` class that takes a species name and returns the average weight of all available animals of that species.

Demonstrate this system by calculating and printing the average weight for "Dog" and "Fish" species.

## Submit your homework

Please follow the [instructions](/Exercises/homework_submission_instructions.md) to submit your homework. The homework is due on Wednesday, October 9 at 5pm.