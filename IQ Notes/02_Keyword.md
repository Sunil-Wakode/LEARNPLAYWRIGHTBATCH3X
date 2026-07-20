# JavaScript Keywords

## Example File: `02_Keywords.js`

```js
class Robot {
  static count = 0;
  constructor(name) {
    this.name = name;
    Robot.count++;
  }
  async greet() {
    if (this.name) {
      return `Hello, I am ${this.name}`;
    } else {
      throw new Error("No name set");
    }
  }
}

export default Robot;
```

---

## What Is a Keyword?

A **keyword** is a word reserved by the JavaScript language spec. It has special meaning to the parser/engine and **cannot be used as a variable, function, or class name** (e.g. `let const = 5;` throws `SyntaxError`).

---

## Comparison Table — All JS Keywords by Category

| Category               | Keywords                                                              | Reserved? | Example Use                                  |
|-------------------------|------------------------------------------------------------------------|-----------|-----------------------------------------------|
| **Declaration**         | `var`, `let`, `const`, `function`, `class`                            | ✅ Always | `const x = 1;`                                |
| **Control Flow**        | `if`, `else`, `switch`, `case`, `default`, `break`, `continue`        | ✅ Always | `if (x) {} else {}`                           |
| **Loops**                | `for`, `while`, `do`, `in`, `of`                                       | ✅ Always | `for (const k in obj) {}`                     |
| **Functions/Return**    | `function`, `return`, `yield`, `async`, `await`                       | ✅ Always | `async function f() { await g(); }`           |
| **Error Handling**      | `try`, `catch`, `finally`, `throw`                                    | ✅ Always | `try {} catch (e) {}`                         |
| **Classes/OOP**         | `class`, `extends`, `super`, `static`, `new`, `this`                  | ✅ Always | `class B extends A { constructor(){super();} }` |
| **Modules**              | `import`, `export`, `default`, `from`, `as`                           | ✅ Always | `import x from "./x.js";`                     |
| **Operators (word-form)** | `typeof`, `instanceof`, `in`, `delete`, `void`, `new`                | ✅ Always | `typeof x === "string"`                       |
| **Literals**             | `true`, `false`, `null`                                                | ✅ Always | `let x = null;`                               |
| **Misc/Legacy**          | `debugger`, `with`, `void`                                             | ✅ Always | `debugger;`                                   |
| **Strict-mode reserved** | `implements`, `interface`, `package`, `private`, `protected`, `public`, `enum` | ⚠️ Reserved but unused in current spec | future-proofing only |
| **Contextual (not fully reserved)** | `let`, `static`, `async`, `await`, `get`, `set`, `of`, `from`, `as`, `yield` | ⚠️ Depends on context | `let` is fine as a property name: `obj.let = 1` |

---

## How It Works for Our Example

### 1. Declaration keywords
```js
class Robot {
  static count = 0;
```
`class` declares a blueprint. `static` attaches `count` to the class itself, not to instances.

### 2. Constructor + `this`
```js
constructor(name) {
    this.name = name;
    Robot.count++;
}
```
`this` refers to the instance being built. `constructor` is a reserved method name inside a `class` body (not a general keyword, but has special meaning there).

### 3. Async + control flow + error handling
```js
async greet() {
    if (this.name) {
      return `Hello, I am ${this.name}`;
    } else {
      throw new Error("No name set");
    }
}
```
`async` marks the method as promise-returning. `if/else` branches. `return` exits with a value. `throw` raises an error that a caller must `try/catch`.

### 4. Module keyword
```js
export default Robot;
```
`export` exposes the class to other files; `default` marks it as the file's primary export.

---

## Keyword Processing Pipeline (Visual)

```
┌─────────────────┐      ┌──────────────────────┐      ┌─────────────────────┐
│   Source Code   │ ───► │   Lexer/Tokenizer     │ ───► │   Parser (AST)      │
│  (raw .js text) │      │ splits into tokens    │      │ builds syntax tree  │
│                 │      │ keywords flagged as   │      │ keywords become     │
│                 │      │ reserved token type   │      │ AST node types      │
└─────────────────┘      └──────────────────────┘      └─────────────────────┘
                                                                   │
                                                                   ▼
                                                     ┌─────────────────────────┐
                                                     │ Engine (V8) executes    │
                                                     │ per keyword semantics:  │
                                                     │ class → prototype setup │
                                                     │ try/catch → exception   │
                                                     │ async → microtask queue │
                                                     └─────────────────────────┘
```

---

## Quick Rule of Thumb

| If you want to...                          | Reach for keyword(s)             |
|---------------------------------------------|-----------------------------------|
| Declare a variable that can change           | `let`                             |
| Declare a variable that can't be reassigned  | `const`                           |
| Define reusable behavior                     | `function`, `class`               |
| Branch logic                                 | `if / else`, `switch`             |
| Repeat work                                  | `for`, `while`, `do`              |
| Handle failures                              | `try / catch / finally`, `throw`  |
| Share code across files                      | `import`, `export`                |
| Wait on a Promise                            | `async`, `await`                  |
| Check a type at runtime                      | `typeof`, `instanceof`            |

