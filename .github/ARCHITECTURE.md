---
title: "Frank v6 Architecture Guide"
description: "Complete guide to Frank's modular skills-centric architecture"
version: "6.0"
lastUpdated: "2026-04-19"
---

# Frank v6 Architecture Guide

## Overview

Frank v6 is a **modular, skills-centric AI assistant** built on three distinct layers that work together to provide flexible, specialized assistance. The architecture is designed for **"pick up and go" portability** - copy the v6/ folder anywhere and you're ready to work.

```
┌─────────────────────────────────────────┐
│   Frank.core (Personality + Base)       │  ← Always loaded
│   - Upbeat, friendly, mentoring         │
│   - Core commands & workflows           │
│   - Universal personas                  │
└─────────────────────────────────────────┘
                ↓ references
┌─────────────────────────────────────────┐
│   Skills (Reasoning Techniques)         │  ← Include as needed
│   - CoT, ToT, RAG, CRAFT                │
│   - Markdown, Mermaid                   │
│   - Advanced Reasoning                  │
└─────────────────────────────────────────┘
                ↓ loads as needed
┌─────────────────────────────────────────┐
│   Specialties (Domain Expertise)        │  ← Plugin architecture
│   - DevOps, Data Analysis, ITIL         │
│   - Prompt Engineering, SCCM            │
│   - Custom user specialties             │
└─────────────────────────────────────────┘
                ↓ references
┌─────────────────────────────────────────┐
│   Knowledge (Examples & References)     │  ← Shared examples
│   - CoT, ToT, RAG examples              │
│   - ITIL, ReAct, Meta-Prompting         │
└─────────────────────────────────────────┘
```

## Design Principles

### 1. Portability First
**No environment-specific paths or configuration**. Frank v6 files contain zero hardcoded paths, repo structures, or project-specific conventions. Copy the v6/ folder to any workspace and it works immediately.

**What was removed from v5**:
- ❌ `/Volume1/appdata/` paths
- ❌ `.github/` folder rules
- ❌ `compose-stack-standard.md` references
- ❌ Project-specific documentation filing requirements

### 2. Skills-Centric Modularity
Each **skill** is a self-contained technique that Frank can reference. Each **specialty** is a domain expert that can be loaded independently or combined with others.

**Benefits**:
- ✅ Load only what you need
- ✅ Mix and match specialties
- ✅ Update one module without touching others
- ✅ Create custom specialties without modifying core

### 3. Composition Over Monolith
Instead of one giant "consolidated" file, Frank v6 uses **composition**:

```
Frank for DevOps = core + craft + devops
Frank for Data = core + craft + markdown + data-analysis
Frank for IT Ops = core + craft + itil
Frank Full Stack = core + craft + devops + data-analysis + itil
```

### 4. Version Compatibility
All core and specialty files declare version metadata:

```yaml
version: "6.0"
compatibleWith: "Frank.core v6+" # or "specialty.*.instructions.md v6+"
```

This enables future version management and compatibility checking.

## File Organization

```
v6/
├── Frank.core.agent.md              # Core personality (REQUIRED)
├── copilot-instructions.md          # VS Code integration guide
├── ARCHITECTURE.md                  # This file
│
├── skills/                          # Reasoning techniques (INCLUDE as needed)
│   ├── style.advanced-reasoning.instructions.md
│   ├── style.cot.instructions.md
│   ├── style.craft.instructions.md
│   ├── style.markdown.instructions.md
│   ├── style.mermaid.instructions.md
│   ├── style.rag.instructions.md
│   └── style.tot.instructions.md
│
├── specialties/                     # Domain experts (LOAD as needed)
│   ├── specialty.devops.instructions.md        ✅
│   ├── specialty.prompt-engineering.instructions.md  ✅
│   ├── specialty.data-analysis.instructions.md ✅
│   ├── specialty.sccm.instructions.md          ✅
│   ├── specialty.itil.instructions.md          ✅
│   └── specialty.TEMPLATE.instructions.md      ✅
│
└── knowledge/                       # Examples & references
    ├── example.CoT-Prompting.md
    ├── example.ITILv4.instructions.md
    ├── example.Meta-Prompting.md
    ├── example.RAG-Token.md
    ├── example.ReAct.md
    └── example.ToT-Prompting.md
```

**Legend**:
- `✅` - Available now

## The Three Layers Explained

### Layer 1: Frank.core (Required)

**File**: `Frank.core.agent.md`

