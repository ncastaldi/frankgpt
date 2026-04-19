# Frank v6 - Modular AI Assistant Framework

**Version**: 6.0  
**Architecture**: Skills-Centric Modular System  
**Philosophy**: Pick up and go - zero environment coupling, maximum portability

---

## 🚀 Quick Start

### Option 1: Core Only (Universal Assistant)

Load just the core for a friendly, mentoring assistant with universal capabilities:

```
Load: v6/Frank.core.agent.md
```

**You get**:
- Upbeat, friendly, mentoring personality
- 7 universal personas (Project Manager, Information Architect, Technical Writer, QA Analyst, Editor, Communications Lead, Business Analyst)
- 8 base commands: `/quickstart`, `/create`, `/review`, `/refactor`, `/document`, `/communicate`, `/consult`, `/help`

### Option 2: Core + Skills (With Reasoning Techniques)

Add advanced reasoning techniques for complex problem-solving:

```
Load: 
- v6/Frank.core.agent.md
- v6/skills/style.cot.instructions.md (Chain-of-Thought)
- v6/skills/style.tot.instructions.md (Tree-of-Thought)
- v6/skills/style.craft.instructions.md (C.R.A.F.T. framework)
```

**You get**: Core + step-by-step reasoning, multi-path exploration, structured prompt creation

### Option 3: Core + Specialty (Domain Expert)

Load a specialty module for domain-specific expertise:

**Frank for DevOps**:
```
Load:
- v6/Frank.core.agent.md
- v6/specialties/specialty.devops.instructions.md
Commands: /docker, /ansible, /compose, /traefik
```

**Frank for Data Analysis**:
```
Load:
- v6/Frank.core.agent.md
- v6/specialties/specialty.data-analysis.instructions.md
Commands: /analyze, /query, /visualize, /model, /clean
```

**Frank for IT Service Management**:
```
Load:
- v6/Frank.core.agent.md
- v6/specialties/specialty.itil.instructions.md
Commands: /ticket, /rca, /sop, /itil
```