---

> **TL;DR:** JS keywords are the ~35 reserved words (`if`, `for`, `class`, `const`, `try`, `async`, etc.) the parser treats as syntax, not identifiers. They split into always-reserved (can never be a variable name) and contextual (reserved only in certain positions, like `let` or `async`). Every keyword maps to one job: declare, branch, loop, handle errors, define classes, or move data between modules.


# JavaScript `keyword`

## What is a Keyword?

In JavaScript, a `keyword` is a reserved word that has a special meaning in the language. It is built into the language syntax and cannot be used freely as a variable name, function name, or property name in normal code.

### Example

```js
let name = "Aman";
if (name === "Aman") {
  console.log("Hello");
}
```

Here:
- `let` is a keyword used to declare a variable.
- `if` is a keyword used for conditional logic.
- `console` is not a keyword; it is an object.
- `name` is an identifier, not a keyword.

---

## Comparison Table

| Aspect | Keyword | Identifier | Reserved Word |
|--------|---------|------------|---------------|
| **Meaning** | Built-in language word with fixed purpose | Name chosen by the programmer | Word that cannot be used as a normal identifier |
| **Example** | `if`, `for`, `class` | `userName`, `sum`, `myFunc` | `await`, `yield`, `let` |
| **Can be used as variable name?** | ❌ No | ✅ Yes | ❌ Usually no |
| **Purpose** | Controls syntax and behavior | Stores or references program data | Prevents name collisions with language syntax |
| **Role in code** | Structural | Custom naming | Language-protected word |

---

## JavaScript Keywords (Reserved Words)

### 1. Variable / Function / Class Declaration

| Keyword | Use |
|---------|-----|
| `var` | Declares a function-scoped variable |
| `let` | Declares a block-scoped variable |
| `const` | Declares a block-scoped constant |
| `function` | Declares a function |
| `class` | Declares a class |

### 2. Control Flow

| Keyword | Use |
|---------|-----|
| `if` | Starts a conditional statement |
| `else` | Handles the false branch |
| `switch` | Multi-condition branching |
| `case` | Defines a switch branch |
| `default` | Default switch branch |
| `break` | Exits a loop or switch |
| `continue` | Skips to the next loop iteration |
| `return` | Returns a value from a function |

### 3. Looping / Iteration

| Keyword | Use |
|---------|-----|
| `for` | Creates a for-loop |
| `while` | Creates a while-loop |
| `do` | Starts a do-while loop |
| `in` | Checks property existence in an object or loop |
| `of` | Iterates over iterable values |

### 4. Exception Handling

| Keyword | Use |
|---------|-----|
| `try` | Starts exception handling |
| `catch` | Handles thrown errors |
| `finally` | Runs after try/catch regardless of result |
| `throw` | Throws an error |

### 5. Object / Prototype / New Object Creation

| Keyword | Use |
|---------|-----|
| `new` | Creates a new object instance |
| `this` | Refers to the current object |
| `extends` | Creates a class that inherits from another |
| `super` | Calls parent class constructor or methods |
| `instanceof` | Checks whether an object is instance of a class |
| `delete` | Deletes an object property |

### 6. Type / Value Operators

| Keyword | Use |
|---------|-----|
| `typeof` | Gets the data type of a value |
| `void` | Returns `undefined` |
| `yield` | Pauses and resumes a generator |
| `await` | Waits for a Promise in async functions |

### 7. Module Keywords

| Keyword | Use |
|---------|-----|
| `import` | Imports bindings from another module |
| `export` | Exports bindings from a module |
| `from` | Used with `import` statements |
| `as` | Renames imported or exported bindings |

### 8. Debugging / Other Special Keywords

| Keyword | Use |
|---------|-----|
| `debugger` | Inserts a breakpoint for debugging |
| `with` | Old syntax for extending scope chain (avoid in modern JS) |

---

## Important Note

Some words are considered “keywords” only in certain contexts. For example:
- `await` is a keyword in async contexts and modules.
- `yield` is used in generator functions.
- `enum`, `implements`, `interface`, `package`, `private`, `protected`, `public`, and `static` are reserved in stricter JavaScript contexts such as classes and modules.

---

## Simple Example

```js
const x = 10;

if (x > 5) {
  console.log("x is greater than 5");
}
```

Here:
- `const` → keyword
- `if` → keyword
- `console` → object name
- `x` → identifier

---

## Pipeline Flow

```text
Program Source
   ↓
JavaScript Parser reads tokens
   ↓
Recognizes keywords and syntax rules
   ↓
Builds valid code structure
```

---

> **TL;DR:**
> A JavaScript keyword is a built-in reserved word with special meaning.
> It is meant for syntax, control flow, declarations, and language behavior.
> You cannot use most keywords as normal variable or function names.
