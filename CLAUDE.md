# CLAUDE.md — Coding Guidelines for AlphaDrop Website

## Project Overview

- This is the AlphaDrop website project.
- Follow all guidelines below when generating, editing, or reviewing code.

---

## General Principles

- Write clean, readable, and maintainable code. Prioritize clarity over cleverness.
- Keep functions and components small and single-purpose.
- Use meaningful, descriptive names for variables, functions, files, and classes.
- Avoid premature optimization — make it work correctly first, then optimize if needed.
- Don't repeat yourself (DRY), but don't over-abstract either. Duplicate code is better than the wrong abstraction.
- Delete dead code instead of commenting it out. Version control exists for a reason.
- Every file should have a single, clear responsibility.

---

## Project Structure

- Organize files by feature or route, not by file type.
- Keep assets (images, fonts, icons) in a dedicated `/assets` or `/public` directory.
- Shared/reusable components go in a `/components` directory.
- Page-level components or routes go in a `/pages` or `/views` directory.
- Utility functions go in a `/utils` or `/lib` directory.
- Keep the project root clean — config files only at the top level.

---

## HTML Best Practices

- Use semantic HTML elements (`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`).
- Every page must have exactly one `<h1>`. Use heading levels in order (h1 > h2 > h3).
- Always include `alt` attributes on images. Use descriptive text or empty `alt=""` for decorative images.
- Use `<button>` for actions and `<a>` for navigation. Never use `<div>` as a clickable element.
- Keep HTML structure flat where possible — avoid deeply nested divs.
- Always set the `lang` attribute on `<html>`.
- Include proper `<meta>` viewport and charset tags.

---

## CSS / Styling Best Practices

- Use a consistent methodology (e.g., BEM, utility-first, or CSS Modules).
- Prefer relative units (`rem`, `em`, `%`, `vw/vh`) over fixed `px` for responsive design.
- Design mobile-first: write base styles for small screens, then add `min-width` media queries.
- Avoid `!important` — fix specificity issues at the source instead.
- Use CSS custom properties (variables) for colors, spacing, fonts, and other design tokens.
- Keep z-index values managed — define a scale (e.g., 10, 20, 30) rather than arbitrary numbers.
- Minimize use of `position: absolute` and `float`. Prefer Flexbox and CSS Grid for layout.
- Ensure sufficient color contrast (minimum WCAG AA: 4.5:1 for text).

---

## JavaScript / TypeScript Best Practices

- Prefer `const` by default. Use `let` only when reassignment is needed. Never use `var`.
- Use arrow functions for callbacks and anonymous functions.
- Use template literals instead of string concatenation.
- Handle errors properly — never silently swallow exceptions.
- Avoid deeply nested callbacks — use async/await for asynchronous code.
- Keep DOM manipulation minimal. Batch reads and writes to avoid layout thrashing.
- Validate and sanitize all user input on both client and server.
- Never store secrets, API keys, or credentials in client-side code.
- Use strict equality (`===`) instead of loose equality (`==`).

---

## Accessibility (a11y)

- All interactive elements must be keyboard accessible (Tab, Enter, Escape).
- Use ARIA attributes only when native HTML semantics are insufficient.
- Ensure focus indicators are visible — never remove outlines without providing an alternative.
- Forms must have associated `<label>` elements for every input.
- Test with screen readers and keyboard-only navigation.
- Provide skip-to-content links for keyboard users.

---

## Performance

- Optimize and compress images. Use modern formats (WebP, AVIF) with fallbacks.
- Lazy-load images and heavy content below the fold.
- Minimize and bundle CSS/JS for production. Remove unused code (tree-shaking).
- Use `loading="lazy"` on images and iframes where appropriate.
- Avoid render-blocking resources — defer or async non-critical scripts.
- Cache static assets with proper cache headers.
- Keep the critical rendering path short — inline critical CSS if necessary.

---

## Responsive Design

- Support at minimum: mobile (320px+), tablet (768px+), and desktop (1024px+).
- Use fluid layouts with `max-width` containers rather than fixed widths.
- Test on real devices, not just browser dev tools.
- Touch targets should be at least 44x44px on mobile.
- Hide/show content responsibly — don't load heavy assets just to hide them on mobile.

---

## SEO

- Every page needs a unique `<title>` and `<meta name="description">`.
- Use descriptive, keyword-relevant URLs (e.g., `/about-us` not `/page2`).
- Use Open Graph and Twitter Card meta tags for social sharing.
- Implement structured data (JSON-LD) where applicable.
- Ensure the site is crawlable — use a `sitemap.xml` and `robots.txt`.
- All pages should be reachable through internal links.

---

## Security

- Sanitize all user inputs to prevent XSS and injection attacks.
- Use HTTPS everywhere — no mixed content.
- Set security headers: `Content-Security-Policy`, `X-Frame-Options`, `X-Content-Type-Options`.
- Never expose sensitive data in URLs, localStorage, or client-side code.
- Keep dependencies up to date and audit for known vulnerabilities regularly.
- Use `rel="noopener noreferrer"` on external links that use `target="_blank"`.

---

## Version Control

- Write clear, descriptive commit messages in imperative mood (e.g., "Add contact form validation").
- Keep commits small and focused — one logical change per commit.
- Use feature branches. Never commit directly to `main` or `master`.
- Review diffs before committing. Don't commit debug logs, console statements, or commented-out code.
- Include a `.gitignore` that excludes `node_modules/`, `.env`, build artifacts, and OS files.

---

## Code Quality

- Use a linter (e.g., ESLint) and formatter (e.g., Prettier) with consistent config.
- Run linting and formatting on save or as a pre-commit hook.
- Write code that doesn't need comments — but add comments when intent isn't obvious.
- Prefer early returns to reduce nesting.
- Keep files under 300 lines. If a file grows larger, consider splitting it.
- Test critical user flows and business logic. Don't aim for 100% coverage — aim for meaningful coverage.

---

## Dependencies

- Only add dependencies when they provide clear value over a simple custom solution.
- Audit new packages before adding: check maintenance status, bundle size, and security.
- Pin dependency versions or use lock files to ensure reproducible builds.
- Regularly update dependencies and check for deprecations.
- Prefer well-maintained, widely-used packages over obscure alternatives.
