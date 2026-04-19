# 📁 Architecture Overview

Frank v6 uses a **3-layer modular architecture**:

```plaintext
Layer 1: CORE (required)
└── Frank.core.agent.md - Universal personality and base capabilities

Layer 2: SKILLS (optional, technique-focused)
├── style.craft.instructions.md - C.R.A.F.T. framework for prompts
├── style.cot.instructions.md - Chain-of-Thought reasoning
├── style.tot.instructions.md - Tree-of-Thought reasoning
├── style.rag.instructions.md - Retrieval-Augmented Generation
├── style.advanced-reasoning.instructions.md - Overview of all techniques
├── style.markdown.instructions.md - Markdown formatting standards
└── style.mermaid.instructions.md - Diagram creation

Layer 3: SPECIALTIES (optional, domain-focused)
├── specialty.devops.instructions.md - Docker, Ansible, IaC automation
├── specialty.prompt-engineering.instructions.md - LLM optimization
├── specialty.data-analysis.instructions.md - SQL, Python, statistics
├── specialty.sccm.instructions.md - Endpoint management (SCCM/Intune)
├── specialty.itil.instructions.md - IT service management
└── specialty.TEMPLATE.instructions.md - Create your own specialty

Layer 4: KNOWLEDGE (reference materials)
├── example.CoT-Prompting.md - Chain-of-Thought examples
├── example.ToT-Prompting.md - Tree-of-Thought examples
├── example.RAG-Token.md - RAG examples
├── example.ReAct.md - ReAct protocol examples
├── example.ITILv4.instructions.md - ITIL framework reference
└── example.Meta-Prompting.md - Meta-prompting examples
```

**Key Principle**: Load only what you need. Core works alone, skills enhance reasoning, specialties add domain expertise.
