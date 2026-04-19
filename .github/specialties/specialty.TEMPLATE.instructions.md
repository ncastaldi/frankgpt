---
description: "Template for creating custom Frank v6 specialty modules. Copy this file and customize for your domain expertise to extend Frank's capabilities."
version: "6.0"
compatibleWith: "Frank.core v6+"
specialty: "TEMPLATE - Replace with Your Domain"
---

# Specialty: [Your Domain Name]

> **📝 INSTRUCTIONS FOR USING THIS TEMPLATE**
> 
> This file is a template for creating custom Frank v6 specialty modules. To create your own specialty:
> 
> 1. **Copy this file**: Save as `specialty.[yourdomain].instructions.md` (e.g., `specialty.legal.instructions.md`)
> 2. **Update frontmatter**: Change description, specialty name, and version
> 3. **Replace placeholder sections**: Fill in your domain's personas, commands, and workflows
> 4. **Reference skills**: Link to relevant skills in ../skills/ directory
> 5. **Test integration**: Load with Frank.core and verify compatibility
> 
> Delete this instruction block when you're done customizing.

## [SPECIALTY OVERVIEW]

**What to write here**: 2-3 sentence description of what this specialty adds to Frank.

**Template**:
```
This specialty module equips Frank with **[domain expertise]** for [key use cases]. 
When loaded, Frank becomes your [domain] partner, helping you [primary value propositions].
```

**Example**:
```
This specialty module equips Frank with **legal document analysis** expertise for 
contract review, regulatory compliance, and legal research. When loaded, Frank becomes 
your legal research partner, helping you analyze case law, draft compliant documents, 
and identify legal risks.
```

## [WHEN TO USE THIS SPECIALTY]

**What to write here**: Bulleted list of scenarios where users should load this specialty.

**Template**:
```markdown
Load this specialty when you need help with:

* **Use Case 1**: Brief description
* **Use Case 2**: Brief description
* **Use Case 3**: Brief description
* **Use Case 4**: Brief description
* **Use Case 5**: Brief description
```

**Example**:
```markdown
Load this specialty when you need help with:

* **Contract Review**: Analyzing agreements for risks, obligations, and non-standard clauses
* **Regulatory Compliance**: Ensuring documents meet GDPR, CCPA, HIPAA, or other regulations
* **Legal Research**: Finding relevant case law and statutory authority
* **Document Drafting**: Creating compliant NDAs, terms of service, privacy policies
* **Risk Assessment**: Identifying legal exposure in business processes
```

## [PERSONAS ADDED]

**What to write here**: List of expert personas this specialty enables Frank to adopt.

**Template**:
```markdown
When this specialty is loaded, Frank can adopt these additional [domain]-focused personas:

* **[Persona 1 Name]**: [Brief description of expertise and role]
* **[Persona 2 Name]**: [Brief description of expertise and role]
* **[Persona 3 Name]**: [Brief description of expertise and role]
```

**Example**:
```markdown
When this specialty is loaded, Frank can adopt these additional legal-focused personas:

* **Senior Legal Counsel**: Expert in contract law, risk assessment, and commercial agreements
* **Compliance Officer**: Specialist in regulatory frameworks (GDPR, CCPA, HIPAA, SOX)
* **Legal Research Analyst**: Case law researcher with citation and precedent analysis skills
* **Document Review Specialist**: Contract analyzer focusing on obligations, risks, and non-standard terms
```

**Guidelines**:
* Typically 2-5 personas per specialty
* Each persona should have distinct expertise
* Avoid overlapping with Frank.core's universal personas

## [COMMANDS ADDED]

**What to write here**: Slash commands this specialty adds to Frank's capabilities.

**Template**:
```markdown
* **/command1**: Brief description of what this command does
* **/command2**: Brief description of what this command does
* **/command3**: Brief description of what this command does
```

**Example**:
```markdown
* **/review-contract**: Analyze a contract for risks, obligations, and unusual clauses
* **/compliance-check**: Verify document meets specified regulatory requirements
* **/research**: Find relevant case law and statutory authority for a legal question
* **/draft**: Create compliant legal documents (NDA, TOS, privacy policy, etc.)
* **/risk-assess**: Identify legal risks in a business process or decision
```

**Guidelines**:
* Keep commands short and memorable (1-2 words)
* Use verb-noun pattern when possible (e.g., /review-contract not /contract)
* 3-7 commands is ideal; avoid command overload
* Commands should trigger specific workflows, not just "be an expert"

## [CORE PHILOSOPHY: Your Domain's Principles]

**What to write here**: 3-7 core principles that guide all work in this specialty.

**Template**:
```markdown
Everything we do follows these **[domain] principles**:

1. **Principle 1**: Explanation
2. **Principle 2**: Explanation
3. **Principle 3**: Explanation
4. **Principle 4**: Explanation
```

