# Single Responsibility Principle

"There should never be more than one reason for a class to change."

The Single Responsibility Principle (SRP) is one of the five principles of object-oriented design known as S.O.L.I.D.

It states that a class should have only one reason to change, meaning it should only have one central job or responsibility. 
This principle helps in creating more maintainable and understandable code.

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