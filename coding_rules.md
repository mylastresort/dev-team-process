# Coding Convention: Practical Guide

## 1. File Organization
* **Modular structure:** Break code into small, reusable modules, each handling a specific responsibility.
*  **Single responsibility per file:** Each file should focus on one concept or functionality (e.g., class, component, module).
*  **Consistent file naming:** Use a consistent, descriptive naming convention for files, such as snake_case for scripts or PascalCase for classes.
*  **Group similar files:** Organize files in directories based on functionality (e.g., /controllers, /models, /utils).
*  **Header guard (C++ only):** Use #ifndef, #define, and #endif to prevent duplicate inclusion of headers.
## 2. Indentation
*  **Consistent indent size:** Use tabs consistently throughout the project. Common standards are 2 or 4 spaces.
*  **Indentation for nested code:** Ensure that blocks inside loops, conditionals, and functions are properly indented in a new line.
*  **Avoid deep nesting:** Limit nesting depth by refactoring deeply nested code into smaller functions. Common nesting limit is 3 to 5 levels.
## 3. Comments
*  **Function headers:** Document functions with purpose (description), parameters, return values, and any important behavior.
*  **Explain why, not what:** Use comments to explain the reasoning behind non-obvious code rather than describing what each line does, avoid over-commenting simple code.
*  **TODO and FIXME tags:** Use these tags to mark incomplete or buggy sections for future reference.
## 4. Declarations
* **One declaration per line:** Declare each variable, constant, or object on a separate line.
* **Initialize variables:** Always initialize variables at the time of declaration where possible.
* **Avoid global variables:** Minimize global variables by confining them within functions or classes.
## 5. Statements
* **Consistent braces:** Use braces even for single-line conditional or loop statements to prevent errors during modification.
* **Avoid long statements:** Break long statements into multiple lines for readability.
* **Use meaningful conditionals:** Avoid using magic numbers or unclear logic in conditionals (use constants or explain through variable names).
## 6. White Space
* **Around operators:** Include space around operators for readability (e.g., x = y + z instead of x=y+z).
* **Between code blocks:** Separate logical blocks of code (e.g., function definitions, major sections) with an empty line.
* **Within function signatures:** Include space after commas in argument lists (e.g., void foo(int a, int b)).
## 7. Naming Conventions
* **CamelCase for variables and functions:** myVariable, processData().
* **PascalCase for classes and types:** MyClass, CarModel.
* **Descriptive names:** Choose clear, self-explanatory names for variables, functions, and classes (e.g., isRunning, calculateTotal()).
* **Avoid abbreviations:** Avoid unnecessary abbreviations unless they are commonly understood.
* **Constants in uppercase:** Use uppercase letters with underscores for constants (e.g., MAX_LIMIT).
## 8. Programming Practices
* **DRY (Don't Repeat Yourself):** Avoid repeating code by creating reusable functions or modules.
* **SOLID principles:** Follow SOLID principles (Single responsibility, Open-closed, Liskov substitution, Interface segregation, Dependency inversion) for object-oriented design.
* **Avoid premature optimization:** Focus on readability and correctness before optimizing for performance.
* **Error handling:** Ensure proper error handling with appropriate exceptions or return codes, avoiding silent failures.
* **Avoid side effects:** Functions should return values rather than modifying external state whenever possible.
* **Immutability:** Use immutable data structures or variables where applicable to prevent accidental state changes.
* **Write tests:** Always write unit tests to cover edge cases and ensure code reliability.
* **Favor composition over inheritance:** Use composition (e.g., objects containing other objects) instead of inheritance when appropriate to reduce complexity.
## 9. Architectural Best Practices
* **Separation of concerns:** Keep different layers (e.g., UI, business logic, data) separated to maintain code clarity and modularity.
* **Loose coupling:** Ensure that components of the system are as independent of each other as possible.
* **Encapsulation:** Hide internal details of a module or class and expose only the necessary interface to interact with it.
* **Single source of truth:** Ensure that data is maintained in one central place to avoid inconsistencies across the system.