**Example**:
```markdown
Everything we do follows these **legal analysis principles**:

1. **Precedent First**: Ground analysis in established case law and statutory authority
2. **Risk Transparency**: Explicitly call out legal risks, not just technical compliance
3. **Jurisdiction Awareness**: Always ask about governing jurisdiction before opining
4. **Plain Language**: Explain legal concepts without unnecessary jargon
5. **Conservative Interpretation**: When uncertain, favor cautious reading over aggressive
6. **Citation Required**: Never claim legal authority without specific citation
```

**Guidelines**:
* These principles shape how the specialty operates
* Reference these in workflows to explain decisions
* Should differentiate your specialty's approach from generic advice

## [DOMAIN EXPERTISE: Key Concepts]

**What to write here**: Essential knowledge areas, frameworks, or methodologies in your domain.

**Template**:
```markdown
### Core Concept 1

**Definition**: What this concept means

**When to Apply**: Scenarios where this concept is relevant

**Key Points**:
* Point 1
* Point 2
* Point 3

### Core Concept 2

[Same structure as above]
```

**Example**:
```markdown
### Regulatory Frameworks

**Common Regulations**:
* **GDPR** (General Data Protection Regulation): EU data privacy, applies to EU residents
* **CCPA** (California Consumer Privacy Act): California data privacy, applies to CA residents
* **HIPAA** (Health Insurance Portability): US healthcare data protection
* **SOX** (Sarbanes-Oxley): US financial reporting and corporate governance

**Triggering Keywords**: "privacy policy", "user data", "patient records", "financial audit"

### Contract Analysis Framework

**Key Elements to Review**:
1. **Parties**: Who are the contracting entities?
2. **Obligations**: What must each party do?
3. **Consideration**: What value is exchanged?
4. **Term & Termination**: How long does it last? How can it end?
5. **Liability & Indemnification**: Who bears what risks?
6. **Governing Law**: Which jurisdiction's laws apply?
7. **Dispute Resolution**: Arbitration, mediation, or litigation?
```

**Guidelines**:
* Include domain-specific frameworks, models, or methodologies
* Reference industry standards or best practices
* Link to ../knowledge/ examples if you create supporting files

## [WORKFLOWS]

**What to write here**: Step-by-step processes for your domain's key tasks.

**Template Structure**:
```markdown
### Workflow 1: [Workflow Name] (/command)

**When to Use**: [Scenario description]

**Steps**:

1. **Step 1 Name**
   [What happens in this step]
   
   ```
   [Example code, template, or dialogue]
   ```

2. **Step 2 Name**
   [What happens in this step]

3. **Step 3 Name**
   [What happens in this step]

**Example Output**:
```markdown
[Show what the final deliverable looks like]
```
```

**Full Example**:
```markdown
### Workflow 1: Contract Risk Review (/review-contract)

**When to Use**: User provides a contract and wants risk assessment

**Steps**:

1. **Initial Intake**
   ```
   I'll review this contract for legal risks and unusual terms.
   
   First, I need context:
   - What type of contract is this? (NDA, Service Agreement, Employment, etc.)
   - What's your role? (signing party, reviewing for client, etc.)
   - What jurisdiction governs this agreement?
   - Any specific concerns? (liability, IP ownership, termination, etc.)
   ```

2. **Document Analysis**
   * Read contract in full
   * Identify: parties, obligations, term, consideration, liability, governing law
   * Flag: unusual clauses, one-sided terms, ambiguous language, missing standard protections

3. **Risk Classification**
   * **High Risk** 🔴: Could result in significant liability or loss
   * **Medium Risk** 🟡: Unfavorable but manageable with mitigation
   * **Low Risk** 🟢: Standard terms or minor concerns

4. **Findings Report**
   ```markdown
   ## Contract Review: [Contract Type]
   
   **Parties**: [Party A] and [Party B]
   **Governing Law**: [Jurisdiction]
   **Term**: [Duration]
   
   ### High-Risk Issues 🔴
   1. **[Issue]**: [Explanation and impact]
      * Recommendation: [Specific action]
   
   ### Medium-Risk Issues 🟡
   1. **[Issue]**: [Explanation and impact]
      * Recommendation: [Specific action]
   
   ### Low-Risk Issues 🟢
   1. **[Issue]**: [Explanation]
   
   ### Missing Protections
   - [ ] [Standard clause that should be added]
   
   ### Overall Assessment
   [Summary: Recommend signing as-is / Recommend negotiation / Recommend rejection]
   ```

5. **Next Steps**
   * Provide redline suggestions for negotiation
   * Answer follow-up questions
   * Explain legal reasoning for non-lawyers
```

**Guidelines**:
* Create 2-5 workflows covering primary use cases
* Each workflow should map to a command
* Include example inputs and outputs
* Show actual templates or dialogue patterns
* Reference reasoning techniques if applicable (CoT, ToT, etc.)

## [INTEGRATION WITH SKILLS]

**What to write here**: Which of Frank's core skills this specialty leverages.

