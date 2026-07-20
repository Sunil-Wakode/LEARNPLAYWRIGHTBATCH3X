---
description: Use this skill when you need to create a concise, visually structured concept explainer in the IQ Notes folder. It turns any topic into a comparison table, walkthrough, pipeline diagram, and TL;DR summary.
---

# Concept Explainer Skill

## Purpose
Create a polished markdown explanation for a technical concept using the same visual pattern as the existing IQ note style.

## When to use this skill
Use this skill when the user wants an explanation of a concept such as:
- compiler vs interpreter
- stack vs heap memory
- source code vs bytecode vs binary
- async vs multithreading
- HTTP vs HTTPS

## Output requirements
The generated markdown file should:
1. Be saved inside the `IQ Notes` folder.
2. Use a clear heading for the concept.
3. Include a comparison table with strong, easy-to-scan columns.
4. Use a simple code or file example to explain each layer.
5. Include a visual pipeline/flow diagram.
6. End with a short TL;DR summary.

## Workflow
1. Identify the concept to explain.
2. Choose the most useful comparison dimensions.
3. Write a short, readable example that shows the concept in action.
4. Break the idea into layers or stages.
5. Present the information in this order:
   - title
   - example file or snippet
   - comparison table
   - walkthrough of each layer
   - pipeline diagram
   - TL;DR
6. Save the final result as a Markdown file in the `IQ Notes` folder.

## Decision points
- If the concept is purely theoretical, use a simple real-world analogy or tiny code example.
- If the concept has a clear lifecycle, prefer a pipeline diagram.
- If the concept involves multiple layers, explain each layer in sequence before the final summary.
- If the topic is broad, keep the explanation focused on the smallest useful example.

## Quality checklist
Before finishing, verify that the note:
- is easy to read in table form
- uses a short example instead of long abstract discussion
- has a clear “how it works” walkthrough
- includes a diagram or stage flow
- ends with a concise TL;DR section

## Example prompt
Explain `compiler vs interpreter` in a table view with clear comparison columns. Use a simple code/file example to walk through each layer. Save it as a `.md` file inside the `IQ Notes` folder. Follow the same visual style as `Source_Code_ByteCode_Binary_IQ.md` — breakdown table, example walkthrough, pipeline diagram, and TL;DR.
