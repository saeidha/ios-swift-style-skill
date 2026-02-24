# Name: iOS Swift Strict Style Guide
# Description: Enforces strict Swift coding style, MARK organizations, dependency injection rules, and architectural conventions for the iOS team.

## Instructions
As an AI agent, whenever you generate, refactor, or review Swift code, you MUST strictly adhere to the following guidelines:

### 1. Organization & MARKs
Organize the code using the following `// MARK:` comments in this EXACT order. 
**Crucial Spacing Rule:** There must be exactly ONE empty line BEFORE a `// MARK:`, and NO empty lines AFTER a `// MARK:`. The code must start immediately on the line below the MARK.

// MARK: - Dependency
// MARK: - Initializer
// MARK: - Life Cycle
// MARK: - Outlets and UI Stuff
// MARK: - Private Properties
// MARK: - Public Properties
// MARK: - Public Methods
// MARK: - Private Methods
// MARK: - Dependency Injection

### 2. Closures as Dependencies
Any closure properties (e.g., `var completion: (() -> Void)?`) MUST be treated as dependencies. Place them under the `// MARK: - Dependency` section alongside other injected dependencies and delegates, right above the Initializer.

### 3. Naming Conventions
Always rename layout setup methods from `setupLayout` to `setupViews`.

### 4. Memory Management (Deinit)
Every class must explicitly include a `deinit` block that prints its name with a trash emoji, exactly like this:
```swift
deinit {
    print("🗑 ClassName")
}
```

### 5. Private Methods Order

Inside the `// MARK: - Private Methods` section, the `setupViews` and `bindingViewModel` methods MUST be the first two functions declared.

### 6. Functional Style

Prioritize functional programming paradigms. Refactor imperative logic (like `for` loops) to use higher-order functions (e.g., `map`, `filter`, `reduce`, `compactMap`) wherever applicable.

### 7. Explicit Self

Always use explicit `self.` when accessing instance properties, methods, or closures.

### 8. Spacing & Braces Rule

You MUST add exactly one empty line immediately after every opening brace `{` in classes, structs, functions, closures, and control flow statements.
