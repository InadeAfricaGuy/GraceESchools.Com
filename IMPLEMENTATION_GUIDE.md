# Grace E. Schools - Implementation Guide

## Quick Start Guide

This guide provides step-by-step instructions for developers to set up, modify, and deploy the Grace E. Schools website.

---

## Table of Contents

1. [Getting Started](#getting-started)
2. [Project Setup](#project-setup)
3. [Making Changes](#making-changes)
4. [Adding New Features](#adding-new-features)
5. [Testing Procedures](#testing-procedures)
6. [Deployment Process](#deployment-process)
7. [Troubleshooting](#troubleshooting)
8. [Code Style Guide](#code-style-guide)

---

## Getting Started

### What You'll Need

**Required:**
- A modern web browser (Chrome, Firefox, Safari, or Edge)
- A text editor or IDE (VS Code recommended)
- Basic knowledge of HTML, CSS, and JavaScript

**Optional:**
- Git for version control
- A local web server (Python, Node.js, or PHP)
- Browser developer tools

### Installation

1. **Clone the Repository**
   ```bash
   git clone https://github.com/[username]/GraceESchools.Com.git
   cd GraceESchools.Com
   ```

2. **Open in Browser**
   ```bash
   # Option 1: Direct file opening
   # Simply open index.html in your browser
   
   # Option 2: Using Python (recommended)
   python -m http.server 8000
   # Then visit http://localhost:8000
   
   # Option 3: Using Node.js
   npx http-server -p 8000
   # Then visit http://localhost:8000
   ```

3. **Verify Setup**
   - Homepage loads correctly
   - Navigation works across all pages
   - Styles are applied properly
   - No console errors

---

## Project Setup

### Directory Structure

```
GraceESchools.Com/
├── index.html          # Homepage
├── about.html          # About page
├── creche.html         # Creche program page
├── primary.html        # Primary school page
├── college.html        # High school/college page
├── contact.html        # Contact page
├── styles.css          # Main stylesheet
├── README.md           # Project overview
├── ARCHITECTURE.md     # Architecture documentation
└── IMPLEMENTATION_GUIDE.md  # This file
```

### Understanding the Structure

Each HTML file follows this pattern:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <!-- Meta tags -->
    <!-- Title -->
    <!-- Stylesheet link -->
</head>
<body>
    <!-- Navigation (same across all pages) -->
    <!-- Page-specific content -->
    <!-- Footer (same across all pages) -->
</body>
</html>
```

---

## Making Changes

### 1. Updating Content

#### Changing Text

**Example: Update school tagline**

1. Open the file containing the text
2. Find the text you want to change
3. Replace it with new text
4. Save the file
5. Refresh browser to see changes

```html
<!-- Before -->
<p class="tagline">Excellence in Education Since 1968</p>

<!-- After -->
<p class="tagline">Your New Tagline Here</p>
```

**Files to update for consistent changes:**
- Navigation tagline appears in all HTML files (6 files)
- Footer content appears in all HTML files (6 files)

#### Updating Contact Information

**Location**: `contact.html` and footer of all pages

```html
<!-- Contact page -->
<p>Email: info@graceeschools.com</p>
<p>Phone: +234 XXX XXX XXXX</p>

<!-- Footer (all pages) -->
<div class="footer-section">
    <h3>Contact Info</h3>
    <p>Email: info@graceeschools.com</p>
    <p>Phone: +234 XXX XXX XXXX</p>
</div>
```

### 2. Modifying Styles

#### Changing Colors

All colors are defined as CSS variables in `styles.css`:

```css
:root {
    --primary-color: #2563eb;        /* Change this value */
    --secondary-color: #10b981;      /* Change this value */
    --accent-color: #f59e0b;         /* Change this value */
    /* ... other colors ... */
}
```

**Example: Change primary color to purple**

```css
:root {
    --primary-color: #7c3aed;  /* Purple instead of blue */
}
```

All elements using `var(--primary-color)` will automatically update.

#### Adjusting Typography

**Change base font:**

```css
body {
    font-family: 'Your Preferred Font', sans-serif;
}
```

**Change heading sizes:**

```css
.hero-content h1 {
    font-size: 3.5rem;  /* Increase from 3rem */
}
```

#### Modifying Spacing

**Increase section padding:**

```css
.content-section {
    padding: 5rem 0;  /* Increase from 4rem */
}
```

### 3. Adding Images

#### Step 1: Prepare Images

1. Optimize images for web (recommended tools: TinyPNG, ImageOptim)
2. Use appropriate formats:
   - JPEG for photos
   - PNG for graphics with transparency
   - SVG for logos and icons

#### Step 2: Add Image Directory

```bash
mkdir images
```

#### Step 3: Add Image to HTML

```html
<img src="images/campus.jpg" 
     alt="Grace E. Schools Campus" 
     width="800" 
     height="600">
```

#### Step 4: Style Image (Optional)

```css
img {
    max-width: 100%;
    height: auto;
    border-radius: 8px;
}
```

---

## Adding New Features

### Adding a New Page

#### Step 1: Create HTML File

Create `new-page.html`:

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
    <!-- Copy navigation from any existing page -->
    <nav class="navbar">
        <!-- ... navigation content ... -->
    </nav>

    <!-- Your page content -->
    <section class="page-header">
        <div class="container">
            <h1>Page Title</h1>
            <p>Page subtitle</p>
        </div>
    </section>

    <!-- Copy footer from any existing page -->
    <footer>
        <!-- ... footer content ... -->
    </footer>
</body>
</html>
```

#### Step 2: Update Navigation

Add link to navigation menu in **all existing pages**:

```html
<ul class="nav-menu">
    <li><a href="index.html">Home</a></li>
    <li><a href="about.html">About Us</a></li>
    <li><a href="creche.html">Creche</a></li>
    <li><a href="primary.html">Primary</a></li>
    <li><a href="college.html">College</a></li>
    <li><a href="new-page.html">New Page</a></li>  <!-- Add this -->
    <li><a href="contact.html">Contact</a></li>
</ul>
```

#### Step 3: Update Active State

In `new-page.html`, add `class="active"` to the new page link:

```html
<li><a href="new-page.html" class="active">New Page</a></li>
```

### Adding a New Section to Existing Page

#### Example: Add Testimonials Section

```html
<!-- Add to index.html before CTA section -->
<section class="testimonials">
    <div class="container">
        <h2>What Parents Say</h2>
        <div class="testimonials-grid">
            <div class="testimonial-item">
                <p>"Excellent school with caring teachers..."</p>
                <h4>- Parent Name</h4>
            </div>
            <!-- More testimonials -->
        </div>
    </div>
</section>
```

#### Add Corresponding CSS

```css
.testimonials {
    padding: 4rem 0;
    background-color: var(--light-color);
}

.testimonials h2 {
    text-align: center;
    font-size: 2.5rem;
    margin-bottom: 3rem;
}

.testimonials-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 2rem;
}

.testimonial-item {
    background: var(--white);
    padding: 2rem;
    border-radius: 10px;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.testimonial-item p {
    font-style: italic;
    margin-bottom: 1rem;
}

.testimonial-item h4 {
    text-align: right;
    color: var(--primary-color);
}
```

### Adding Interactive JavaScript

#### Example: Form Validation

Add to `contact.html` before closing `</body>` tag:

```html
<script>
document.addEventListener('DOMContentLoaded', function() {
    const form = document.querySelector('.contact-form');
    
    form.addEventListener('submit', function(e) {
        e.preventDefault();
        
        // Get form values
        const name = document.getElementById('name').value;
        const email = document.getElementById('email').value;
        const message = document.getElementById('message').value;
        
        // Basic validation
        if (!name || !email || !message) {
            alert('Please fill in all required fields');
            return;
        }
        
        // Email validation
        const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
        if (!emailRegex.test(email)) {
            alert('Please enter a valid email address');
            return;
        }
        
        // Success message
        alert('Thank you! Your message has been sent.');
        form.reset();
    });
});
</script>
```

---

## Testing Procedures

### 1. Manual Testing

#### Before Each Change

- [ ] Open page in browser
- [ ] Check visual appearance
- [ ] Test navigation links
- [ ] Verify content displays correctly

#### After Making Changes

- [ ] Refresh browser (Ctrl+F5 or Cmd+Shift+R for hard refresh)
- [ ] Check changed elements
- [ ] Test any affected functionality
- [ ] Verify no errors in browser console (F12 → Console)

### 2. Cross-Browser Testing

Test in multiple browsers:

- [ ] Google Chrome
- [ ] Mozilla Firefox  
- [ ] Safari (if on Mac)
- [ ] Microsoft Edge

**How to test:**
1. Open site in each browser
2. Navigate through all pages
3. Check for visual inconsistencies
4. Test interactive elements

### 3. Responsive Design Testing

#### Using Browser DevTools

1. Open DevTools (F12)
2. Click device toggle icon (Ctrl+Shift+M)
3. Test different screen sizes:
   - Mobile: 375px, 414px
   - Tablet: 768px, 1024px
   - Desktop: 1366px, 1920px

#### What to Check

- [ ] Navigation adapts properly
- [ ] Text is readable (not too small)
- [ ] Buttons are clickable
- [ ] Images scale appropriately
- [ ] No horizontal scrolling
- [ ] Content doesn't overflow

### 4. Accessibility Testing

#### Keyboard Navigation

- [ ] Tab through all links and buttons
- [ ] Verify focus indicators are visible
- [ ] Ensure all interactive elements are reachable

#### Screen Reader Testing

**Using NVDA (Windows) or VoiceOver (Mac):**

- [ ] Page title is announced
- [ ] Headings are in logical order
- [ ] Links have descriptive text
- [ ] Images have alt text
- [ ] Form labels are associated with inputs

#### Automated Testing Tools

**Browser Extensions:**
- WAVE (Web Accessibility Evaluation Tool)
- axe DevTools
- Lighthouse (built into Chrome)

**How to use Lighthouse:**
1. Open Chrome DevTools (F12)
2. Click "Lighthouse" tab
3. Select "Accessibility"
4. Click "Generate report"
5. Fix any issues found

### 5. Performance Testing

#### Using Lighthouse

1. Open Chrome DevTools
2. Navigate to Lighthouse tab
3. Select "Performance"
4. Click "Generate report"

**Target Scores:**
- Performance: > 90
- Accessibility: > 90
- Best Practices: > 90
- SEO: > 90

#### Common Issues and Fixes

| Issue | Solution |
|-------|----------|
| Large images | Optimize and compress images |
| Render-blocking CSS | Use critical CSS inline |
| Unused CSS | Remove unused styles |
| Large DOM size | Simplify HTML structure |

### 6. Validation

#### HTML Validation

1. Visit [W3C HTML Validator](https://validator.w3.org/)
2. Upload HTML file or enter URL
3. Fix any errors or warnings

#### CSS Validation

1. Visit [W3C CSS Validator](https://jigsaw.w3.org/css-validator/)
2. Upload CSS file or enter URL
3. Fix any errors or warnings

---

## Deployment Process

### Pre-Deployment Checklist

- [ ] All changes tested locally
- [ ] Cross-browser testing complete
- [ ] Responsive design verified
- [ ] HTML validated (no errors)
- [ ] CSS validated (no errors)
- [ ] Accessibility checks passed
- [ ] Performance optimized
- [ ] Contact information updated
- [ ] All links working
- [ ] Forms tested (if applicable)

### Deployment Methods

#### Method 1: GitHub Pages

1. **Commit Changes**
   ```bash
   git add .
   git commit -m "Description of changes"
   git push origin main
   ```

2. **Enable GitHub Pages**
   - Go to repository settings
   - Scroll to "Pages" section
   - Select branch: `main`
   - Select folder: `/ (root)`
   - Click "Save"

3. **Access Site**
   - URL: `https://[username].github.io/[repository]`
   - Wait 1-2 minutes for deployment

#### Method 2: Netlify

1. **Option A: Drag and Drop**
   - Visit [netlify.com](https://netlify.com)
   - Drag project folder to deploy area
   - Site goes live immediately

2. **Option B: Git Integration**
   - Connect GitHub repository
   - Configure build settings (leave empty for static site)
   - Automatic deployments on git push

#### Method 3: Traditional Hosting (FTP)

1. **Connect via FTP**
   ```
   Host: ftp.yourhost.com
   Username: your-username
   Password: your-password
   ```

2. **Upload Files**
   - Upload all HTML files
   - Upload styles.css
   - Upload any images folder
   - Ensure index.html is in root

3. **Set Permissions**
   - Files: 644
   - Directories: 755

### Post-Deployment Verification

- [ ] Visit live URL
- [ ] Test all pages load
- [ ] Check navigation works
- [ ] Verify forms (if applicable)
- [ ] Test on mobile device
- [ ] Check HTTPS is working
- [ ] Verify custom domain (if applicable)

---

## Troubleshooting

### Common Issues

#### Issue: Styles Not Loading

**Symptoms:** Page shows unstyled HTML

**Solutions:**
1. Check CSS file path in HTML:
   ```html
   <link rel="stylesheet" href="styles.css">
   ```
2. Ensure styles.css is in same directory
3. Clear browser cache (Ctrl+F5)
4. Check for CSS syntax errors

#### Issue: Links Not Working

**Symptoms:** Clicking links shows 404 error

**Solutions:**
1. Verify file names match exactly (case-sensitive)
2. Check file paths are correct
3. Ensure files exist in correct location
4. Use relative paths, not absolute

#### Issue: Images Not Displaying

**Symptoms:** Broken image icons

**Solutions:**
1. Check image path is correct
2. Verify image file exists
3. Check file extension matches (jpg vs jpeg)
4. Ensure proper case in filename
5. Check image file isn't corrupted

#### Issue: Mobile Layout Broken

**Symptoms:** Content overflows or looks wrong on mobile

**Solutions:**
1. Add viewport meta tag:
   ```html
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   ```
2. Check media queries in CSS
3. Use responsive units (%, rem) not fixed pixels
4. Test with browser DevTools device mode

#### Issue: Form Not Submitting

**Symptoms:** Nothing happens when clicking submit

**Solutions:**
1. Check JavaScript console for errors
2. Verify form has action attribute (if backend exists)
3. Ensure button type is "submit"
4. Check JavaScript event listeners
5. Test without JavaScript to isolate issue

### Getting Help

1. **Check Console**: F12 → Console tab for errors
2. **Validate Code**: Use W3C validators
3. **Search Error Messages**: Copy exact error to Google
4. **Check Documentation**: Review ARCHITECTURE.md
5. **Review Git History**: See what changed recently

---

## Code Style Guide

### HTML Guidelines

#### 1. Indentation
- Use 4 spaces for indentation
- Indent child elements

```html
<!-- Good -->
<div class="container">
    <h1>Title</h1>
    <p>Content</p>
</div>

<!-- Avoid -->
<div class="container">
<h1>Title</h1>
<p>Content</p>
</div>
```

#### 2. Attribute Order
1. class
2. id
3. data-*
4. src, href, type
5. title, alt
6. other attributes

```html
<a class="btn btn-primary" 
   id="submit-btn" 
   href="contact.html" 
   title="Contact Us">
   Contact
</a>
```

#### 3. Semantic HTML
Use appropriate HTML5 elements:

```html
<!-- Good -->
<nav>...</nav>
<main>...</main>
<article>...</article>
<section>...</section>

<!-- Avoid -->
<div class="nav">...</div>
<div class="main">...</div>
```

### CSS Guidelines

#### 1. Organization
Group related styles together:

```css
/* Navigation */
.navbar { }
.nav-menu { }
.nav-menu a { }

/* Hero Section */
.hero { }
.hero-content { }
.hero-buttons { }
```

#### 2. Naming Conventions
- Use lowercase with hyphens
- Be descriptive and specific
- Follow BEM-like patterns where helpful

```css
/* Good */
.level-card { }
.level-card__icon { }
.level-card--primary { }

/* Avoid */
.Card { }
.lc { }
.levelCard { }
```

#### 3. Property Order
1. Positioning (position, top, right, bottom, left, z-index)
2. Box model (display, width, height, margin, padding)
3. Typography (font, color, text)
4. Visual (background, border, box-shadow)
5. Misc (cursor, overflow, etc.)

```css
.element {
    /* Positioning */
    position: relative;
    z-index: 10;
    
    /* Box model */
    display: flex;
    width: 100%;
    padding: 1rem;
    margin-bottom: 2rem;
    
    /* Typography */
    font-size: 1.2rem;
    color: var(--text-color);
    
    /* Visual */
    background-color: var(--white);
    border-radius: 8px;
}
```

### JavaScript Guidelines

#### 1. Use Modern JavaScript
- Use const/let instead of var
- Use arrow functions
- Use template literals

```javascript
// Good
const userName = 'John';
const greeting = `Hello, ${userName}!`;

// Avoid
var userName = 'John';
var greeting = 'Hello, ' + userName + '!';
```

#### 2. Event Listeners
Wait for DOM to load:

```javascript
document.addEventListener('DOMContentLoaded', function() {
    // Your code here
});
```

#### 3. Comments
Add comments for complex logic:

```javascript
// Validate email format using regex
const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
if (!emailRegex.test(email)) {
    // Show error if invalid
    alert('Please enter a valid email address');
    return;
}
```

### Git Commit Guidelines

#### Commit Message Format
```
Type: Brief description (50 chars or less)

More detailed explanation if needed (wrap at 72 chars)
```

#### Types
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting, no logic change)
- `refactor`: Code refactoring
- `content`: Content updates

#### Examples
```bash
git commit -m "feat: Add testimonials section to homepage"
git commit -m "fix: Correct mobile navigation alignment"
git commit -m "docs: Update installation instructions"
git commit -m "content: Update contact phone number"
```

---

## Quick Reference

### Common Tasks

| Task | Command/Action |
|------|----------------|
| Start local server | `python -m http.server 8000` |
| Open DevTools | `F12` or `Ctrl+Shift+I` |
| Hard refresh | `Ctrl+F5` or `Cmd+Shift+R` |
| Mobile view | `Ctrl+Shift+M` in DevTools |
| Validate HTML | https://validator.w3.org/ |
| Validate CSS | https://jigsaw.w3.org/css-validator/ |

### File Locations

| Content | File(s) |
|---------|---------|
| Homepage | index.html |
| Navigation | All .html files |
| Footer | All .html files |
| All styles | styles.css |
| Contact info | contact.html + footer |

### CSS Variables

```css
var(--primary-color)        /* Blue */
var(--secondary-color)      /* Green */
var(--accent-color)         /* Orange */
var(--creche-color)         /* Pink */
var(--primary-school-color) /* Purple */
var(--college-color)        /* Cyan */
var(--dark-color)          /* Dark gray */
var(--text-color)          /* Medium gray */
```

---

## Next Steps

After completing this guide:

1. **Practice**: Make small changes to get comfortable
2. **Experiment**: Try different colors, layouts, content
3. **Review**: Read ARCHITECTURE.md for deeper understanding
4. **Deploy**: Push your site live when ready
5. **Maintain**: Regular updates keep content fresh

---

**Questions?** Review the ARCHITECTURE.md file or check the troubleshooting section.

**Last Updated**: February 2026  
**Version**: 1.0
