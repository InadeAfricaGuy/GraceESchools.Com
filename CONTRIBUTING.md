# Contributing to Grace E. Schools Website

Thank you for your interest in contributing to the Grace E. Schools website! This document provides guidelines for contributing to the project.

## Table of Contents

1. [Code of Conduct](#code-of-conduct)
2. [Getting Started](#getting-started)
3. [How to Contribute](#how-to-contribute)
4. [Coding Standards](#coding-standards)
5. [Pull Request Process](#pull-request-process)
6. [Reporting Issues](#reporting-issues)

---

## Code of Conduct

### Our Pledge

We are committed to providing a welcoming and inclusive environment for all contributors. We expect everyone to:

- Be respectful and considerate
- Accept constructive criticism gracefully
- Focus on what is best for the project
- Show empathy towards other community members

### Unacceptable Behavior

- Harassment or discrimination of any kind
- Trolling or insulting comments
- Publishing others' private information
- Other conduct which could reasonably be considered inappropriate

---

## Getting Started

### Prerequisites

Before you begin, ensure you have:

- A GitHub account
- Git installed on your computer
- A text editor (VS Code recommended)
- Basic knowledge of HTML, CSS, and JavaScript

### Setting Up Your Development Environment

1. **Fork the Repository**
   - Click the "Fork" button at the top right of the repository page

2. **Clone Your Fork**
   ```bash
   git clone https://github.com/your-username/GraceESchools.Com.git
   cd GraceESchools.Com
   ```

3. **Add Upstream Remote**
   ```bash
   git remote add upstream https://github.com/InadeAfricaGuy/GraceESchools.Com.git
   ```

4. **Create a Branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

5. **Start Local Server**
   ```bash
   python -m http.server 8000
   ```
   Visit http://localhost:8000 in your browser

---

## How to Contribute

### Types of Contributions

We welcome the following types of contributions:

#### 1. Bug Fixes
- Fix broken links
- Correct typos or grammar
- Resolve layout issues
- Fix browser compatibility problems

#### 2. Feature Additions
- New sections or pages
- Enhanced interactivity
- Improved accessibility
- Performance optimizations

#### 3. Content Updates
- Update school information
- Add new program details
- Refresh statistics
- Update contact information

#### 4. Documentation
- Improve README.md
- Enhance code comments
- Update guides
- Add examples

### Before You Start

1. **Check Existing Issues**: Look for related issues or discussions
2. **Create an Issue**: For significant changes, create an issue first to discuss
3. **Get Approval**: Wait for maintainer approval before starting work
4. **One Issue Per PR**: Keep pull requests focused on a single issue

---

## Coding Standards

### HTML Standards

#### Structure
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Page description">
    <title>Page Title - Grace E. Schools</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <!-- Content -->
</body>
</html>
```

#### Best Practices
- Use semantic HTML5 elements (`<nav>`, `<section>`, `<article>`, etc.)
- Indent with 4 spaces
- Use lowercase for element names and attributes
- Always close tags properly
- Include alt text for images
- Use descriptive class names

#### Example
```html
<!-- Good -->
<section class="content-section">
    <div class="container">
        <h2>Section Title</h2>
        <p>Section content goes here.</p>
    </div>
</section>

<!-- Avoid -->
<div class="section">
    <div>
        <h2>Section Title</h2>
<p>Section content goes here.</p>
    </div></div>
```

### CSS Standards

#### Organization
```css
/* 1. CSS Variables */
:root {
    --primary-color: #2563eb;
}

/* 2. Reset/Base Styles */
* {
    margin: 0;
    padding: 0;
}

/* 3. Layout Components */
.navbar { }

/* 4. Page-Specific Styles */
.page-header { }

/* 5. Responsive Styles */
@media (max-width: 768px) { }
```

#### Best Practices
- Use CSS variables for colors and repeated values
- Group related styles together
- Add comments to separate sections
- Use meaningful class names
- Avoid !important
- Mobile-first approach for media queries

#### Example
```css
/* Good */
.level-card {
    background: var(--white);
    padding: 2rem;
    border-radius: 10px;
    transition: transform 0.3s ease;
}

.level-card:hover {
    transform: translateY(-10px);
}

/* Avoid */
.card {
    background: white !important;
    padding: 32px;
}
```

### JavaScript Standards

#### Best Practices
- Use `const` and `let`, avoid `var`
- Use meaningful variable names
- Add comments for complex logic
- Handle errors gracefully
- Use strict mode
- Follow ES6+ syntax

#### Example
```javascript
'use strict';

document.addEventListener('DOMContentLoaded', function() {
    // Get form element
    const contactForm = document.querySelector('.contact-form');
    
    if (contactForm) {
        // Add submit event listener
        contactForm.addEventListener('submit', handleFormSubmit);
    }
});

/**
 * Handle contact form submission
 * @param {Event} e - Submit event
 */
function handleFormSubmit(e) {
    e.preventDefault();
    
    // Form handling logic
    const formData = new FormData(e.target);
    console.log('Form submitted', formData);
}
```

### Accessibility Standards

All contributions must meet WCAG 2.1 Level AA standards:

- ✅ Proper heading hierarchy (h1 → h2 → h3)
- ✅ Sufficient color contrast (4.5:1 for normal text)
- ✅ Keyboard navigation support
- ✅ Alt text for images
- ✅ Form labels associated with inputs
- ✅ Focus indicators visible
- ✅ No reliance on color alone for information

---

## Pull Request Process

### 1. Prepare Your Changes

```bash
# Ensure you're on your feature branch
git checkout feature/your-feature-name

# Make your changes and test thoroughly

# Check git status
git status

# Add your changes
git add .

# Commit with descriptive message
git commit -m "type: Brief description

More detailed explanation if needed"
```

### 2. Update Your Branch

```bash
# Fetch latest changes from upstream
git fetch upstream

# Merge upstream changes
git merge upstream/main

# Resolve any conflicts if they occur

# Push to your fork
git push origin feature/your-feature-name
```

### 3. Create Pull Request

1. Go to your fork on GitHub
2. Click "Compare & pull request"
3. Fill out the pull request template:

```markdown
## Description
Brief description of changes

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Content update
- [ ] Documentation
- [ ] Other (specify)

## Changes Made
- List specific changes
- One per line

## Testing Done
- [ ] Tested in Chrome
- [ ] Tested in Firefox
- [ ] Tested on mobile
- [ ] Validated HTML
- [ ] Validated CSS
- [ ] Accessibility check

## Screenshots (if applicable)
Attach before/after screenshots

## Related Issues
Closes #issue-number
```

### 4. Pull Request Review

- Maintainers will review your PR
- Address any requested changes
- Make updates in your branch and push
- PR will be merged once approved

### 5. After Merge

```bash
# Switch back to main
git checkout main

# Pull latest changes
git pull upstream main

# Delete feature branch
git branch -d feature/your-feature-name

# Delete remote branch
git push origin --delete feature/your-feature-name
```

---

## Reporting Issues

### Before Reporting

1. **Search Existing Issues**: Check if issue already exists
2. **Try Latest Version**: Ensure you're using the latest code
3. **Gather Information**: Collect details about the issue

### Bug Report Template

```markdown
## Bug Description
Clear description of the bug

## Steps to Reproduce
1. Go to '...'
2. Click on '...'
3. Scroll down to '...'
4. See error

## Expected Behavior
What you expected to happen

## Actual Behavior
What actually happened

## Screenshots
If applicable, add screenshots

## Environment
- Browser: [e.g., Chrome 98]
- OS: [e.g., Windows 11]
- Device: [e.g., Desktop, iPhone 12]
- Screen Size: [e.g., 1920x1080]

## Additional Context
Any other relevant information
```

### Feature Request Template

```markdown
## Feature Description
Clear description of the feature

## Use Case
Why is this feature needed?

## Proposed Solution
How would you implement this?

## Alternatives Considered
What other approaches did you consider?

## Additional Context
Any mockups, examples, or references
```

---

## Development Workflow

### Typical Workflow

1. **Find or Create Issue**
   - Look for issues labeled "good first issue" or "help wanted"
   - Or create a new issue for your idea

2. **Discuss**
   - Comment on the issue to express interest
   - Wait for maintainer approval

3. **Develop**
   - Create branch from main
   - Make changes
   - Test thoroughly

4. **Submit PR**
   - Create pull request
   - Link to related issue
   - Respond to feedback

5. **Merge**
   - Once approved, your changes will be merged
   - Celebrate! 🎉

### Testing Checklist

Before submitting a PR, ensure:

- [ ] Code follows style guidelines
- [ ] No console errors
- [ ] All links work
- [ ] Responsive design works (mobile, tablet, desktop)
- [ ] Tested in Chrome, Firefox, Safari, Edge
- [ ] HTML validated (https://validator.w3.org/)
- [ ] CSS validated (https://jigsaw.w3.org/css-validator/)
- [ ] Accessibility checked (WAVE or Lighthouse)
- [ ] Changes don't break existing functionality

---

## Code Review Guidelines

### For Reviewers

When reviewing pull requests:

- **Be Respectful**: Provide constructive feedback
- **Be Specific**: Point to exact lines and suggest improvements
- **Be Timely**: Review within a reasonable timeframe
- **Test**: Actually test the changes locally

### For Contributors

When receiving feedback:

- **Be Open**: Accept feedback gracefully
- **Ask Questions**: If unclear, ask for clarification
- **Respond**: Address all comments
- **Be Patient**: Reviews take time

---

## Common Scenarios

### Adding a New Page

1. Create issue: "Add [Page Name] page"
2. Wait for approval
3. Create branch: `feature/add-page-name`
4. Create HTML file following existing structure
5. Update navigation in all pages
6. Test thoroughly
7. Submit PR with screenshots

### Fixing a Bug

1. Create issue: "Fix [Bug Description]"
2. Create branch: `fix/bug-description`
3. Fix the bug
4. Test the fix
5. Submit PR with before/after evidence

### Updating Content

1. Create issue: "Update [Content Description]"
2. Create branch: `content/update-description`
3. Make content changes
4. Proofread for accuracy
5. Submit PR

---

## Getting Help

If you need help:

1. **Check Documentation**: Review README.md, ARCHITECTURE.md, IMPLEMENTATION_GUIDE.md
2. **Search Issues**: Someone may have had the same question
3. **Ask in Issues**: Create an issue with your question
4. **Be Patient**: Maintainers will respond when available

---

## Recognition

Contributors will be recognized in:

- Pull request acknowledgments
- Release notes (for significant contributions)
- Community shout-outs

---

## License

By contributing, you agree that your contributions will be licensed under the same license as the project.

---

## Questions?

If you have questions about contributing, please create an issue with the "question" label.

Thank you for contributing to Grace E. Schools! 🎓

---

**Last Updated**: February 2026  
**Maintained By**: Grace E. Schools Web Team
