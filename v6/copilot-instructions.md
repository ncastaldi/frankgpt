# Frank v6 - GitHub Copilot Instructions

**Version**: 6.0  
**Last Updated**: April 19, 2026

## Quick Start

Frank v6 is a modular AI assistant built on three layers:

1. **Frank.core** - Your upbeat, friendly mentor (always loaded)
2. **Skills** - Reasoning techniques (CoT, ToT, RAG, CRAFT, Markdown, Mermaid)
3. **Specialties** - Domain expertise (load as needed)

## Using Frank in VS Code

### Core Only (General Assistant)

For general content creation, analysis, and mentoring:

```
Load: v6/Frank.core.agent.md
```

Frank will help with:
- Content creation (prompts, documentation, guides)
- Reviews and analysis
- Business consulting
- Strategic communications

### With Skills (Recommended)

For best results, include the skills Frank uses for reasoning:

```
Load: v6/Frank.core.agent.md
Include: v6/skills/style.craft.instructions.md
Include: v6/skills/style.advanced-reasoning.instructions.md
Include: v6/skills/style.markdown.instructions.md
```

This gives Frank access to:
- C.R.A.F.T. framework for prompt engineering
- Advanced reasoning techniques (CoT, ToT, RAG)
- Markdown formatting standards

### With Specialties (Domain Expert)

Add specialty modules for specific domains:

**Frank for IT Operations**:
```
Load: v6/Frank.core.agent.md
Include: v6/skills/style.craft.instructions.md
Include: v6/specialties/specialty.itil.instructions.md
```

**Frank for DevOps**:
```
Load: v6/Frank.core.agent.md
Include: v6/skills/style.craft.instructions.md
Include: v6/specialties/specialty.devops.instructions.md
```

**Frank for Prompt Engineering**:
```
Load: v6/Frank.core.agent.md
Include: v6/skills/style.craft.instructions.md
Include: v6/skills/style.cot.instructions.md
Include: v6/skills/style.tot.instructions.md
Include: v6/specialties/specialty.prompt-engineering.instructions.md
```

**Frank for Data Analysis**:
```
Load: v6/Frank.core.agent.md
Include: v6/skills/style.markdown.instructions.md
Include: v6/specialties/specialty.data-analysis.instructions.md
```

### Multi-Specialty Composition

You can load multiple specialties simultaneously:

```
Load: v6/Frank.core.agent.md
Include: v6/skills/style.craft.instructions.md
Include: v6/specialties/specialty.devops.instructions.md
Include: v6/specialties/specialty.itil.instructions.md
```

This gives you a Frank with both DevOps AND IT service management expertise.

## Available Specialties (v6)

| Specialty | File | What You Get |
|-----------|------|--------------|
| **IT Operations** | `specialty.itil.instructions.md` | ITIL v4, incident/problem/knowledge management, /ticket, /rca, /sop commands |
| **DevOps** | `specialty.devops.instructions.md` | Docker, Compose, Ansible, IaC, /docker, /ansible commands *(Phase 3)* |
| **Prompt Engineering** | `specialty.prompt-engineering.instructions.md` | Advanced prompting, optimization, /optimize command *(Phase 3)* |
| **Data Analysis** | `specialty.data-analysis.instructions.md` | SQL, Python, statistical modeling, /analyze command *(Phase 3)* |
| **SCCM/Intune** | `specialty.sccm.instructions.md` | Endpoint management, co-management, modern management *(Phase 3)* |

**Note**: Specialties marked *(Phase 3)* are planned but not yet created. Check [v6/ARCHITECTURE.md](v6/ARCHITECTURE.md) for status.

## Available Skills (v6)

| Skill | File | Purpose |
|-------|------|---------|
| **C.R.A.F.T.** | `style.craft.instructions.md` | Structured prompt creation framework |
| **Advanced Reasoning** | `style.advanced-reasoning.instructions.md` | Overview of reasoning techniques |
| **Chain-of-Thought** | `style.cot.instructions.md` | Step-by-step reasoning prompting |
| **Tree-of-Thought** | `style.tot.instructions.md` | Multi-path reasoning with backtracking |
| **RAG** | `style.rag.instructions.md` | Retrieval-augmented generation |
| **Markdown** | `style.markdown.instructions.md` | Formatting and style standards |
| **Mermaid** | `style.mermaid.instructions.md` | Diagram creation in Markdown |

## Commands Reference

### Core Commands (Always Available)

- `/quickstart` - Rapid creation from one-sentence goal
- `/create` - Guided documentation creation
- `/review` - Evaluate prompts or documents
- `/refactor` - Restructure and optimize content
- `/document` - Generate comprehensive docs
- `/communicate [Audience] [Channel] [Subject]` - Recast for audiences
- `/consult [Question]` - Business strategy insights
- `/help` - Learn about Frank's capabilities

### Specialty Commands (When Loaded)

**With specialty.itil**:
- `/ticket` - Incident management workflow
- `/rca` - Root cause analysis
- `/sop` - Create IT documentation
- `/itil` - Explain ITIL v4 principles

**With specialty.devops** *(Phase 3)*:
- `/docker` - Docker/Compose troubleshooting
- `/ansible` - Ansible/IaC assistance

**With specialty.prompt-engineering** *(Phase 3)*:
- `/optimize` - Advanced prompt optimization

**With specialty.data-analysis** *(Phase 3)*:
- `/analyze` - Data analysis workflow

## Customization

### Create Your Own Specialty

1. Copy `v6/specialties/specialty.TEMPLATE.instructions.md` *(Phase 3)*
2. Fill in your domain expertise
3. Define personas, commands, and workflows
4. Save as `specialty.{yourDomain}.instructions.md`
5. Include in your Copilot configuration

See [v6/ARCHITECTURE.md](v6/ARCHITECTURE.md) for detailed guidance.

### Portability

Frank v6 is designed to be portable - just copy the `v6/` folder:

```
your-project/
├── v6/               ← Copy this entire folder
│   ├── Frank.core.agent.md
│   ├── skills/
│   ├── specialties/
│   └── knowledge/
└── .github/
    └── copilot-instructions.md  ← Point to v6/
```

## Troubleshooting

**Frank doesn't have a specialty capability I expected**:
- Check which specialty files are included in your configuration
- Verify the specialty file exists in `v6/specialties/`
- Some specialties are still in development (check ARCHITECTURE.md)

**Commands aren't working**:
- Ensure you've loaded the specialty that provides that command
- Check command syntax (e.g., `/communicate` needs parameters)
- Try `/help` to see what's currently available

**Cross-references or links broken**:
- Ensure you've copied the complete `v6/` folder structure
- Check that relative paths point to correct locations
- Skills and knowledge folders must exist at v6/skills/ and v6/knowledge/

## More Information

- **Architecture Guide**: [v6/ARCHITECTURE.md](v6/ARCHITECTURE.md) *(Phase 4)*
- **Quick Start**: [v6/README.md](v6/README.md) *(Phase 5)*
- **Migration Guide**: See ARCHITECTURE.md for upgrading from v4/v5
- **GitHub Issues**: [Report bugs or request features](https://github.com/yourrepo/frankgpt/issues)

---

**Welcome to Frank v6! Ready to create, analyze, and collaborate!** 🚀
