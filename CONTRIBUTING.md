# Contributing to Nuxt UI Rules

Thank you for your interest in improving Nuxt UI Rules! This project aims to help AI assistants generate better Nuxt UI v3 code by providing comprehensive rules and examples.

## 🎯 How You Can Contribute

### 1. Report AI Hallucinations
Found an AI making mistakes with Nuxt UI v3? Help us fix it!

- **What to include**: Screenshot/example of the wrong code generated
- **Expected behavior**: What the AI should have generated instead
- **AI assistant used**: Cursor, Claude, ChatGPT, etc.

### 2. Suggest Rule Improvements
- Missing breaking changes or patterns
- Unclear examples or explanations
- New v3 features not covered

### 3. Add Real-World Examples
Share code patterns that work well with AI assistants:
- Complex component combinations
- Common use cases and patterns
- Performance optimizations

### 4. Improve Documentation
- Better explanations for complex concepts
- More comprehensive examples
- Translations (eventually)

## 📝 Contribution Guidelines

### Before Contributing
1. Check existing [issues](https://github.com/hugorcd/nuxt-ui-rules/issues) and [discussions](https://github.com/hugorcd/nuxt-ui-rules/discussions)
2. For major changes, open a discussion first
3. Test your changes with real AI assistants when possible

### Making Changes
1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature-name`
3. Make your changes
4. Test with AI assistants if applicable
5. Submit a pull request

### Rule Format
When adding new rules, follow this structure:

```md
## Section Name

Brief explanation of the concept.

### Subsection (if needed)

```vue
<!-- ❌ Don't do this -->
<BadExample />

<!-- ✅ Do this instead -->
<GoodExample />
```

**Why**: Brief explanation of why this matters for AI assistants.
```

### Commit Messages
Use conventional commits:
- `feat: add new overlay pattern examples`
- `fix: correct UModal slot documentation`
- `docs: improve design token explanations`

## 🧪 Testing Your Changes

### With AI Assistants
1. Copy your updated rules to your AI assistant
2. Ask it to generate Nuxt UI v3 code
3. Verify it follows the new/updated rules
4. Share results in your PR

### Validation
Run our validation script:
```bash
npm run validate-rules
```

## 🏷️ Issue Templates

Use our issue templates for:
- 🐛 **Bug Report**: AI generating wrong code
- 💡 **Feature Request**: Missing rules or improvements
- 📚 **Documentation**: Unclear or missing documentation
- ❓ **Question**: Usage questions

## 💬 Community Discussions

- **Show & Tell**: Share successful AI-generated code
- **Ideas**: Discuss potential improvements
- **Help**: Get help with specific use cases

## 📦 Release Process

We follow semantic versioning:
- **Patch** (1.0.1): Bug fixes, small clarifications
- **Minor** (1.1.0): New rules, examples, or features
- **Major** (2.0.0): Breaking changes to rule structure

## ⭐ Recognition

Contributors will be:
- Listed in release notes
- Added to the README contributors section
- Mentioned in the changelog

## 🎉 Getting Started

1. **Star the repo** to show support
2. **Join discussions** to share ideas
3. **Open your first issue** or PR
4. **Share the project** with your community

---

**Questions?** Open a discussion or reach out to [@hugorcd](https://github.com/hugorcd)! 