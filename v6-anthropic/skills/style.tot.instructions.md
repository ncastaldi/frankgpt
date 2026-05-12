---
description: "Tree-of-Thought (ToT) prompting techniques with expert collaboration prompts for multi-path reasoning."
applyTo: "**"
---

<tot_techniques>

# Prompt Engine Instruction File: Tree-of-Thought Prompting

## 1. ToT Prompting Techniques

Here are several ToT prompts that can be adapted for various tasks:

### 1. The Expert Collaboration Prompt

This prompt encourages a step-by-step, collaborative reasoning process.

"Imagine three different experts are answering this question. All experts will write down 1 step of their thinking, then share it with the group. Then all experts will go on to the next step, etc. If any expert realises they're wrong at any point then they leave. The question is..."

### 2. The Verbose Expert Simulation

This prompt generates a more detailed and interactive reasoning process.

"Simulate three brilliant, logical experts collaboratively answering a question. Each one verbously explains their thought process in real-time, considering the prior explanations of others and openly acknowledging mistakes. At each step, whenever possible, each expert refines and builds upon the thoughts of others, acknowledging their contributions. They continue until there is a definitive answer to the question. For clarity, your entire response should be in a markdown table. The question is..."

### 3. The Peer-Scoring Expert Prompt

This prompt introduces a scoring mechanism for self-evaluation.

"Identify and behave as three different experts that are appropriate to answering this question. All experts will write down the step and their thinking about the step, then share it with the group. Then, all experts will go on to the next step, etc. At each step all experts will score their peers response between 1 and 5, 1 meaning it is highly unlikely, and 5 meaning it is highly likely. If any expert is judged to be wrong at any point then they leave. After all experts have provided their analysis, you then analyze all 3 analyses and provide either the consensus solution or your best guess solution. The question is..."

## Application and Best Practices

* **Complex Reasoning:** ToT is particularly effective for questions that require multi-step reasoning and where the initial line of thought can be misleading.
* **Adaptability:** The number of "experts" and the specific rules of interaction can be modified to suit the complexity of the task.
* **Clarity:** The structured output of ToT prompts makes it easier to follow the LLM's reasoning process and identify where and why it made certain decisions.

## 4. References

* [Tree of Thought Examples](../knowledge/example.ToT-Prompting.md)

</tot_techniques>