# `var`, `let`, and `const` in JavaScript

## Example File: `variables.js`

```js
var a = 1;
let b = 2;
const c = 3;

function demo() {
  var x = "function scope";
  if (true) {
    let y = "block scope";
    const z = 10;
  }
}
```

---

## Comparison Table

| Aspect | `var` | `let` | `const` |
|--------|-------|------|---------|
| **Scope** | Function-scoped | Block-scoped | Block-scoped |
| **Hoisting** | Yes, initialized to `undefined` | Yes, in TDZ | Yes, in TDZ |
| **Re-declaration** | ✅ Allowed | ❌ Not allowed in same scope | ❌ Not allowed in same scope |
| **Re-assignment** | ✅ Allowed | ✅ Allowed | ❌ Not allowed |
| **Use case** | Older scripts, legacy code | General variable declaration | Constants / fixed values |
| **Common preference** | Avoid in modern JS | Preferred for changeable values | Preferred for fixed values |

---

## How It Works

### 1. `var`

`var` is function-scoped. That means if you declare it inside a function, it is accessible anywhere inside that function.

```js
function test() {
  var x = 10;
  if (true) {
    var y = 20;
  }
  console.log(x, y); // works
}
```

`var` is also hoisted, but its value is initialized to `undefined` until assignment.

### 2. `let`

`let` is block-scoped. It is only accessible inside the block where it is declared.

```js
function test() {
  let x = 10;
  if (true) {
    let y = 20;
  }
  console.log(x); // works
  console.log(y); // error
}
```

`let` can be reassigned, but not redeclared in the same scope.

### 3. `const`

`const` is also block-scoped, but its value cannot be reassigned after initialization.

```js
const pi = 3.14;
pi = 3.1415; // error
```

Use `const` when the value should stay fixed.

---

## Simple Example Walkthrough

```js
var name = "Aman";
let age = 25;
const country = "India";

name = "Rahul";   // allowed
age = 30;         // allowed
country = "USA";  // error
```

### What happens here?
- `var name` can be reassigned.
- `let age` can be reassigned.
- `const country` cannot be reassigned.

---

## Pipeline Diagram

```text
┌──────────────┐
│ declare value│
└──────┬───────┘
       │
       ├── `var` → function scope, can re-declare, can reassign
       ├── `let` → block scope, cannot re-declare, can reassign
       └── `const` → block scope, cannot re-declare, cannot reassign
```

---

## Quick Rule of Thumb

| Use this when... | Keyword |
|------------------|---------|
| You want a variable that can be changed and is old-style | `var` |
| You want a modern, flexible variable | `let` |
| You want a value that should never change | `const` |

---

> **TL;DR:**
> `var` is function-scoped and legacy.
> `let` is block-scoped and mutable.
> `const` is block-scoped and immutable.
> In modern JavaScript, prefer `let` and `const` over `var`.
