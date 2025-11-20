# Factory Method

Normally, we create objects directly using class constructors.

However, in some scenarios, we might want to delegate the instantiation logic to subclasses. This is where the **Factory Method** pattern comes into play.

This approach has a major architectural disadvantage:
• You have to know the exact class type you want to instantiate.

**Why is this bad?**

Think of this: what if we wanted to create an app that used different types of classes that we have not even thought of yet?

The main problem with this approach is that your code is unnecessarily aware of the type of objects that it creates and thus it is **strongly coupled** with the type.

The **Factory Method** pattern defines an **interface** for creating an object but allows subclasses to alter the type of objects that will be created.

## A good rule

**Define an interface** for creating an object, but let subclasses decide which class to instantiate.

**Factory Method** lets a class defer instantiation to subclasses.

This pattern is often used with the following **GoF patterns**:

**Strategy** and **Iterator** design patterns are often used with **Factory Method** pattern to let collection subclasses return different types of iterators that are compatible with the collections.

## PROS
1. It allows sub-classes to **choose the type of objects to create**.
2. **Simple to implement** (simpler than **Builder** pattern).
3. Promotes **loose-coupling** by eliminating the need to bind application-specific classes into the code.
   That means the code interacts only with the resultant **interface** or **abstract class**.
4. **Single Responsibility Principle**.
   You can move the creation code into one place in the program, making the code easier to support.
5. **Open/Closed Principle**.
   You can introduce new subtypes into the program without breaking existing client code. This results in **Clean code**.

## CONS
1. One disadvantage of the **Factory Method** pattern is that it can **expand the total number of classes** in a system.
   Every concrete class also requires a concrete Creator class.
   Note: the **Parameterized Factory Method** avoids this downside.
2. Another potential downside is that the Creator classes may become **overly complex** if they are responsible for creating many different types of products.
   In such cases, it may be better to use a different creational pattern, such as the **Abstract Factory** or **Builder pattern**.

## Design Considerations:
1. When you have many objects of a common type (like for example a **Shape**)
   a. Make all such object types (like for example **IShape**) follow the same
      interface or extend the same abstract class. This interface should declare
      methods that make sense in every **Shape** but in a generalized way.
2. Create a **Factory** with a static creation method which always returns the same common interface reference (for example **IShape**)
   Let the **Factory** know which instance you want, through some sort of a constant id for the specific object type.
   a. This can be accomplished through an **enum** or a list of constants which could be integers or strings.

There are two main variants of the pattern:
1. The very popular **Simple Factory Method** variant (also called **Parameterized Factory Method pattern**).

![](../static/images/factoryUML_0.png)

2. The classic (or original) **GoF Factory Method** variant.

![](../static/images/factoryUML_1.png)

For every concrete instance of the implementation of the common interface.