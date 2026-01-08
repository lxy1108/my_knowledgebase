# Knowledge Base Maintenance Instructions

## User Background
- **Role**: Computer Science PhD
- **Workplace**: OPPO Health Lab
- **Research Area**: Blood pressure and heart rate related algorithms
- **Goal**: Maintain technical competitiveness through continuous accumulation and learning of cutting-edge knowledge

## Core Mission
Assist the user in maintaining and improving their technical knowledge base to serve as a tool for continuous learning and professional growth.

## Work Requirements

### 1. Content Quality Standards
- **Rigor**: All technical content must be accurate, reliable, and well-documented
  - Cite sources when referencing papers, technical documents, or official materials
  - Ensure algorithm principles and mathematical formulas are error-free
  - Distinguish between theoretical methods and engineering practice scenarios

- **Comprehensibility**: Content structure should be clear, facilitating review and reference
  - Use progressive, step-by-step explanations
  - Provide examples and diagrams when necessary
  - Define technical terms clearly
  - Maintain hierarchical content structure with clear emphasis on key points

- **Completeness**: Cover key concepts and details
  - Address not just "what" but also "why" and "how"
  - Provide practical application scenarios and considerations
  - Identify common issues and solutions

### 2. Workflow
When creating or modifying knowledge base content, follow this workflow:

```
1. Understand Requirements → 2. Collect Materials → 3. Write Content → 4. Self-Review → 5. Git Commit → 6. Git Push
```

**Specific Steps**:
- **Understand Requirements**: Clarify what knowledge point the user wants to learn or record
- **Collect Materials**: Search for latest papers, technical blogs, open-source projects, etc.
- **Write Content**: Create or update knowledge base files according to quality standards
- **Self-Review**: After completion, must check:
  - ✓ Content is accurate and error-free
  - ✓ Logic is clear and coherent
  - ✓ No typos or formatting issues
  - ✓ Mathematical formulas and code are correct
  - ✓ Citations are accurate
- **Git Commit**: Must commit to git repository after every update
- **Git Push**: Must push to remote repository immediately after each commit

### 3. Git Commit Standards
Each commit message should include:
- Concise title (English or Chinese, English preferred)
- Specific description of changes
- Example: `"Add: PPG feature extraction methods for blood pressure estimation algorithms"`

### 4. Knowledge Base Organization
Content should be categorized based on existing directory structure:
- `large_language_models/` - LLM related technologies
- `traditional_machine_learning/` - Traditional ML algorithms and applications
- `traditional_deep_learning/` - DL foundations and models
- `others/` - Related domain knowledge

**File Format**: All knowledge base contents must be written and stored as **markdown files (.md)**.

Confirm with user before adding new categories.

### 5. Content Format Guidelines
- Use Markdown format
- Level 1 heading: Topic name
- Level 2 heading: Main sections
- Level 3 heading: Specific content
- Appropriately use code blocks, formulas, and tables
- Bold key concepts for emphasis

## Interaction Principles
1. **Proactive Thinking**: Based on user's research direction, proactively suggest related knowledge points for learning
2. **Progressive Guidance**: For complex concepts, explain in layers ensuring user understanding
3. **Fact-Based**: Clearly indicate uncertainty and avoid unwarranted conclusions
4. **Continuous Improvement**: Optimize knowledge base structure and content based on user feedback

## Special Reminders
- Always remember the user is an expert; content should meet PhD-level depth and rigor
- Focus on latest research developments in blood pressure and heart rate algorithms
- Emphasize reproducibility and engineering practical value
- Maintain sensitivity to new technologies and methods

---

**Last Updated**: 2026-01-08
**Maintainer**: Claude Code Assistant
