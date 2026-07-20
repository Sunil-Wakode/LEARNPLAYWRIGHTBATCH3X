# Compiler vs Interpreter

## Example File: `hello.js`

```js
console.log("Hello, World!");
```

---

## Comparison Table

| Aspect | Compiler | Interpreter |
|--------|----------|-------------|
| **What it does** | Translates the full program into machine code before execution | Executes the program line by line (or statement by statement) |
| **Execution style** | Whole-program translation first | Direct execution on the fly |
| **Typical output** | Native executable file | No separate executable file; runtime executes code directly |
| **Performance** | Usually faster after compilation | Usually slower because of runtime interpretation overhead |
| **Error detection** | Often finds many errors before running | May stop at the first error encountered during execution |
| **Portability** | Depends on target platform and compiled binary | More portable because the interpreter can run on many systems |
| **Examples** | C, C++, Rust, Go | Python, JavaScript, Ruby, PHP |
| **Best use case** | Performance-critical apps, system tools | Quick scripting, dynamic workflows, rapid development |

---

## How It Works for Our Example

### 1. Source Code — What You Write

```js
console.log("Hello, World!");
```

This is plain text stored in `hello.js`. A human can read it easily.

### 2. Compiler Path

A compiler reads the whole file, analyzes it, and converts it into machine code before execution.

Conceptually:

```text
hello.js
   ↓
compile entire file
   ↓
machine code / native executable
   ↓
run on CPU
```

Example: when you compile a C program, the compiler produces a binary that the OS can run directly.

### 3. Interpreter Path

An interpreter does not create a machine-code executable first. Instead, it reads the source and executes it step by step.

Conceptually:

```text
hello.js
   ↓
read statement
   ↓
interpret and execute immediately
   ↓
move to next statement
```

Example: when Node.js runs a JavaScript file, it interprets the JS source or converts it into an internal intermediate form before execution.

---

## Simple Walkthrough

### JavaScript Example

```js
let x = 2;
let y = 3;
console.log(x + y);
```

#### Compiler-style behavior
- The compiler analyzes the full source program.
- It translates the program into an optimized output form.
- The output can then run many times.

#### Interpreter-style behavior
- The interpreter reads `let x = 2;`.
- Then it reads `let y = 3;`.
- Then it evaluates `console.log(x + y);`.
- It does this as the program is being run.

> Key idea: a compiler translates first; an interpreter executes while reading.

---

## Pipeline Diagram

```text
┌──────────────────┐      ┌──────────────────┐      ┌──────────────────┐
│ Source Code      │ ───► │ Compiler         │ ───► │ Machine Code     │
│ hello.js         │      │ translates once  │      │ fast native run  │
└──────────────────┘      └──────────────────┘      └──────────────────┘

┌──────────────────┐      ┌──────────────────┐
│ Source Code      │ ───► │ Interpreter      │
│ hello.js         │      │ executes while   │
│                  │      │ reading/handling │
└──────────────────┘      └──────────────────┘
```

---

## Quick Rule of Thumb

| If you want to... | Use |
|-------------------|-----|
| Build high-performance native apps | **Compiler** |
| Write quick scripts and dynamic code | **Interpreter** |
| Run code with less upfront translation cost | **Interpreter** |
| Produce a standalone executable | **Compiler** |

---

> **TL;DR:**
> A compiler translates the whole program before running it.
> An interpreter runs the program directly, statement by statement.
> Compilers usually favor speed after build; interpreters favor flexibility and quick execution.
