# 🤝 Contributing to MetaCH

Thank you for your interest in contributing! MetaCH is an open-source educational project, and we welcome contributions from the community.

---

## 📋 Code of Conduct

- Be respectful and inclusive
- Focus on code quality and education
- Help others learn and grow
- No harassment or discrimination

---

## 🚀 How to Contribute

### 1. Fork the Repository

```bash
# Click "Fork" on GitHub
git clone https://github.com/your-username/AI-Website-Project.git
cd AI-Website-Project
```

### 2. Create a Feature Branch

```bash
git checkout -b feature/your-feature-name
# or for bug fixes
git checkout -b fix/bug-name
```

### 3. Make Your Changes

```bash
# Edit files
# Test locally
npm run dev

# Verify no errors
npm run lint
npm run test
```

### 4. Commit Your Changes

```bash
git add .
git commit -m "feat: add new feature"
# or
git commit -m "fix: resolve issue with X"
# or
git commit -m "docs: improve documentation"
```

**Commit message format:**
- `feat:` - New feature
- `fix:` - Bug fix
- `docs:` - Documentation changes
- `style:` - Code style (formatting)
- `refactor:` - Code refactoring
- `test:` - Adding tests
- `chore:` - Build/dependency updates

### 5. Push to Your Fork

```bash
git push origin feature/your-feature-name
```

### 6. Create a Pull Request

1. Go to your fork on GitHub
2. Click "Compare & pull request"
3. Fill in the PR description
4. Submit the PR

---

## 📝 PR Description Template

```markdown
## Description
Brief description of changes

## Type of Change
- [ ] New feature
- [ ] Bug fix
- [ ] Documentation
- [ ] Performance improvement

## Checklist
- [ ] Code follows style guidelines
- [ ] Comments added for complex logic
- [ ] No new warnings generated
- [ ] Tests added/updated
- [ ] Documentation updated

## Related Issues
Closes #(issue number)
```

---

## 🎨 Code Style Guidelines

### JavaScript
```javascript
// Use const/let, not var
const myVar = 'value';

// Use arrow functions
const fn = (x) => x * 2;

// Use meaningful names
const getUserData = async () => {};

// Add comments for complex logic
// Calculate fibonacci recursively
const fib = (n) => n <= 1 ? n : fib(n - 1) + fib(n - 2);

// Use async/await, not .then()
const data = await fetch(url);
```

### CSS
```css
/* Use CSS variables */
color: var(--text-primary);

/* Use descriptive class names */
.hero-title { /* Good */ }
.title { /* Bad */ }

/* Keep specificity low */
.button { } /* instead of div.container .button */

/* Comment sections */
/* ──────────────────────── */
/* Navigation Styles */
/* ──────────────────────── */
```

### HTML
```html
<!-- Use semantic elements -->
<header>
<nav>
<main>
<section>
<article>
<footer>

<!-- Add aria labels for accessibility -->
<button aria-label="Menu">☰</button>

<!-- Use meaningful IDs -->
id="user-profile" <!-- Good -->
id="div1" <!-- Bad -->
```

---

## 🧪 Testing

### Run Tests
```bash
npm test
```

### Test Checklist
- [ ] Feature works locally
- [ ] Responsive design verified (mobile/tablet/desktop)
- [ ] No console errors
- [ ] Accessibility tested (keyboard navigation, screen reader)
- [ ] Performance acceptable (Lighthouse score)

---

## 📚 Documentation

When adding features, update:

1. **README.md** - Add feature description
2. **LEARNING_GUIDE.md** - Add educational content
3. **Code comments** - Explain complex logic
4. **Git commits** - Clear, descriptive messages

---

## 🐛 Reporting Bugs

### Before Creating an Issue

- [ ] Search existing issues
- [ ] Try latest version
- [ ] Check documentation

### Issue Template

```markdown
**Describe the bug**
Clear description of the issue

**To Reproduce**
Steps to reproduce the behavior:
1. Go to '...'
2. Click on '...'
3. See error

**Expected behavior**
What should happen

**Screenshots**
If applicable

**Environment**
- Browser: Chrome 90
- OS: Windows 10
- Device: Desktop
```

---

## 💡 Feature Requests

### Suggest a Feature

```markdown
**Is your feature request related to a problem?**
Yes/No, description

**Describe the solution you'd like**
Clear description

**Describe alternatives you've considered**
Other solutions

**Additional context**
Any other relevant info
```

---

## 📦 Types of Contributions

### Code Contributions
- Bug fixes
- New features
- Performance improvements
- Accessibility enhancements

### Documentation
- README improvements
- Tutorial creation
- API documentation
- Code examples

### Community
- Answering questions
- Creating tutorials
- Writing blog posts
- Sharing projects

---

## 🎓 Learning Levels

Contributions are organized by difficulty:

### BASIC (Great for beginners)
- [ ] Fix typos in documentation
- [ ] Improve comments
- [ ] Add HTML improvements
- [ ] Basic CSS tweaks

### INTERMEDIATE (Some experience)
- [ ] Add new features
- [ ] Improve API integration
- [ ] Add form validation
- [ ] Create animations

### ADVANCED (Experienced developers)
- [ ] Performance optimization
- [ ] Architecture improvements
- [ ] State management refactoring
- [ ] Testing infrastructure

---

## ✅ Contribution Checklist

Before submitting:

- [ ] Code follows style guide
- [ ] Comments added
- [ ] Tests pass: `npm test`
- [ ] No new warnings: `npm run lint`
- [ ] Documentation updated
- [ ] Commit messages clear
- [ ] Branch is up to date with main
- [ ] PR description complete

---

## 🚀 Merge Requirements

Your PR will be merged when:

1. ✅ All checks pass
2. ✅ Code review approved
3. ✅ Documentation updated
4. ✅ At least 1 approval from maintainer
5. ✅ No conflicts with main branch

---

## 📊 Recognition

Contributors are recognized in:
- `README.md` Contributors section
- Commit history
- Release notes

```markdown
## Contributors ✨

- [Your Name](https://github.com/username) - Feature X
- [Another Dev](https://github.com/username) - Fix Y
```

---

## 🔗 Helpful Links

- [GitHub Flow Guide](https://guides.github.com/introduction/flow/)
- [Commit Message Convention](https://www.conventionalcommits.org/)
- [Semantic Versioning](https://semver.org/)
- [Keep a Changelog](https://keepachangelog.com/)

---

## 💬 Questions?

- **GitHub Issues** - For bugs and features
- **Discussions** - For questions and ideas
- **Email** - Contact maintainers

---

## 📜 License

By contributing to MetaCH, you agree that your contributions will be licensed under the MIT License.

---

**Thank you for contributing! 🎉**

Your contributions help make MetaCH better for everyone!

Built with ❤️ by **Kabi lash** • Powered by **Claude API**
