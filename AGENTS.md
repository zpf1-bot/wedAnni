# AGENTS.md - Agentic Coding Guidelines

## Project Overview

This is a **static wedding anniversary webpage** containing:
- A single HTML file (`index.html`) with embedded CSS and JavaScript
- Images in `/images/` directory
- Background music in `/music/` directory
- No build system, no package manager, no tests

## Build/Lint/Test Commands

This is a **static HTML project** - no build commands required.

### Running the Project

Simply open `index.html` in a browser, or serve it locally:

```bash
# Using Python
python -m http.server 8000

# Using PHP
php -S localhost:8000

# Using Node.js (if available)
npx serve .
```

### Linting

No linting configured. For HTML validation, you can use:
- W3C HTML Validator: https://validator.w3.org/

### Testing

No test framework configured. Manual testing by:
1. Opening `index.html` in browser
2. Testing all interactive features (heart clicks, music player, timer, sync code)
3. Verifying responsive design on different screen sizes

### Single Test Command

N/A - no automated tests exist.

## Code Style Guidelines

### General

This is a **simple static HTML project**. Avoid overcomplicating. Keep changes minimal and focused.

### HTML Structure

- Use semantic HTML5 elements (`<header>`, `<main>`, `<section>`, `<footer>`)
- Always include `lang` attribute on `<html>` tag
- Include proper meta tags for charset and viewport
- Use lowercase for tags and attributes

### CSS

- Embedded in `<style>` tag within `<head>`
- Use CSS custom properties (variables) for colors and sizes
- Follow mobile-first responsive design with `@media` queries
- Use meaningful class names (e.g., `.photo-frame`, `.heart-btn`)
- Animations should be smooth (use `ease` or `ease-out`)
- Use `rem` for font sizes, `px` for precise pixel values

### JavaScript

- Embedded in `<script>` tag at end of `<body>`
- Use vanilla JavaScript only (no frameworks)
- Use `const` by default, `let` when mutation needed
- Use meaningful variable names in English or follow existing patterns
- Use `===` for comparisons (strict equality)
- Add error handling for browser APIs (localStorage, audio, clipboard)
- Use `localStorage` for persisting user data across sessions

### Naming Conventions

| Element | Convention | Example |
|---------|------------|---------|
| CSS classes | kebab-case | `.heart-btn`, `.photo-frame` |
| JavaScript functions | camelCase | `clickHeart()`, `createFirework()` |
| JavaScript variables | camelCase | `husbandClicks`, `totalClicks` |
| Constants | camelCase | `weddingDate` |

### Error Handling

- Wrap browser API calls in try-catch blocks
- Provide fallback for features that may fail (autoplay, clipboard)
- Use optional chaining and nullish coalescing where appropriate

### Accessibility

- Include `alt` attributes for all images
- Use semantic buttons for interactions (not `<div>` with onclick)
- Ensure sufficient color contrast
- Make music player keyboard accessible

## File Organization

```
wedAnni/
├── index.html      # Main page (HTML + CSS + JS)
├── images/         # Photo assets
│   ├── husband.jpg
│   └── wife.jpg
└── music/         # Audio assets
    └── lucky.mp3
```

## Common Tasks

### Adding a New Effect
1. Add CSS animation in `<style>` section (keep alphabetical order)
2. Add JavaScript function in `<script>` section
3. Call function on appropriate user action

### Adding New Photos
1. Add image file to `images/` directory
2. Add `<img>` tag in appropriate section
3. Add styling if needed

### Modifying the Wedding Date
Edit the `weddingDate` constant in JavaScript (line ~499):
```javascript
const weddingDate = new Date('2025-03-09 00:00:00');
```

## Notes

- This is a personal project - a wedding anniversary celebration page
- The page tracks "love clicks" per person with localStorage
- Supports sync codes via URL parameters to share click counts between partners
- Features include: floating hearts, click effects, fireworks, music player, countdown timer
