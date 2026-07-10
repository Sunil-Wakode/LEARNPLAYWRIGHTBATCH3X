# Source Code → Bytecode → Binary

This note explains how the same program moves from a human-readable source file into intermediate bytecode and finally into machine-readable binary. The structure mirrors a learning note style with a comparison table, a simple code walkthrough, a pipeline diagram, and a concise TL;DR.

## Breakdown Table

| Layer | What it is | Who reads it | Example representation | Purpose |
|---|---|---|---|---|
| Source Code | Text written by humans in a programming language | Developers, editors | `console.log("Hello, world!");` | Express program logic clearly |
| Bytecode | Intermediate instructions for a virtual machine | Language runtime / VM | `LOAD_CONST "Hello, world!"; CALL_METHOD console.log` | Enable portability and optimization |
| Binary | Machine instructions for a CPU | CPU / hardware | `0x55 0x48 0x89 ...` | Execute directly on hardware |

## Example Walkthrough

Imagine a simple JavaScript source file named `hello.js`.

### 1) Source Code

File: `hello.js`
```js
console.log("Hello, world!");
```

- This is the file a developer writes.
- It is easy to read and modify.
- It must be parsed before execution.

### 2) Bytecode (Intermediate Layer)

After parsing, a JavaScript engine like V8 converts the source into bytecode.

Pseudo bytecode representation:
```text
LOAD_GLOBAL console
LOAD_ATTR log
LOAD_CONST "Hello, world!"
CALL_FUNCTION 1
RETURN_VALUE
```

- This form is not meant for developers.
- It is consumed by the JavaScript runtime.
- Bytecode is typically platform-independent for the VM.

### 3) Binary (Machine Code)

In the final stage, the runtime may compile bytecode to CPU machine code.

Pseudo binary bytes:
```text
55 48 89 E5 48 83 EC 20 48 8D 3D ...
```

- This is what the processor executes directly.
- It is architecture-specific (x86, ARM, etc.).
- Binary is the lowest-level representation in the pipeline.

## Pipeline Diagram

```text
Source Code (hello.js)
          |
          | parse / compile
          v
Bytecode (VM instructions)
          |
          | optimize / JIT compile
          v
Binary (CPU machine code)
```

- `parse / compile`: converts source text into a structured intermediate form.
- `optimize / JIT compile`: prepares bytecode for fast execution on real hardware.

## TL;DR

- Source code is human-readable text written in a programming language.
- Bytecode is an intermediate VM-friendly format used by runtimes.
- Binary is the CPU-ready machine code executed by hardware.
- The conversion path is: source → parse/compile → bytecode → optimize/JIT → binary.
- This layered model helps make code portable, optimizable, and executable.
