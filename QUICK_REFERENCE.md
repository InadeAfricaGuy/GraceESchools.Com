# Grace E. Schools - Quick Reference Guide

This quick reference guide provides at-a-glance information for common tasks and configurations.

---

## 📁 Project Structure

```
GraceESchools.Com/
├── index.html              # Homepage
├── about.html              # About page
├── creche.html            # Creche program
├── primary.html           # Primary school
├── college.html           # High school/college
├── contact.html           # Contact & admissions
├── styles.css             # All styles
├── README.md              # Project overview
├── ARCHITECTURE.md        # Architecture guide
├── IMPLEMENTATION_GUIDE.md # Implementation guide
├── CONTRIBUTING.md        # Contributing guide
└── QUICK_REFERENCE.md     # This file
```

---

## 🎨 Color Palette

| Color | Variable | Hex Code | Usage |
|-------|----------|----------|-------|
| Primary Blue | `--primary-color` | #2563eb | Navigation, headings, buttons |
| Secondary Green | `--secondary-color` | #10b981 | Gradients, accents |
| Accent Orange | `--accent-color` | #f59e0b | Call-to-action buttons |
| Creche Pink | `--creche-color` | #ec4899 | Creche program cards |
| Primary Purple | `--primary-school-color` | #8b5cf6 | Primary school cards |
| College Cyan | `--college-color` | #0891b2 | College/high school cards |
| Dark Gray | `--dark-color` | #1f2937 | Headers, footer |
| Light Gray | `--light-color` | #f3f4f6 | Section backgrounds |
| Text Gray | `--text-color` | #374151 | Body text |
| White | `--white` | #ffffff | Backgrounds |

**Usage in CSS:**
```css
.my-element {
    color: var(--primary-color);
    background-color: var(--light-color);
}
```

---

## 📐 Typography Scale

| Element | Desktop | Mobile | Usage |
|---------|---------|--------|-------|
| Hero H1 | 3rem | 2rem | Homepage hero title |
| Page H1 | 3rem | 2rem | Page headers |
| Section H2 | 2.5rem | 2.5rem | Section titles |
| Card H3 | 1.8rem | 1.8rem | Card titles |
| Value H3 | 1.5rem | 1.5rem | Value items |
| Intro Text | 1.1rem | 1.1rem | Introduction paragraphs |
| Body Text | 1rem | 1rem | Default text |
| Small Text | 0.9rem | 0.9rem | Taglines, meta info |

---

## 🔧 Common CSS Classes

### Layout Classes
```css
.container           /* Max-width container (1200px) */
.page-header         /* Page header with gradient */
.content-section     /* Standard content section */
.hero                /* Homepage hero section */
.intro               /* Introduction section */
.cta                 /* Call-to-action section */
```

### Component Classes
```css
.navbar              /* Navigation bar */
.nav-menu            /* Navigation menu list */
.level-card          /* Educational level card */
.creche-card         /* Creche program card */
.primary-card        /* Primary school card */
.college-card        /* College/high school card */
.value-item          /* Core value item */
.feature-item        /* Feature highlight box */
.stat-item           /* Statistics display */
```

### Button Classes
```css
.btn                 /* Base button */
.btn-primary         /* Orange accent button */
.btn-secondary       /* White button with blue text */
.btn-outline         /* Transparent with border */
.btn-large           /* Larger button */
```

### Grid Classes
```css
.levels-grid         /* Educational levels grid */
.values-grid         /* Core values grid */
.feature-grid        /* Feature items grid */
.stats               /* Statistics grid */
.testimonials-grid   /* Testimonials grid (future) */
```

---

## ⚡ Quick Commands

### Local Development

```bash
# Clone repository
git clone https://github.com/InadeAfricaGuy/GraceESchools.Com.git
cd GraceESchools.Com

# Start local server (Python)
python -m http.server 8000

# Start local server (Node.js)
npx http-server -p 8000

# Start local server (PHP)
php -S localhost:8000

# Open in browser
# Visit http://localhost:8000
```

### Git Workflow

```bash
# Create new branch
git checkout -b feature/your-feature

# Check status
git status

# Stage all changes
git add .

# Commit changes
git commit -m "feat: Your commit message"

# Push to remote
git push origin feature/your-feature

# Pull latest changes
git pull origin main
```

### Testing

```bash
# Check HTML validity
# Visit: https://validator.w3.org/

# Check CSS validity
# Visit: https://jigsaw.w3.org/css-validator/

# Run Lighthouse (Chrome DevTools)
# F12 → Lighthouse → Generate Report
```

---

## 📱 Responsive Breakpoints

```css
/* Mobile: Default (320px - 767px) */
/* No media query needed */

/* Tablet and below: 768px and down */
@media (max-width: 768px) {
    /* Adjustments for tablet and mobile */
}

/* Desktop: 769px and up */
/* Uses default styles */
```

### Common Responsive Patterns

```css
/* Stack columns on mobile */
.levels-grid {
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
}

/* Smaller text on mobile */
@media (max-width: 768px) {
    .hero-content h1 {
        font-size: 2rem;  /* from 3rem */
    }
}

/* Vertical buttons on mobile */
@media (max-width: 768px) {
    .hero-buttons {
        flex-direction: column;
    }
}
```

---

## 🎯 Common Tasks

### Change Website Colors

**File:** `styles.css`

```css
:root {
    --primary-color: #YOUR_COLOR;      /* Change this */
    --secondary-color: #YOUR_COLOR;    /* Change this */
    --accent-color: #YOUR_COLOR;       /* Change this */
}
```

### Update Contact Information

**Files:** `contact.html` + all page footers

