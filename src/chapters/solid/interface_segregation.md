# Interface Segregation Principle

"A client should not be forced to depend on interfaces it does not use."

This principle encourages the creation of smaller, more specific interfaces rather than a large, general-purpose one.

## Example

Consider a large interface for a printer:

```python
class IPrinter:
    def print_document(self, document: Document): pass
    def scan_document(self, document: Document): pass
    def fax_document(self, document: Document): pass
```

A multi-function printer implements all methods, but a simple printer only needs the `print_document` method. This forces the simple printer to implement unnecessary methods.

### Solution

Split the large interface into smaller ones:

```python
class IPrinter:
    def print_document(self, document: Document): pass

class IScanner:
    def scan_document(self, document: Document): pass

class IFax:
    def fax_document(self, document: Document): pass
```

Now, each printer can implement only the interfaces it needs, adhering to the Interface Segregation Principle.