**See**: [All Available Specialties](#available-specialties)

### Option 4: Multi-Specialty Composition

Combine multiple specialties for cross-domain expertise:

```
Load:
- v6/Frank.core.agent.md
- v6/specialties/specialty.devops.instructions.md
- v6/specialties/specialty.data-analysis.instructions.md
- v6/skills/style.advanced-reasoning.instructions.md
```

**You get**: DevOps + Data Science hybrid with advanced reasoning

---

## 📁 Architecture Overview

Frank v6 uses a **3-layer modular architecture**:

```
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

---

## 🎯 Available Specialties

### DevOps & Site Reliability Engineering
**File**: `specialty.devops.instructions.md`  
**Commands**: `/docker`, `/ansible`, `/compose`, `/traefik`  
**Expertise**: Container orchestration, infrastructure automation, Traefik routing, safe deployment strategies  
**Use When**: Troubleshooting Docker/Compose, writing Ansible playbooks, designing IaC solutions

### Prompt Engineering & LLM Optimization
**File**: `specialty.prompt-engineering.instructions.md`  
**Commands**: `/optimize`, `/craft`, `/reason`, `/evaluate`, `/patterns`  
**Expertise**: LLM optimization, C.R.A.F.T. framework mastery, reasoning technique integration  
**Use When**: Creating production prompts, optimizing existing prompts, integrating CoT/ToT/RAG

### Data Analysis & Visualization
**File**: `specialty.data-analysis.instructions.md`  
**Commands**: `/analyze`, `/query`, `/visualize`, `/model`, `/clean`  
**Expertise**: SQL, Python (Pandas, Matplotlib, Seaborn), statistical modeling, SCoT methodology  
**Use When**: Analyzing datasets, writing queries, creating visualizations, statistical analysis

### Modern Endpoint Management
**File**: `specialty.sccm.instructions.md`  
**Commands**: `/sccm`, `/intune`, `/comanage`, `/package`, `/troubleshoot`  
**Expertise**: SCCM/Intune, Co-management, compliance policies, Win32 app packaging  
**Use When**: Managing endpoints, deploying apps, configuring compliance, migrating to Intune

### IT Service Management (ITIL v4)
**File**: `specialty.itil.instructions.md`  
**Commands**: `/ticket`, `/rca`, `/sop`, `/itil`  
**Expertise**: Incident Management, Problem Management, Knowledge Management, ITIL v4 framework  
**Use When**: Resolving incidents, conducting RCAs, creating IT documentation, applying ITIL principles

---

## 🛠️ VS Code Integration

### Method 1: Workspace Instructions (Recommended)

1. Open VS Code Settings (Ctrl+,)
2. Search for "GitHub Copilot Chat: Instructions File"
3. Set to: `${workspaceFolder}/v6/copilot-instructions.md`
4. Reload VS Code

The copilot-instructions.md file pre-configures common loading patterns.

### Method 2: Manual Loading

In any Copilot Chat, use `#file` to reference:

```
@workspace Load #file:v6/Frank.core.agent.md and #file:v6/specialties/specialty.devops.instructions.md

Now help me troubleshoot this Docker Compose issue...
```

### Method 3: Direct File Reference

Copy the content you need directly into your chat context, or use VS Code's "Add to Chat" feature on the files.

**See**: [copilot-instructions.md](copilot-instructions.md) for pre-configured patterns

---

## 💡 Usage Examples

### Example 1: Creating a Technical Document

```
User: "I need to create API documentation for our REST service"

Frank (Core): "I'll guide you through creating comprehensive API documentation.
Let me use the Technical Writer persona and Documentation workflow..."

[Walks through structure, audience, content gathering, drafting]
```

### Example 2: DevOps Troubleshooting

```
User: "My Docker Compose stack won't start, getting network errors"

Frank (Core + DevOps): "I'll help diagnose this. Triggering DevOps SRE persona.
Let me gather diagnostics..."

[Requests specific outputs, analyzes logs, proposes minimal fix with verification steps]
```

### Example 3: Data Analysis with Reasoning

```
User: "Analyze Q1 sales data and identify trends"

Frank (Core + Data Analysis + CoT): "I'll analyze this using Structured Chain-of-Thought.

## 1. Clarify & Define
Your objective: Identify sales trends in Q1 data
Key sources: sales table, customers table
Success criteria: Actionable insights with visualizations

## 2. Repository Check
[Reviews existing scripts]

## 3. Plan & Methodology
[Outlines analytical steps]
..."
```

### Example 4: Root Cause Analysis with ITIL

```
User: "Email server has been slow all week, need to find root cause"

Frank (Core + ITIL): "I'll conduct a root cause analysis using ITIL Problem Management.
Triggering Problem Manager persona with Tree-of-Thought analysis..."

[Gathers timeline, generates hypotheses, evaluates evidence, documents RCA]
```

### Example 5: Multi-Specialty Composition

```
Load: Core + DevOps + Data Analysis

User: "Help me analyze Docker container metrics and visualize resource usage"

Frank: "This combines my DevOps and Data Analysis expertise.
I'll use Docker diagnostic commands to gather metrics, then Python/Pandas for analysis..."

[Bridges both domains seamlessly]
```

---

## 🎨 Creating Custom Specialties

Want to add your own domain expertise? Use the template:

1. **Copy the template**:
   ```bash
   cp v6/specialties/specialty.TEMPLATE.instructions.md v6/specialties/specialty.legal.instructions.md
   ```

2. **Customize sections**:
   - Replace placeholder text with your domain
   - Define 2-5 expert personas
   - Create 3-7 slash commands
   - Document 2-5 key workflows
   - Reference relevant skills

3. **Test integration**:
   ```
   Load: v6/Frank.core.agent.md + v6/specialties/specialty.legal.instructions.md
   ```

4. **Share** (optional):
   Your custom specialty can be shared with others - just distribute the file!

**See**: [specialty.TEMPLATE.instructions.md](specialties/specialty.TEMPLATE.instructions.md) for detailed guidance

---

## 📚 Documentation

- **[ARCHITECTURE.md](ARCHITECTURE.md)**: Comprehensive architecture guide (500+ lines)
  - Design principles
  - File organization
  - Loading patterns
  - Multi-specialty composition
  - Migration from v4/v5
  - Troubleshooting
  - Version history

- **[copilot-instructions.md](copilot-instructions.md)**: VS Code integration guide
  - Pre-configured loading patterns
  - Quick start templates
  - Multi-specialty examples

- **Individual files**: Each skill and specialty has inline documentation

---

## 🔄 Migration from Earlier Versions

### From v5 (FrankGPT.consolidated-instructions.md)

**v5 approach**: Single monolithic file with all capabilities  
**v6 approach**: Modular - load only what you need

**Migration path**:
1. **Core functionality**: Use `Frank.core.agent.md` (replaces universal personas)
2. **IT operations**: Use `specialty.itil.instructions.md` (replaces ITIL/incident workflows)
3. **DevOps**: Use `specialty.devops.instructions.md` (replaces Docker/Ansible sections)
4. **Prompting**: Use `specialty.prompt-engineering.instructions.md` (replaces prompt optimization)

**Benefit**: Smaller context window, faster loading, compose only what you need

### From v4 (Multiple agents/ files)

**v4 approach**: Separate agent files (Data Analyst, SCCM Tutor, etc.)  
**v6 approach**: Specialties that compose with shared core

**Migration path**:
- `agents/Data Analyst.agent.md` → `specialty.data-analysis.instructions.md`
- `agents/SCCM Tutor.agent.md` → `specialty.sccm.instructions.md`
- Custom agents → Create using `specialty.TEMPLATE.instructions.md`

**Benefit**: Shared core personality, multi-specialty composition, portable structure

---

## 🏗️ Design Principles

### 1. Portability First
- **Zero environment coupling**: No hardcoded paths, no system-specific references
- **Relative paths only**: All cross-references use `../skills/`, `../knowledge/` patterns
- **"Pick up and go"**: Copy the v6/ folder to any system and it works

### 2. Modularity
- **Core is self-sufficient**: Works alone without dependencies
- **Skills enhance**: Add reasoning techniques as needed
- **Specialties compose**: Load multiple domains without conflicts
- **Knowledge is reference**: Shared examples available to all layers

### 3. Versioning
- **All files tagged**: `version: 6.0` in frontmatter
- **Compatibility tracked**: `compatibleWith: Frank.core v6+`
- **Forward compatible**: v6+ notation allows future evolution

### 4. Multi-Specialty Support
- **No command conflicts**: Each specialty uses domain-specific commands
- **Shared skills**: Multiple specialties can reference same CoT/ToT/RAG modules
- **Conflict resolution**: When overlaps exist, documentation explains disambiguation

---

## 📊 Project Structure

```
v6/
├── README.md                          ← You are here
├── ARCHITECTURE.md                    ← Detailed architecture guide
├── copilot-instructions.md            ← VS Code integration
├── Frank.core.agent.md                ← Core personality (REQUIRED)
├── skills/                            ← Reasoning techniques (OPTIONAL)
│   ├── style.advanced-reasoning.instructions.md
│   ├── style.cot.instructions.md
│   ├── style.craft.instructions.md
│   ├── style.markdown.instructions.md
│   ├── style.mermaid.instructions.md
│   ├── style.rag.instructions.md
│   └── style.tot.instructions.md
├── specialties/                       ← Domain expertise (OPTIONAL)
│   ├── specialty.data-analysis.instructions.md
│   ├── specialty.devops.instructions.md
│   ├── specialty.itil.instructions.md
│   ├── specialty.prompt-engineering.instructions.md
│   ├── specialty.sccm.instructions.md
│   └── specialty.TEMPLATE.instructions.md
└── knowledge/                         ← Reference examples
    ├── example.CoT-Prompting.md
    ├── example.ITILv4.instructions.md
    ├── example.Meta-Prompting.md
    ├── example.RAG-Token.md
    ├── example.ReAct.md
    └── example.ToT-Prompting.md
```

**Total**: 22 files, ~6,200 lines, fully modular

---

## 🔧 Troubleshooting

### Frank isn't responding to specialty commands

**Check**: Are you loading both Frank.core AND the specialty?
```
# Correct:
Load: Frank.core.agent.md + specialty.devops.instructions.md

# Incorrect (core alone doesn't have /docker):
Load: Frank.core.agent.md
```

### Commands from multiple specialties conflict

**Check**: Do the specialties actually conflict, or are they complementary?
- `/docker` (DevOps) and `/analyze` (Data Analysis) don't conflict
- If true conflict exists, specify domain: "Use DevOps /troubleshoot" vs "Use Data Analysis workflow"

### Skills aren't being applied

**Check**: Skills are passive references - specialties or core must explicitly invoke them
- Frank.core references C.R.A.F.T. framework for prompt evaluation
- specialty.prompt-engineering deeply integrates all skills
- Loading skills alone without core/specialty won't trigger behaviors

### Cross-references not working

**Check**: All paths are relative from v6/ root
- Correct: `../skills/style.cot.instructions.md`
- Incorrect: `/skills/style.cot.instructions.md` or absolute paths

---

## 🚀 Roadmap

### v6.1 (Future)
- [ ] Additional specialties: Security, Cloud Architecture, Database Design
- [ ] Enhanced multi-specialty conflict resolution
- [ ] Knowledge base expansion with more examples

### v7.0 (Future)
- [ ] Dynamic specialty loading based on conversation context
- [ ] Auto-detection of required skills
- [ ] Specialty versioning and compatibility matrix

---

## 🤝 Contributing

Want to contribute a specialty or improve existing modules?

1. **For new specialties**: Use `specialty.TEMPLATE.instructions.md` as your starting point
2. **For improvements**: Ensure changes maintain v6 compatibility
3. **For bug fixes**: Update version metadata if behavior changes
4. **Share**: Custom specialties can be shared as standalone files

**Principles**:
- Maintain portability (no environment coupling)
- Use relative paths
- Document in frontmatter
- Include examples in workflows
- Test with Frank.core independently

---

## 📜 Version History

### v6.0 (April 2026)
**Major refactor**: Monolithic → Modular architecture

**Changes**:
- ✅ Created 3-layer system (Core → Skills → Specialties)
- ✅ Extracted 5 domain specialties from v5 monolith
- ✅ Added specialty.TEMPLATE for custom domains
- ✅ Zero environment coupling achieved
- ✅ Multi-specialty composition support
- ✅ Full documentation (ARCHITECTURE.md, README.md)

**Migration**: v4/v5 → v6 (see Migration section above)

### v5.0 (2024-2025)
- Single consolidated file: FrankGPT.consolidated-instructions.md
- Monolithic approach with all capabilities included
- IT operations focus with ITIL integration

### v4.0 (2023-2024)
- Multiple agent files in agents/ folder
- Separate: Data Analyst, SCCM Tutor, custom agents
- Core instructions in instructions/ folder

---

## 📞 Support

**Documentation**:
- Quick start: This file (README.md)
- Architecture deep-dive: [ARCHITECTURE.md](ARCHITECTURE.md)
- VS Code setup: [copilot-instructions.md](copilot-instructions.md)
- Template guide: [specialty.TEMPLATE.instructions.md](specialties/specialty.TEMPLATE.instructions.md)

**Need help**?
- Review [ARCHITECTURE.md](ARCHITECTURE.md) for detailed patterns
- Check individual specialty files for domain-specific guidance
- Load `specialty.prompt-engineering.instructions.md` to optimize your own prompts

---

## 📄 License

This is a personal AI assistant framework. Use, modify, and extend as needed for your projects.

---

**Frank v6**: Modular. Portable. Composable. Pick up and go. 🚀
