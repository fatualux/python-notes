# Single Responsibility Principle

”The single responsibility principle states that every module or class 
should have responsibility over a single part of the functionality 
provided by the software, and that responsibility should be entirely 
encapsulated by the class, module or function. All its services should be 
narrowly aligned with that responsibility." (Wikipedia)

”A class should have only one reason to change.” 
(Robert C. Martin, Agile Software Development)

The Single Responsibility Principle (SRP) is one of the five principles of object-oriented design known as S.O.L.I.D.

It states that a class should have only one reason to change, meaning it should only have one central job or responsibility. 
This principle helps in creating more maintainable and understandable code.

”We want to design components that are self-contained: independent, 
and with a single, well-defined purpose ([...] cohesion). When 
components are isolated from one another, you know that you can 
change one without having to worry about the rest.”
(Andrew Hunt, David Thomas, The Pragmatic Programmer)

Prefer cohesive software entities. Everything that does not 
strictly belong together, should be separated

## Example:

The wrong way:
```python
class ToDoList:
    def __init__(self):
        self.tasks = []

    def add_task(self, task: str):
        self.tasks.append(task)

    def delete_task(self, task: str):
        self.tasks.remove(task)

    def get_tasks(self):
        return self.tasks

    def input_tasks(self):
        tasks = input("Enter a task: ")
        self.add_task(tasks)

    def remove_task(self):
        tasks = input("Enter a task to remove: ")
        self.delete_task(tasks)

    # the ToDoList class handles multiple responsibilities:
    # managing tasks, handling user input, and displaying tasks.
    # This violates the SRP, which states that a class should have only
    # one reason to change.
```

The right way:
```python
class TaskManager:
    def __init__(self):
        self.tasks = []

    def add_task(self, task: str):
        self.tasks.append(task)

    def delete_task(self, task: str):
        self.tasks.remove(task)

    def get_tasks(self):
        return self.tasks

class TaskInputHandler:
    def __init__(self, task_manager: TaskManager):
        self.task_manager = task_manager

    def input_tasks(self):
        tasks = input("Enter a task: ")
        self.task_manager.add_task(tasks)

    def remove_task(self):
        tasks = input("Enter a task to remove: ")
        self.task_manager.delete_task(tasks)

class TaskDisplay:
    def __init__(self, task_manager: TaskManager):
        self.task_manager = task_manager

    def display_tasks(self):
        for task in self.task_manager.get_tasks():
            print(f"Task: {task}")
```