**What it provides**:
- Core personality: upbeat, friendly, mentoring approach
- Universal personas: Project Manager, Technical Writer, QA Analyst, Editor, etc.
- Base commands: `/quickstart`, `/create`, `/review`, `/refactor`, `/document`, `/communicate`, `/consult`, `/help`
- Generalized workflows: Content Creation, Content Analysis & Refinement
- Error handling protocols
- Integration points for skills and specialties

**When to use**: Always. This is Frank's foundation.

**What it doesn't include**:
- Domain-specific expertise (that's in specialties)
- Detailed reasoning techniques (that's in skills)
- Environment-specific configuration

### Layer 2: Skills (Include as Needed)

**Location**: `skills/`

**What they provide**:
Each skill is a **technique** or **methodology** that Frank can reference:

| Skill | Purpose | When Frank Uses It |
|-------|---------|-------------------|
| `style.craft.instructions.md` | C.R.A.F.T. framework (Context, Role, Action, Format, Tone) | Creating or evaluating prompts |
| `style.advanced-reasoning.instructions.md` | Overview of CoT, ToT, PoT, PAL, CoVe | Choosing reasoning approach |
| `style.cot.instructions.md` | Chain-of-Thought step-by-step reasoning | Sequential problem-solving |
| `style.tot.instructions.md` | Tree-of-Thought multi-path reasoning | Complex decision spaces |
| `style.rag.instructions.md` | Retrieval-Augmented Generation | Grounding in external knowledge |
| `style.markdown.instructions.md` | Markdown formatting standards | All Markdown output |
| `style.mermaid.instructions.md` | Mermaid diagram creation | Visual diagrams |

**When to include**:
- **Minimum**: `style.craft.instructions.md` for quality prompting
- **Recommended**: `craft` + `advanced-reasoning` + `markdown` for general use
- **Specialized**: Add `cot`, `tot`, `rag` when working on complex reasoning tasks

**How Frank uses them**:
Frank references these files when:
- Analyzing prompt quality (uses CRAFT framework)
- Choosing reasoning strategies (references advanced-reasoning)
- Formatting output (follows markdown guide)
- Creating complex prompts (may suggest ToT or RAG)

### Layer 3: Specialties (Load for Domain Expertise)

**Location**: `specialties/`

**What they provide**:
Each specialty adds:
- **Domain-specific personas** (e.g., DevOps SRE, Data Analyst)
- **New commands** (e.g., `/docker`, `/ticket`, `/analyze`)
- **Specialized workflows** (e.g., incident management, container troubleshooting)
- **Domain knowledge** (e.g., ITIL v4, Docker Compose patterns)

**Available Specialties**:

#### ✅ specialty.itil.instructions.md
**Domain**: IT Service Management & Operations

**Adds**:
- Personas: Senior Support Analyst, Problem Manager, Service Desk Lead
- Commands: `/ticket`, `/rca`, `/sop`, `/itil`
- Workflows: Incident Management (ReAct), Problem Management (ToT), Knowledge Management
- Framework: ITIL v4 Service Value System with 7 Guiding Principles

**Use when**: Managing IT incidents, performing root cause analysis, creating IT documentation

#### specialty.devops.instructions.md ✅
**Domain**: DevOps, Docker, Compose, Ansible, IaC

**Provides**:
- Personas: DevOps SRE (Docker & Compose), DevOps SRE (Ansible & IaC)
- Commands: `/docker`, `/ansible`, `/compose`, `/traefik`
- Workflows: Container troubleshooting, Compose debugging, Ansible automation, safe deployment strategies

**Use when**: Working with Docker, Compose, Swarm, Traefik, Ansible, infrastructure automation

#### specialty.prompt-engineering.instructions.md ✅
**Domain**: Advanced Prompt Optimization & Engineering

**Provides**:
- Personas: Senior Prompt Engineer
- Commands: `/optimize`, `/craft`, `/reason`, `/evaluate`, `/patterns`
- Workflows: Prompt creation (C.R.A.F.T.), optimization, reasoning integration (CoT/ToT/RAG), evaluation rubric

**Use when**: Creating production prompts, optimizing LLM interactions, integrating advanced reasoning

#### specialty.data-analysis.instructions.md ✅
**Domain**: Data Analysis, SQL, Python, Statistics

**Provides**:
- Personas: DataAnalystX (SQL, Python, statistical modeling expert)
- Commands: `/analyze`, `/query`, `/visualize`, `/model`, `/clean`
- Workflows: Structured Chain-of-Thought (SCoT) 6-phase methodology, visualization guide, statistical analysis

**Use when**: Analyzing datasets, writing SQL queries, creating visualizations, statistical modeling

#### specialty.sccm.instructions.md ✅
**Domain**: SCCM, Intune, Endpoint Management

**Provides**:
- Personas: Senior Infrastructure Engineer, Microsoft MVP
- Commands: `/sccm`, `/intune`, `/comanage`, `/package`, `/troubleshoot`
- Workflows: Win32 app deployment, Co-management configuration, compliance policies, architectural guidance

**Use when**: Managing Windows endpoints, SCCM/Intune deployments, Co-management, application packaging

### Layer 4: Knowledge (Shared Examples)

**Location**: `knowledge/`

**What it provides**:
Concrete examples and reference materials that skills and specialties reference:

- `example.CoT-Prompting.md` - Step-by-step reasoning examples
- `example.ToT-Prompting.md` - Mini crosswords with backtracking
- `example.RAG-Token.md` - RAG implementation example
- `example.ReAct.md` - Thought-Act-Observation loops
- `example.ITILv4.instructions.md` - ITIL v4 framework reference
- `example.Meta-Prompting.md` - Meta-prompting patterns

**When to reference**: These are educational materials. Skills point to them for detailed examples.

## Usage Patterns

### Pattern 1: General Assistant (Minimal)

**Load**:
```
v6/Frank.core.agent.md
```

**Capabilities**:
- All base commands
- Content creation and analysis
- General business consulting
- Basic Markdown output

**Best for**: Quick questions, general writing, simple documentation

### Pattern 2: Content Creator (Recommended)

**Load**:
```
v6/Frank.core.agent.md
v6/skills/style.craft.instructions.md
v6/skills/style.markdown.instructions.md
```

**Capabilities**:
- CRAFT-based prompt creation
- High-quality documentation
- Proper Markdown formatting

**Best for**: Creating prompts, documentation, guides, SOPs

### Pattern 3: IT Operations Specialist

**Load**:
```
v6/Frank.core.agent.md
v6/skills/style.craft.instructions.md
v6/specialties/specialty.itil.instructions.md
```

**Capabilities**:
- All core commands
- IT-specific commands: `/ticket`, `/rca`, `/sop`
- ITIL v4 workflows
- Incident/Problem/Knowledge Management

**Best for**: IT support, troubleshooting, IT documentation

### Pattern 4: DevOps Engineer ✅

**Load**:
```
v6/Frank.core.agent.md
v6/skills/style.craft.instructions.md
v6/specialties/specialty.devops.instructions.md
```

**Capabilities**:
- All core commands
- DevOps commands: `/docker`, `/ansible`, `/compose`, `/traefik`
- Container and IaC troubleshooting

**Best for**: Docker, Compose, Swarm, Traefik, Ansible, infrastructure work

### Pattern 5: Multi-Specialty Expert

**Load**:
```
v6/Frank.core.agent.md
v6/skills/style.craft.instructions.md
v6/skills/style.advanced-reasoning.instructions.md
v6/specialties/specialty.devops.instructions.md
v6/specialties/specialty.itil.instructions.md
```

**Capabilities**:
- All core commands
- Combined specialty commands
- Both DevOps AND IT Ops expertise

**Best for**: Complex environments requiring multiple domains

**Conflict Resolution**: If multiple specialties define the same command, Frank will:
1. Acknowledge the overlap
2. Ask which specialty's implementation you prefer
3. Proceed with clarified approach

## Creating Custom Specialties

### Step 1: Copy the Template ✅

```bash
cp v6/specialties/specialty.TEMPLATE.instructions.md v6/specialties/specialty.myDomain.instructions.md
```

### Step 2: Define Your Specialty

Edit the file with:

```yaml
---
description: "Your specialty description"
version: "6.0"
compatibleWith: "Frank.core v6+"
specialty: "Your Domain Name"
---
```

### Step 3: Add Your Domain Expertise

**Required sections**:
1. **[SPECIALTY OVERVIEW]** - What does this add to Frank?
2. **[WHEN TO USE THIS SPECIALTY]** - Use cases
3. **[PERSONAS ADDED]** - Domain expert personas
4. **[COMMANDS ADDED]** - New commands with syntax
5. **[WORKFLOWS]** - Step-by-step domain workflows
6. **[INTEGRATION WITH FRANK CORE]** - How it enhances core
7. **[FORMATTING & TONE]** - Domain-specific communication style
8. **[REFERENCES]** - Links to skills and knowledge files

### Step 4: Load It

Include your specialty in VS Code configuration:

```
Include: v6/specialties/specialty.myDomain.instructions.md
```

### Best Practices for Custom Specialties

**DO**:
- ✅ Focus on a specific domain (not "everything DevOps", but "Docker & Compose")
- ✅ Define clear triggering keywords for auto-routing
- ✅ Provide concrete workflow steps with examples
- ✅ Reference existing skills (don't duplicate CRAFT or CoT)
- ✅ Include version metadata for compatibility

**DON'T**:
- ❌ Include environment-specific paths or credentials
- ❌ Duplicate content from Frank.core or skills
- ❌ Create overlapping commands with existing specialties (without noting conflicts)
- ❌ Assume knowledge - reference knowledge/ examples explicitly

## VS Code Integration

### Option 1: Workspace Settings

Create or edit `.vscode/settings.json`:

```json
{
  "github.copilot.chat.codeGeneration.instructions": [
    {"file": "v6/Frank.core.agent.md"},
    {"file": "v6/skills/style.craft.instructions.md"},
    {"file": "v6/specialties/specialty.itil.instructions.md"}
  ]
}
```

### Option 2: Global Copilot Instructions

Create or edit `.github/copilot-instructions.md`:

```markdown
Include: v6/Frank.core.agent.md
Include: v6/skills/style.craft.instructions.md
Include: v6/specialties/specialty.itil.instructions.md
```

### Option 3: Use the Provided copilot-instructions.md

The `v6/copilot-instructions.md` file contains pre-configured loading patterns. Copy it to your `.github/` folder and customize as needed.

## Migration from v4/v5

### What Changed from v5 to v6

**Architecture**:
- v5: Monolithic consolidated file (FrankGPT.consolidated-instructions.md)
- v6: Modular composition (core + skills + specialties)

**Portability**:
- v5: Contained repo-specific paths and standards
- v6: Fully portable, zero environment coupling

**Specialization**:
- v5: All personas in one file (couldn't load selectively)
- v6: Load only the specialties you need

**Commands**:
- v5: `//ticket`, `//sop`, `//rca`, `//persona`, etc.
- v6: `/ticket`, `/sop`, `/rca` (specialty-specific), plus new `/quickstart`, `/create`, etc.

### Migration Steps

1. **Back up your v5 configuration**
   ```bash
   cp -r agents/ agents.backup/
   cp copilot-instructions.md copilot-instructions.v5.md
   ```

2. **Copy v6 to your workspace**
   ```bash
   # v6/ folder already exists in frankgpt repo
   # Just update your copilot configuration to point to it
   ```

3. **Update VS Code configuration**
   - Remove references to old files (agents/FrankGPT.consolidated-instructions.md)
   - Add references to v6/Frank.core.agent.md and desired specialties

4. **Map your v5 usage to v6 patterns**
   
   | v5 Pattern | v6 Equivalent |
   |------------|---------------|
   | Load consolidated file | Load Frank.core + craft + specialties |
   | `//ticket` command | Load specialty.itil → `/ticket` |
   | `//docker` command | Load specialty.devops → `/docker` ✅ |
   | ITIL modes | Load specialty.itil |
   | Meta-prompting | Load skills/style.craft |

5. **Test core functionality**
   ```
   - Try /quickstart
   - Try /review with a document
   - Try specialty commands if loaded
   ```

### What to Do with Old Files

| File/Folder | Recommendation |
|-------------|----------------|
| `agents/FrankGPT.consolidated-instructions.md` | Archive with note "Superseded by v6" |
| `agents/Data Analyst.agent.md` | Keep for reference (see v6/specialties/specialty.data-analysis.instructions.md) |
| `agents/SCCM Tutor.agent.md` | Keep for reference (see v6/specialties/specialty.sccm.instructions.md) |
| `_Frank_/markdown/*.md` | Source files - can archive after v6 verified |
| `_Frank_/docx/` | Archive or delete (export artifacts) |
| `instructions/core.instructions.md` | Archive with note "v4 file, replaced by v6" |
| `instructions/style.markdown.instructions.md` | Delete (duplicate, now in v6/skills/) |
| `knowledge/*.md` | ✅ Copied to v6/knowledge/ - can keep originals as backup |
| `prompts/*.md` | ✅ Keep at repo root (templates, not Frank core files) |
| See LEGACY.md | Complete migration and cleanup guide |

## Troubleshooting

### "Frank doesn't recognize a command"

**Problem**: Command like `/docker` doesn't work

**Solution**:
1. Check which files are loaded in your VS Code configuration
2. Verify the specialty providing that command is included (e.g., specialty.devops.instructions.md for `/docker`)
3. Confirm you're loading both Frank.core AND the specialty

### "Cross-references are broken"

**Problem**: Links to knowledge/ or skills/ files return 404

**Solution**:
1. Ensure you copied the entire v6/ folder structure
2. Verify relative paths start from v6/ root
3. Check that knowledge/ and skills/ folders exist

### "Frank has different personality than expected"

**Problem**: Responses don't match the upbeat, mentoring style

**Solution**:
1. Ensure v6/Frank.core.agent.md is loaded (required)
2. Check that you're not mixing v5 and v6 files
3. Verify specialty files aren't overriding core personality

### "Commands from multiple specialties conflict"

**Problem**: Two specialties define the same command differently

**Expected Behavior**: Frank will:
1. Acknowledge the overlap: *"Both specialty.devops and specialty.custom define /analyze"*
2. Ask which implementation you prefer
3. Proceed with clarified approach

**Prevention**: When creating custom specialties, check existing commands and choose unique names.

## Version History

### v6.0 (April 2026) - Initial Modular Release
- ✅ Modular architecture (core + skills + specialties)
- ✅ Portable design (zero environment coupling)
- ✅ VS Code integration
- ✅ Frank.core with 7 universal personas
- ✅ 7 skill modules (CRAFT, CoT, ToT, RAG, Markdown, Mermaid, Advanced Reasoning)
- ✅ specialty.itil for IT Service Management
- ✅ Phase 3 complete: 5 additional specialties (devops, prompt-engineering, data-analysis, sccm, TEMPLATE)
- ✅ Phase 5 complete: README.md, LEGACY.md, and documentation finalization

### v5.0 (Pre-modular)
- Single consolidated file (FrankGPT.consolidated-instructions.md)
- ITIL operational modes
- Repo-specific standards enforcement

### v4.0 (Legacy)
- Initial FrankGPT core logic engine
- instructions/core.instructions.md as primary file

## Roadmap

### Completed ✅
- ✅ Phase 1-2: Core architecture, skills, ITIL specialty
- ✅ Phase 3: Five domain specialties (devops, prompt-engineering, data-analysis, sccm, TEMPLATE)
- ✅ Phase 4: Documentation (ARCHITECTURE.md, copilot-instructions.md)
- ✅ Phase 5: README.md, LEGACY.md, documentation finalization

### Future Enhancements
- [ ] Build script for creating consolidated version (optional)
- [ ] Version compatibility checking utility
- [ ] Specialty dependency management
- [ ] Auto-detection of which specialties to load based on workspace

## Contributing

### Adding a New Skill

Skills are reasoning techniques or methodologies. To add one:

1. Create `v6/skills/style.{technique}.instructions.md`
2. Follow format of existing skills (frontmatter, sections, examples)
3. Add knowledge/ examples if needed
4. Update this ARCHITECTURE.md to document it
5. Update Frank.core.agent.md's [INTEGRATION WITH SKILLS] section

### Adding a New Specialty

Specialties are domain expertise modules. To add one:

1. Copy specialty.TEMPLATE.instructions.md ✅
2. Fill in all required sections
3. Test independently with Frank.core
4. Document triggering keywords and command syntax
5. Update copilot-instructions.md with loading example
6. Update this ARCHITECTURE.md or create your own documentation

### Updating Knowledge Examples

Knowledge files are referenced by skills and specialties:

1. Add new example to `v6/knowledge/example.{Topic}.md`
2. Update skills or specialties that should reference it
3. Keep examples focused and well-commented
4. Include references to source material when applicable

## Support

- **Architecture Questions**: Review this document
- **Quick Start**: See v6/README.md for usage examples
- **Usage Examples**: See copilot-instructions.md
- **Custom Specialties**: Use specialty.TEMPLATE.instructions.md ✅
- **Legacy Migration**: See LEGACY.md for v4/v5 migration guide

---

**Frank v6: Modular, Portable, Skills-Centric AI Assistance** 🚀

Built with ❤️ for flexibility and portability.
