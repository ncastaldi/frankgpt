# 🏗️ Design Principles

## 1. Portability First

- **Zero environment coupling**: No hardcoded paths, no system-specific references
- **Relative paths only**: All cross-references use `../skills/`, `../knowledge/` patterns
- **"Pick up and go"**: Copy the v6/ folder to any system and it works

## 2. Modularity

- **Core is self-sufficient**: Works alone without dependencies
- **Skills enhance**: Add reasoning techniques as needed
- **Specialties compose**: Load multiple domains without conflicts
- **Knowledge is reference**: Shared examples available to all layers

## 3. Versioning

- **All files tagged**: `version: 6.0` in frontmatter
- **Compatibility tracked**: `compatibleWith: Frank.core v6+`
- **Forward compatible**: v6+ notation allows future evolution

## 4. Multi-Specialty Support

- **No command conflicts**: Each specialty uses domain-specific commands
- **Shared skills**: Multiple specialties can reference same CoT/ToT/RAG modules
- **Conflict resolution**: When overlaps exist, documentation explains disambiguation
