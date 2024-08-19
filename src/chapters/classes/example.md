# Classes: code example

>Definition of the SoftwareDeveloper class
```python
class SoftwareDeveloper:
```
>The constructor method (__init__) initializes the attributes of the class
```python
    def __init__(self, name, experience, languages):
        self.name = name  # Attribute: name of the developer
        self.experience = experience  # Attribute: years of experience
        self.languages = languages  # Attribute: list of programming languages the developer knows
    # Method to add a new programming language to the developer's skill set
    def add_language(self, new_language):
        self.languages.append(new_language)  # Adds the new language to the list of known languages
        print(f"{self.name} has learned {new_language}.")
    # Method to get the developer's details as a formatted string
    def get_details(self):
        # Returns the developer's details
        return f"Name: {self.name}, Experience: {self.experience} years, Languages: {', '.join(self.languages)}"
    # Method to update the developer's experience
    def update_experience(self, new_experience):
        self.experience = new_experience  # Updates the experience attribute
        print(f"{self.name}'s experience updated to {self.experience} years.")
```
>Creating an instance of the SoftwareDeveloper class
```python
dev1 = SoftwareDeveloper("Alice", 5, ["Python", "JavaScript"])
```
>Accessing attributes and methods
```python
print(dev1.get_details())  # Output: Name: Alice, Experience: 5 years, Languages: Python, JavaScript
```
>Adding a new language
```python
dev1.add_language("Java")  # Output: Alice has learned Java.
```
>Updating experience
```python
dev1.update_experience(6)  # Output: Alice's experience updated to 6 years.
```
>Printing updated details
```python
print(dev1.get_details())  # Output: Name: Alice, Experience: 6 years, Languages: Python, JavaScript, Java
```
>Inheritance example: creating a subclass of SoftwareDeveloper
```python
class SeniorDeveloper(SoftwareDeveloper):
    def __init__(self, name, experience, languages, mentoring_experience):
        # Calling the parent class constructor to initialize inherited attributes
        super().__init__(name, experience, languages)
        self.mentoring_experience = mentoring_experience  # New attribute specific to SeniorDeveloper
    # Method to get the senior developer's details including mentoring experience
    def get_details(self):
        base_details = super().get_details()  # Get details from the parent class
        return f"{base_details}, Mentoring Experience: {self.mentoring_experience} years"
```
>Creating an instance of the SeniorDeveloper class
```python
senior_dev = SeniorDeveloper("Bob", 10, ["Python", "Java", "C++"], 4)
```
>Accessing attributes and methods from both the parent and child classes
```python
print(senior_dev.get_details())  # Output: Name: Bob, Experience: 10 years, Languages: Python, Java, C++, Mentoring Experience: 4 years
```
