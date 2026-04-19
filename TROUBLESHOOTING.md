# 📞 Support and Troubleshooting

## Documentation

- Quick start: This file (README.md)
- Architecture deep-dive: [ARCHITECTURE.md](ARCHITECTURE.md)
- VS Code setup: [copilot-instructions.md](copilot-instructions.md)
- Template guide: [specialty.TEMPLATE.instructions.md](specialties/specialty.TEMPLATE.instructions.md)

## Need help?

- Review [ARCHITECTURE.md](ARCHITECTURE.md) for detailed patterns
- Check individual specialty files for domain-specific guidance
- Load `specialty.prompt-engineering.instructions.md` to optimize your own prompts

## Troubleshooting

### Frank isn't responding to specialty commands

**Check**: Are you loading both Frank.core AND the specialty?

```plaintext
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
