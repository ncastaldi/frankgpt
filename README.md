# Frank Meadows v6 - Modular AI Assistant Framework

**Version**: 6.0  
**Architecture**: Skills-Centric Modular System  
**Philosophy**: Pick up and go - zero environment coupling, maximum portability

---

## 🚀 Quick Start

### Option 1: Core Only (Universal Assistant)

Load just the core for a friendly, mentoring assistant with universal capabilities:

```plaintext
Load: v6/Frank.core.agent.md
```

**You get**:

- Upbeat, friendly, mentoring personality
- 7 universal personas (Project Manager, Information Architect, Technical Writer, QA Analyst, Editor, Communications Lead, Business Analyst)
- 8 base commands: `/quickstart`, `/create`, `/review`, `/refactor`, `/document`, `/communicate`, `/consult`, `/help`

### Option 2: Core + Skills (With Reasoning Techniques)

Add advanced reasoning techniques for complex problem-solving:

```plaintext
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
```plaintext
Load:
- v6/Frank.core.agent.md
- v6/specialties/specialty.devops.instructions.md
Commands: /docker, /ansible, /compose, /traefik
```

**Frank for Data Analysis**:
```plaintext
Load:
- v6/Frank.core.agent.md
- v6/specialties/specialty.data-analysis.instructions.md
Commands: /analyze, /query, /visualize, /model, /clean
```

**Frank for IT Service Management**:
```plaintext
Load:
- v6/Frank.core.agent.md
- v6/specialties/specialty.itil.instructions.md
Commands: /ticket, /rca, /sop, /itil
```

### Option 4: Multi-Specialty Composition

Combine multiple specialties for cross-domain expertise:

```plaintext
Load:
- v6/Frank.core.agent.md
- v6/specialties/specialty.devops.instructions.md
- v6/specialties/specialty.data-analysis.instructions.md
- v6/skills/style.advanced-reasoning.instructions.md
```

**You get**: DevOps + Data Science hybrid with advanced reasoning

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

```plaintext
@workspace Load #file:v6/Frank.core.agent.md and #file:v6/specialties/specialty.devops.instructions.md

Now help me troubleshoot this Docker Compose issue...
```

### Method 3: Direct File Reference

Copy the content you need directly into your LLM chat of choice.

**See**: [copilot-instructions.md](copilot-instructions.md) for pre-configured patterns

---

## 📄 License

This is a personal AI assistant framework. Use, modify, and extend as needed for your projects.
