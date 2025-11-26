# Programming Essentials

This guide covers fundamental concepts and best practices for writing high-quality, maintainable code.

## 1. Clean Code Principles

### Meaningful Names
- **Variables**: Use intention-revealing names. `daysSinceCreation` is better than `d`.
- **Functions**: Should be verbs or verb phrases. `calculateTax()` is better than `tax()`.
- **Classes**: Should be nouns or noun phrases. `Customer` or `WikiPage`.

### Functions
- **Small**: Functions should be small and do one thing well.
- **Arguments**: Limit the number of arguments (0-2 is ideal). Use objects for more.
- **Side Effects**: Avoid hidden side effects. A function should either do something or answer something, not both.

### Comments
- **Explain "Why", not "What"**: Code should be self-explanatory. Comments should explain the *intent* or *reasoning* behind complex logic, not describe what the code is doing line-by-line.

## 2. SOLID Principles

- **S - Single Responsibility Principle (SRP)**: A class should have one, and only one, reason to change.
- **O - Open/Closed Principle (OCP)**: Software entities should be open for extension, but closed for modification.
- **L - Liskov Substitution Principle (LSP)**: Subtypes must be substitutable for their base types.
- **I - Interface Segregation Principle (ISP)**: Clients should not be forced to depend on methods they do not use.
- **D - Dependency Inversion Principle (DIP)**: Depend on abstractions, not on concretions.

## 3. Common Design Patterns

### Creational
- **Singleton**: Ensures a class has only one instance.
- **Factory**: Creates objects without specifying the exact class of object that will be created.

### Structural
- **Adapter**: Allows incompatible interfaces to work together.
- **Decorator**: Adds behavior to an object dynamically.

### Behavioral
- **Observer**: Defines a subscription mechanism to notify multiple objects about any events that happen to the object they're observing.
- **Strategy**: Enables selecting an algorithm at runtime.

## 4. Version Control (Git) Best Practices

- **Commit Often**: Make small, atomic commits.
- **Meaningful Messages**: Write clear, descriptive commit messages (e.g., "Fix login bug" instead of "Update").
- **Branching**: Use feature branches for new development; keep `main`/`master` stable.
- **Pull Requests**: Review code before merging to catch issues early.

## 5. Testing

- **Unit Tests**: Test individual components in isolation.
- **Integration Tests**: Test how components work together.
- **TDD (Test-Driven Development)**: Write tests *before* writing the code to ensure requirements are met and code is testable.
