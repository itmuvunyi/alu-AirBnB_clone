# HBnB

**HBnB** is a complete web application that integrates database storage, a back-end API, and a front-end interface in a clone of AirBnB. This project is the first step toward building a full web application. It includes a custom command-line interface (CLI) for data management and base classes for data storage.

---


## Table of Contents
- [Project Description](#project-description)
- [Command Interpreter](#command-interpreter)
- [Installation](#installation)
- [Usage](#usage)
  - [Commands](#commands)
  - [Alternative Syntax](#alternative-syntax)
- [Examples](#examples)
- [Contributing](#contributing)
- [Authors](#authors)

---

## Project Description
HBnB allows users to manage objects (e.g., users, places, etc.) through a command-line interface. It simulates key functionalities of AirBnB, storing data persistently and providing an interactive way to manipulate it.

---

## Command Interpreter
The CLI is accessed via the `console.py` file. The prompt `(hbnb)` indicates you are in the HBnB console. The interpreter supports:

- Creating, updating, showing, and deleting objects
- Displaying all objects or filtering by class
- Advanced syntax for method-like commands

---

## Installation
1. Clone this repository:  
   ```bash
   git clone <repository_url>
2. Navigate to the project directory:
    ```bash
   cd AirBnB_clone
3. Run the console:
   ```bash
   ./console.py
4. The CLI prompt should appear:
   ```bash
   (hbnb)
## Usage
First clone this repository.

Once the repository is cloned locate the "console.py" file and run it as follows:
```
/AirBnB_clone$ ./console.py
```
When this command is run the following prompt should appear:
```
(hbnb)
```
This prompt designates you are in the "HBnB" console. There are a variety of commands available within the console program.

## Commands
```
* create - Creates an instance based on given class

* destroy - Destroys an object based on class and UUID

* show - Shows an object based on class and UUID

* all - Shows all objects the program has access to, or all objects of a given class

* update - Updates existing attributes an object based on class name and UUID

* quit - Exits the program (EOF will as well)
```
## Alternative Syntax
Users are able to issue a number of console command using an alternative syntax:

```Usage: <class_name>.<command>([<id>[name_arg value_arg]|[kwargs]])```
Advanced syntax is implemented for the following commands:
```
* all - Shows all objects the program has access to, or all objects of a given class

* count - Return number of object instances by class

* show - Shows an object based on class and UUID

* destroy - Destroys an object based on class and UUID

* update - Updates existing attributes an object based on class name and UUID
```
## Examples
### Primary Command Syntax
  ```bash
  Example 0: Create an object
  ```
Usage: create <class_name>
```
(hbnb) create BaseModel
(hbnb) create BaseModel
3aa5babc-efb6-4041-bfe9-3cc9727588f8
(hbnb)
```
```bash               
Example 1: Show an object
```
Usage: show <class_name> <_id>
```
(hbnb) show BaseModel 3aa5babc-efb6-4041-bfe9-3cc9727588f8
[BaseModel] (3aa5babc-efb6-4041-bfe9-3cc9727588f8) {'id': '3aa5babc-efb6-4041-bfe9-3cc9727588f8', 'created_at': datetime.datetime(2020, 2, 18, 14, 21, 12, 96959), 
'updated_at': datetime.datetime(2020, 2, 18, 14, 21, 12, 96971)}
(hbnb)
```
```bash
Example 2: Destroy an object
```
Usage: destroy <class_name> <_id>
```

(hbnb) destroy BaseModel 3aa5babc-efb6-4041-bfe9-3cc9727588f8
(hbnb) show BaseModel 3aa5babc-efb6-4041-bfe9-3cc9727588f8
** no instance found **
(hbnb)
```
```bash
Example 3: Update an object
```
Usage: update <class_name> <_id>
```
(hbnb) update BaseModel b405fc64-9724-498f-b405-e4071c3d857f first_name "person"
(hbnb) show BaseModel b405fc64-9724-498f-b405-e4071c3d857f
[BaseModel] (b405fc64-9724-498f-b405-e4071c3d857f) {'id': 'b405fc64-9724-498f-b405-e4071c3d857f', 'created_at': datetime.datetime(2020, 2, 18, 14, 33, 45, 729889), 
'updated_at': datetime.datetime(2020, 2, 18, 14, 33, 45, 729907), 'first_name': 'person'}
(hbnb)
```
## Alternative Syntax
   ```bash
   Example 0: Show all User objects
   ```
Usage: <class_name>.all()
```
(hbnb) User.all()
["[User] (99f45908-1d17-46d1-9dd2-b7571128115b) {'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 34, 92071), 'id': '99f45908-1d17-46d1-9dd2-b7571128115b', 'created_at': datetime.datetime(2020, 2, 19, 21, 47, 34, 92056)}", "[User] (98bea5de-9cb0-4d78-8a9d-c4de03521c30) {'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134362), 'id': '98bea5de-9cb0-4d78-8a9d-c4de03521c30', 'created_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134343)}"]
```
```bash
Example 1: Destroy a User
```
Usage: <class_name>.destroy(<_id>)
```
(hbnb) User.destroy("99f45908-1d17-46d1-9dd2-b7571128115b")
(hbnb)
(hbnb) User.all()
(hbnb) ["[User] (98bea5de-9cb0-4d78-8a9d-c4de03521c30) {'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134362), 'id': '98bea5de-9cb0-4d78-8a9d-c4de03521c30', 'created_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134343)}"]
```
```bash
Example 2: Update User (by attribute)
```
Usage: <class_name>.update(<_id>, <attribute_name>, <attribute_value>)
```
(hbnb) User.update("98bea5de-9cb0-4d78-8a9d-c4de03521c30", name "Todd the Toad")
(hbnb)
(hbnb) User.all()
(hbnb) ["[User] (98bea5de-9cb0-4d78-8a9d-c4de03521c30) {'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134362), 'id': '98bea5de-9cb0-4d78-8a9d-c4de03521c30', 'name': 'Todd the Toad', 'created_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134343)}"]
```
```bash
Example 3: Update User (by dictionary)
```
Usage: <class_name>.update(<_id>, )
```
(hbnb) User.update("98bea5de-9cb0-4d78-8a9d-c4de03521c30", {'name': 'Fred the Frog', 'age': 9})
(hbnb)
(hbnb) User.all()
(hbnb) ["[User] (98bea5de-9cb0-4d78-8a9d-c4de03521c30) {'updated_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134362), 'name': 'Fred the Frog', 'age': 9, 'id': '98bea5de-9cb0-4d78-8a9d-c4de03521c30', 'created_at': datetime.datetime(2020, 2, 19, 21, 47, 29, 134343)}"]
```
## Contributing

. Use branches and pull requests on GitHub to organize work

. Follow clear commit messages and code style conventions

. Ensure new features include proper CLI examples and tests

---

## **AUTHOR**

```text
Innocent Tito Muvunyi <>