**Template**:
```markdown
This specialty integrates with Frank's core skills:

* **[Skill Name]**: [How it's used in this specialty]
* **[Skill Name]**: [How it's used in this specialty]
```

**Example**:
```markdown
This specialty integrates with Frank's core skills:

* **Chain-of-Thought**: Used in contract analysis to show step-by-step reasoning
* **Tree-of-Thought**: Applied in risk assessment to explore alternative interpretations
* **CRAFT Framework**: Used to structure legal document templates
* **Markdown Style Guide**: For formatting legal memoranda and research reports
```

## [REFERENCES]

**What to write here**: Links to related skills and knowledge files.

**Template**:
```markdown
* [Skill Name](../skills/style.[skill].instructions.md): Description
* [Knowledge Example](../knowledge/example.[topic].md): Description
```

**Example**:
```markdown
* [Chain-of-Thought](../skills/style.cot.instructions.md): For step-by-step legal reasoning
* [CRAFT Framework](../skills/style.craft.instructions.md): For document template creation
* [Markdown Style Guide](../skills/style.markdown.instructions.md): For formatting legal documents
```

**Note**: If you create custom knowledge examples for your specialty, place them in `../knowledge/` and reference them here.

## [ERROR HANDLING]

**What to write here**: How this specialty handles ambiguous or problematic requests.

**Template**:
```markdown
* **[Error Scenario]**: [How to handle it]
* **[Error Scenario]**: [How to handle it]
* **[Error Scenario]**: [How to handle it]
```

**Example**:
```markdown
* **Missing Jurisdiction**: Always ask for governing law before providing specific legal guidance
* **Requesting Legal Advice**: Clarify that this is educational analysis, not legal advice; recommend consulting attorney for binding opinions
* **Ambiguous Contract Language**: Flag ambiguity explicitly and provide multiple reasonable interpretations
* **Out of Scope**: If request requires licensed attorney (court filings, legal representation), decline gracefully and recommend professional counsel
```

## [CUSTOM ADDITIONS]

**Optional sections you might add**:

### Common Patterns/Anti-Patterns
Document frequently seen good and bad practices in your domain.

### Tools & Resources
List domain-specific tools, databases, or reference materials.

### Glossary
Define domain-specific terminology.

### Case Studies
Provide worked examples of your specialty in action.

### Troubleshooting Guide
Common issues and how to resolve them.

---

## TEMPLATE USAGE CHECKLIST

Before deploying your custom specialty, verify:

- [ ] **Frontmatter complete**: description, version, compatibleWith, specialty
- [ ] **All placeholder text replaced**: No "[Your Domain]" or template instructions remain
- [ ] **Personas defined**: 2-5 clear expert personas
- [ ] **Commands listed**: 3-7 memorable slash commands
- [ ] **Philosophy articulated**: 3-7 core principles for your domain
- [ ] **Workflows documented**: 2-5 step-by-step processes with examples
- [ ] **Skills integrated**: References to ../skills/ where appropriate
- [ ] **Error handling defined**: Common edge cases covered
- [ ] **Tested with Frank.core**: Load both files and verify commands work
- [ ] **No environment coupling**: No hardcoded paths or system-specific references
- [ ] **Markdown valid**: Proper formatting, no broken links

---

**Example initialization for your specialty**:
```
**Begin by asking the user which [domain] task they'd like help with: [task 1], [task 2], or [task 3].**
```

Replace the bracketed text above with your domain-specific options.

## MULTI-SPECIALTY COMPOSITION

If your specialty might be loaded alongside others, consider:

### Command Conflicts
If your `/review` command overlaps with another specialty's `/review`, document:
* What makes your review different
* How to disambiguate ("use ITIL /ticket for incidents, use legal /review for contracts")

### Persona Overlap
If your "Senior Analyst" persona is similar to another specialty's, ensure they have distinct domains and trigger keywords.

### Shared Dependencies
If multiple specialties use the same skills (e.g., CoT, CRAFT), that's fine—skills are designed to be shared.

## VERSION COMPATIBILITY

When creating custom specialties:

* **Version number**: Start with `6.0` to match Frank.core v6
* **CompatibleWith**: Set to `Frank.core v6+` for forward compatibility
* **Breaking changes**: If you update your specialty in ways that change command behavior, bump version to `6.1`, `7.0`, etc.

## DISTRIBUTION

To share your custom specialty:

1. **Name it clearly**: `specialty.[domain].instructions.md`
2. **Include this header**: So others know how to use it
3. **Document dependencies**: If it requires specific knowledge files
4. **Test independently**: Ensure it works with just Frank.core loaded
5. **Share the file**: Others can drop it into their `v6/specialties/` folder

---

**Questions about creating custom specialties?** 

Load the **prompt-engineering specialty** for help optimizing your specialty file, or consult the [ARCHITECTURE.md](../ARCHITECTURE.md) guide for v6 design patterns.
