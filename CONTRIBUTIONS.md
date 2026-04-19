# 🤝 Contributing

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

   Ensure your specialty works with Frank.core by loading it in a test environment:
   ```plaintext
   Load: v6/Frank.core.agent.md + v6/specialties/specialty.legal.instructions.md
   ```

4. **Share** (optional):

   Your custom specialty can be shared with others - just distribute the file!

**See**: [specialty.TEMPLATE.instructions.md](.github/specialties/specialty.TEMPLATE.instructions.md) for detailed guidance

