# Legacy Files - Frank v4/v5 Artifacts

This document identifies legacy files from previous Frank versions and their v6 equivalents or migration status.

---

## ✅ Preserved & Organized

### _Frank_/docx/
**Status**: ✅ Organized (moved from root to subdirectory in Phase 1)  
**Contents**: DOCX exports of source markdown files  
**Action**: Keep as archive - useful for Word-based workflows  
**v6 Equivalent**: Source files now in v6/ structure

### _Frank_/markdown/
**Status**: ✅ Preserved  
**Contents**: Original v5 source markdown files  
**Action**: Keep as reference - shows evolution to v6  
**v6 Equivalent**: 
- `Frank Meadows.agent.md` → Extracted to `v6/Frank.core.agent.md` + multiple specialties
- `style.*.md` → Copied to `v6/skills/`

---

## 🔄 Superseded Files (Consider Archiving)

### copilot-instructions.md (root)
**Status**: 🔄 Superseded by `v6/copilot-instructions.md`  
**Version**: v4/v5 artifact  
**v6 Equivalent**: `v6/copilot-instructions.md` (fully rewritten for modular architecture)  
**Recommendation**: Rename to `copilot-instructions.v5.md` or move to `archive/` folder  

### agents/FrankGPT.consolidated-instructions.md
**Status**: 🔄 Superseded by v6 modular system  
**Version**: v5 consolidated monolith  
**v6 Equivalent**: Use `v6/Frank.core.agent.md` + relevant specialties  
**Recommendation**: Rename to `FrankGPT.consolidated-instructions.v5.md` for reference  

### instructions/core.instructions.md
**Status**: 🔄 Superseded by v6 core  
**Version**: v4 IT-focused core logic  
**v6 Equivalent**: 
- General personality → `v6/Frank.core.agent.md`
- IT-specific logic → `v6/specialties/specialty.itil.instructions.md`  
**Recommendation**: Keep for historical reference, note superseded status  

### instructions/style.markdown.instructions.md
**Status**: 🔄 Duplicate (canonical version in v6)  
**Version**: v4/v5  
**v6 Equivalent**: `v6/skills/style.markdown.instructions.md`  
**Recommendation**: Delete or mark as deprecated (100% duplicate)  

---

## 📦 Kept As-Is

### agents/Data Analyst.agent.md
**Status**: 📦 Extracted to specialty  
**Version**: v4/v5  
**v6 Equivalent**: `v6/specialties/specialty.data-analysis.instructions.md`  
**Recommendation**: Keep original for comparison, clearly superseded by v6  

### agents/SCCM Tutor.agent.md
**Status**: 📦 Extracted to specialty  
**Version**: v4/v5  
**v6 Equivalent**: `v6/specialties/specialty.sccm.instructions.md`  
**Recommendation**: Keep original for comparison, clearly superseded by v6  

### knowledge/
**Status**: ✅ Copied to v6  
**Contents**: Example files for reasoning techniques  
**v6 Equivalent**: `v6/knowledge/` (identical copies)  
**Recommendation**: Keep both - root for reference, v6 for active use  

### prompts/
**Status**: ✅ Kept at root  
**Contents**: Prompt templates (content2template, create-commit, md2html, etc.)  
**v6 Status**: Independent templates, not core to Frank architecture  
**Recommendation**: Keep at root - these are utilities, not agent definitions  
**Future Option**: Could create `specialty.prompt-templates.instructions.md` if desired  

---

## 🗂️ Recommended Cleanup Actions

### Option A: Minimal (Safe)
Just add deprecation notices to superseded files:

```bash
# Add header to superseded files
echo "⚠️ DEPRECATED: This file is superseded by v6/copilot-instructions.md" | cat - copilot-instructions.md > temp && mv temp copilot-instructions.md
```

### Option B: Archive Folder
Create `archive/` folder for v4/v5 artifacts:

```bash
mkdir archive/
mv copilot-instructions.md archive/copilot-instructions.v5.md
mv agents/FrankGPT.consolidated-instructions.md archive/
mv instructions/core.instructions.md archive/core.instructions.v4.md
# Keep originals in _Frank_/markdown and agents/ for reference
```

### Option C: Aggressive Cleanup
Delete duplicates, keep only v6 as canonical:

```bash
# Delete 100% duplicates
rm instructions/style.markdown.instructions.md

# Archive superseded files
mkdir archive/
mv copilot-instructions.md archive/
mv agents/FrankGPT.consolidated-instructions.md archive/
mv instructions/core.instructions.md archive/

# Keep _Frank_/, agents/, knowledge/, prompts/ as-is for reference
```

---

## 📊 Version Mapping

| v4/v5 File | Purpose | v6 Equivalent |
|------------|---------|---------------|
| Frank Meadows.agent.md | Monolithic agent | Frank.core.agent.md + specialties |
| Data Analyst.agent.md | Data analysis | specialty.data-analysis.instructions.md |
| SCCM Tutor.agent.md | Endpoint mgmt | specialty.sccm.instructions.md |
| FrankGPT.consolidated.md | v5 monolith | Frank.core + specialties composition |
| core.instructions.md | v4 core | Frank.core + specialty.itil |
| copilot-instructions.md | VS Code integration | v6/copilot-instructions.md |
| instructions/style.*.md | Style guides | v6/skills/style.*.md |
| knowledge/*.md | Examples | v6/knowledge/*.md |

---

## 🎯 Migration Decision Matrix

**Keep if**:
- ✅ Original source for v6 content (_Frank_/markdown/)
- ✅ Unique content not in v6 (prompts/)
- ✅ Archive/reference value (agents/ originals)

**Archive if**:
- 📦 Superseded by v6 but has historical value
- 📦 Might be useful for rollback scenarios
- 📦 Comparison/migration reference

**Delete if**:
- 🗑️ 100% duplicate of v6 content
- 🗑️ No historical value
- 🗑️ Confusing to keep both versions

---

## 💡 Recommendation

**Suggested approach**: Option B (Archive Folder)

1. Create `archive/` folder
2. Move superseded root files: `copilot-instructions.md`, `agents/FrankGPT.consolidated-instructions.md`
3. Delete 100% duplicate: `instructions/style.markdown.instructions.md`
4. Keep everything else as-is for reference
5. Add note to root README pointing to v6/

This preserves history while making it clear v6 is canonical.

---

**Last Updated**: Phase 5 - April 2026  
**For Questions**: See v6/ARCHITECTURE.md for v6 design philosophy
