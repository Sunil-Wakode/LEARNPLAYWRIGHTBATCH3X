# Java vs JavaScript vs TypeScript

## Example Files

### Java

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello from Java");
    }
}
```

### JavaScript

```js
console.log("Hello from JavaScript");
```

### TypeScript

```ts
const message: string = "Hello from TypeScript";
console.log(message);
```

---

## Comparison Table

| Aspect | Java | JavaScript | TypeScript |
|--------|------|------------|------------|
| **What it is** | A strongly typed, object-oriented programming language | A dynamic scripting language for web and Node.js | A typed superset of JavaScript |
| **Typing** | ✅ Strongly typed | ⚠️ Dynamically typed | ✅ Statically typed |
| **Main runtime** | JVM | Browser / Node.js / V8 | Browser / Node.js / V8 |
| **Compilation** | Compiles to bytecode (`.class`) | Interpreted/JIT-compiled by engines | Compiles to JavaScript before execution |
| **File extension** | `.java` | `.js` | `.ts` |
| **Typical use** | Enterprise apps, Android, backend services | Web pages, scripts, APIs | Large applications with safer code |
| **Syntax style** | More verbose, class-based | Flexible, lightweight | Similar to JavaScript, but with types |
| **Performance** | High after JVM optimization | Fast with JIT engines | Same runtime performance as JavaScript |

---

## How It Works for the Example

### 1. Java — What You Write and How It Runs

The Java file is written as source code and saved as `HelloWorld.java`.

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello from Java");
    }
}
```

Then the Java compiler turns it into bytecode (`.class`), and the JVM executes that bytecode.

### 2. JavaScript — What You Write and How It Runs

The JavaScript file is written as source code and saved as `hello.js`.

```js
console.log("Hello from JavaScript");
```

When Node.js or a browser runs it, the JavaScript engine executes the script, often using bytecode and JIT optimization internally.

### 3. TypeScript — What You Write and How It Runs

The TypeScript file is written as source code and saved as `hello.ts`.

```ts
const message: string = "Hello from TypeScript";
console.log(message);
```

TypeScript checks types first, then compiles the code into plain JavaScript so it can run in any JavaScript environment.

---

## The Compilation / Execution Pipeline

```text
Java:       .java  ->  Java Compiler  ->  .class bytecode  ->  JVM

JavaScript: .js    ->  JS Engine (V8/Node/Browser)  ->  Execution

TypeScript: .ts    ->  TypeScript Compiler  ->  .js  ->  JS Engine  ->  Execution
```

---

## Quick Rule of Thumb

| If you want to... | Use |
|-------------------|-----|
| Build large enterprise or backend systems | **Java** |
| Build web scripts or frontend/backend logic quickly | **JavaScript** |
| Build safer large-scale apps with fewer runtime errors | **TypeScript** |

---

> **TL;DR:** 
| Java is a strongly typed, JVM-based language.
| JavaScript is the dynamic language used in browsers and Node.js.
| TypeScript is JavaScript with type checking, compiled to plain JavaScript before execution.
