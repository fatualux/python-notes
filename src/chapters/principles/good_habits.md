# Basic rules to write good code

### D.R.Y. (Don't Repeat Yourself)

Duplicating some parts of code is an extremely bad practice.

It causes the code to become hardly readable, redundant and difficult to maintain.

### PEP8

PEP8 is a style guide for Python code.

This acronym, PEP, stands for ***Python Enhancement Proposal***, and it is the primary way to propose new features in Python and share issues and suggestions with the community.

The most famous, [PEP8](https://peps.python.org/pep-0008/), lays down a simple set of guidelines to keep the code readable and maintainable.

Some PEP8's rules are:

- Use 4 spaces per indentation level.
- Use 79 characters per line.
- Surround top-level function and class definitions with two blank lines.
- Method definitions inside a class are surrounded by a single blank line.
- Extra blank lines may be used to separate groups of related functions.
- Use blank lines in functions, sparingly, to indicate logical sections.
- Imports should usually be on separate lines:
- Imports are always put at the top of the file.

### KISS (Keep It Simple, Stupid)

Simplicity is key in coding. Keeping code simple makes it more readable, maintainable, and less prone to errors. Avoid over-engineering and aim for the simplest solution that works.

### Refactoring

Refactoring involves changing the structure of existing code without changing its behavior to improve readability and maintainability. Regular refactoring helps in keeping the codebase clean and adaptable.

- **Extract Methods**: Break down large functions into smaller, more manageable ones.
- **Rename Variables**: Use descriptive names to make the code more understandable.
- **Remove Dead Code**: Eliminate unused or redundant code to reduce complexity.

### Testing

Testing ensures that your code works as expected and helps catch bugs early. 

- **Unit Tests**: Test individual units of code (e.g., functions or classes) in isolation.
- **Integration Tests**: Test the interactions between different parts of the application.
- **Test-Driven Development (TDD)**: Write tests before implementing the code to ensure that the code meets the desired specifications.

