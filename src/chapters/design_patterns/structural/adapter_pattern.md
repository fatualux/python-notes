# Adapter Pattern

![UML](../../../static/images/adapter_uml.png)

**Adapter** is a structural design pattern which is used to convert the interface
contract of one class to be compatible with another.

This 'conversion' can take two different elements into account
1.Adapter can convert source data into formats that the client can
understand.

2.Adapter can also help objects with different (or incompatible) interfaces
collaborate.

```plaintext
It converts the interface of a class into another interface that clients expect.
Adapter lets classes work together that couldn't otherwise because of incompatible interfaces.
```

**When to use**:
- Use the Adapter pattern when you have an existing class or contract that
you would like to reuse, but its interface isn't compatible with the rest of
your code.

**When not to use**:
- When your system is very time-sensitive since 'wrapping' the Adaptee
creates a bit of an overhead as it creates an extra call layer.

**Pros**:
1. You can separate data conversion code from the main business logic of
your application. This follows the Single Responsibility Principle.
2. You can introduce Adapters into your code without breaking any existing
client code. This follows the Open/Closed Principle.
**Cons**:
1. The Adapter pattern can increase the overall complexity of your code
since you introduce a set of new interfaces and classes.

### Implementation Steps
1. Identify the service (i.e. Adaptee) class that you want to create an adapter for.
2. Declare the client interface and define how clients will communicate with the
service.
3. Define the Adapter class by implementing the client interface. Leave all the
methods stubbed (i.e. empty for the time being.)
4. Add a private field to the adapter class to store a reference to the Adaptee
object.
5. Implement each of the methods of the client interface in the Adapter class.
The adapter should delegate most of the actual work to the service (i.e.
Adaptee) object, handling only the interface or data format conversion.
6. Clients must use the Adapter via the client interface. This will let you maintain
the Adapter code without affecting the client code.