```html
<!-- contact.html -->
<p>Email: newemail@example.com</p>
<p>Phone: +234 XXX XXX XXXX</p>

<!-- Footer (all pages) -->
<div class="footer-section">
    <h3>Contact Info</h3>
    <p>Email: newemail@example.com</p>
    <p>Phone: +234 XXX XXX XXXX</p>
</div>
```

### Add New Navigation Link

**Files:** All `.html` files (6 files)

```html
<ul class="nav-menu">
    <li><a href="index.html">Home</a></li>
    <li><a href="about.html">About Us</a></li>
    <li><a href="creche.html">Creche</a></li>
    <li><a href="primary.html">Primary</a></li>
    <li><a href="college.html">College</a></li>
    <li><a href="new-page.html">New Page</a></li>  <!-- Add -->
    <li><a href="contact.html">Contact</a></li>
</ul>
```

### Change School Tagline

**Files:** All `.html` files (6 files)

```html
<div class="logo">
    <h1>Grace E. Schools</h1>
    <p class="tagline">Your New Tagline Here</p>  <!-- Change -->
</div>
```

### Update Statistics

**File:** `index.html`

```html
<div class="stats">
    <div class="stat-item">
        <h3>60+</h3>  <!-- Change number -->
        <p>Years of Excellence</p>
    </div>
    <!-- More stats -->
</div>
```

---

## 🐛 Troubleshooting

### Issue: Styles not loading
```bash
# Check file path in HTML
<link rel="stylesheet" href="styles.css">

# Clear browser cache
Ctrl + F5 (Windows/Linux)
Cmd + Shift + R (Mac)

# Check for CSS syntax errors
# Validate at: https://jigsaw.w3.org/css-validator/
```

### Issue: Links not working
```bash
# Ensure file exists
ls -l filename.html

# Check file name (case-sensitive)
about.html ≠ About.html

# Use relative paths
<a href="about.html">  ✓ Good
<a href="/about.html"> ✗ May not work locally
```

### Issue: Changes not visible
```bash
# Hard refresh browser
Ctrl + F5

# Check if editing correct file
# Look for unique content to confirm

# Check browser console for errors
F12 → Console tab
```

### Issue: Mobile layout broken
```html
<!-- Add viewport meta tag -->
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<!-- Check media queries in CSS -->
@media (max-width: 768px) { }
```

---

## 🚀 Deployment Checklist

- [ ] Test all pages load correctly
- [ ] Verify all links work (internal and external)
- [ ] Test contact form (if backend implemented)
- [ ] Check responsive design (mobile, tablet, desktop)
- [ ] Validate HTML (https://validator.w3.org/)
- [ ] Validate CSS (https://jigsaw.w3.org/css-validator/)
- [ ] Test browser compatibility (Chrome, Firefox, Safari, Edge)
- [ ] Check accessibility (Lighthouse or WAVE)
- [ ] Verify meta tags and titles
- [ ] Test page load speed (< 3 seconds)
- [ ] Check HTTPS is working
- [ ] Test on real mobile device

---

## 📚 Documentation Links

| Document | Purpose |
|----------|---------|
| [README.md](README.md) | Project overview and introduction |
| [ARCHITECTURE.md](ARCHITECTURE.md) | Detailed architecture guide |
| [IMPLEMENTATION_GUIDE.md](IMPLEMENTATION_GUIDE.md) | Step-by-step implementation |
| [CONTRIBUTING.md](CONTRIBUTING.md) | How to contribute |
| [QUICK_REFERENCE.md](QUICK_REFERENCE.md) | This quick reference |

---

## 🔗 Useful Links

### Validation Tools
- HTML Validator: https://validator.w3.org/
- CSS Validator: https://jigsaw.w3.org/css-validator/
- Accessibility Checker (WAVE): https://wave.webaim.org/

### Testing Tools
- Chrome DevTools: F12
- Lighthouse: Chrome DevTools → Lighthouse
- Responsive Design Mode: Ctrl+Shift+M

### Resources
- MDN Web Docs: https://developer.mozilla.org/
- CSS Tricks: https://css-tricks.com/
- Can I Use: https://caniuse.com/

### Hosting Options
- GitHub Pages: https://pages.github.com/
- Netlify: https://netlify.com/
- Vercel: https://vercel.com/

---

## 💡 Tips & Best Practices

### Performance
- Optimize images before uploading
- Use appropriate image formats (JPEG for photos, PNG for graphics)
- Minimize CSS/JS files for production
- Use CSS instead of images where possible

### Accessibility
- Always add alt text to images
- Use semantic HTML elements
- Ensure keyboard navigation works
- Maintain proper heading hierarchy (h1 → h2 → h3)
- Ensure color contrast meets WCAG standards

### SEO
- Unique title for each page
- Descriptive meta descriptions
- Use semantic HTML
- Descriptive link text (avoid "click here")
- Proper heading structure

### Maintenance
- Test after every change
- Keep backups of working code
- Document custom changes
- Update content regularly
- Monitor browser console for errors

---

## 📞 Getting Help

1. **Check this quick reference first**
2. **Review detailed guides:**
   - [IMPLEMENTATION_GUIDE.md](IMPLEMENTATION_GUIDE.md) for how-to
   - [ARCHITECTURE.md](ARCHITECTURE.md) for technical details
3. **Search existing issues** on GitHub
4. **Create new issue** if problem persists
5. **Ask in discussions** for general questions

---

**Last Updated**: February 2026  
**Version**: 1.0  

**Need more details?** See [ARCHITECTURE.md](ARCHITECTURE.md) or [IMPLEMENTATION_GUIDE.md](IMPLEMENTATION_GUIDE.md)
