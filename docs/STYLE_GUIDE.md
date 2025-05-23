# Style Guide for Elevated Vector Automation Website

This style guide provides coding conventions and best practices for the Elevated Vector Automation website project. Adhering to these guidelines ensures consistency, readability, maintainability, and high-quality code.

## Table of Contents

- [General Principles](#general-principles)
- [HTML](#html)
  - [Markup](#markup)
  - [Semantics](#semantics)
  - [Accessibility (A11y)](#accessibility-a11y)
  - [Indentation and Formatting](#indentation-and-formatting)
- [CSS](#css)
  - [Methodology](#methodology)
  - [Naming Conventions](#naming-conventions)
  - [Custom Properties (Variables)](#custom-properties-variables)
  - [Formatting](#formatting)
  - [Units](#units)
  - [Performance](#performance)
- [JavaScript](#javascript)
  - [Syntax and Features](#syntax-and-features)
  - [Naming Conventions](#naming-conventions)
  - [Comments](#comments)
  - [Performance](#performance)
  - [Error Handling](#error-handling)
- [Accessibility (WCAG)](#accessibility-wcag)
- [Performance](#performance-1)
  - [Lighthouse Scores](#lighthouse-scores)
  - [Optimization Techniques](#optimization-techniques)
- [Images and Assets](#images-and-assets)
- [Commit Messages](#commit-messages)
- [Editor Configuration (Recommended)](#editor-configuration-recommended)

## General Principles

- **Clarity and Readability**: Write code that is easy to understand and follow.
- **Consistency**: Apply these guidelines uniformly across the entire codebase.
- **Maintainability**: Structure code in a way that facilitates future modifications and debugging.
- **Performance**: Optimize for fast loading times and smooth user experience.
- **Accessibility**: Ensure the website is usable by people of all abilities.

## HTML

### Markup

- Use HTML5 doctype: `<!DOCTYPE html>`.
- Use UTF-8 character encoding: `<meta charset="UTF-8">`.
- Include the viewport meta tag for responsiveness: `<meta name="viewport" content="width=device-width, initial-scale=1.0">`.

### Semantics

- Use semantic HTML5 elements appropriately (e.g., `<header>`, `<footer>`, `<nav>`, `<main>`, `<article>`, `<section>`, `<aside>`).
- Ensure a logical document outline with proper heading hierarchy (`<h1>` to `<h6>`). There should generally be only one `<h1>` per page.
- Use `<button>` for interactive controls, and `<a>` for navigation.

### Accessibility (A11y)

- Provide `alt` attributes for all `<img>` tags. If an image is purely decorative, use `alt=""`.
- Use ARIA attributes where necessary to enhance accessibility, but prioritize native HTML semantics.
- Ensure all interactive elements are keyboard accessible and focusable.
- Maintain sufficient color contrast.

### Indentation and Formatting

- Use 2 spaces for indentation. Do not use tabs.
- Write tags and attributes in lowercase.
- Quote attribute values (e.g., `class="example"`).

## CSS

### Methodology

- Follow the BEM (Block, Element, Modifier) methodology for naming CSS classes to create modular and maintainable styles.
  - Example: `.card__title--highlighted`

### Naming Conventions

- Class names should be lowercase, with words separated by hyphens (kebab-case) for BEM blocks and elements.
- Modifiers in BEM can use double hyphens (`--`) or single underscores (`_`) if preferred, but be consistent.

### Custom Properties (Variables)

- Utilize CSS custom properties (variables) for theming (colors, fonts, spacing) to promote consistency and easier updates.
  - Define global variables on the `:root` pseudo-class.
  - Example:

    ```css
    :root {
      --primary-color: #007bff;
      --font-family-main: 'Arial', sans-serif;
    }
    body {
      color: var(--primary-color);
      font-family: var(--font-family-main);
    }
    ```

### Formatting

- Use 2 spaces for indentation.
- Place each property-value pair on a new line.
- Include a space after the colon in property declarations (e.g., `color: #fff;`).
- End every declaration with a semicolon.
- Group related CSS rules together.

### Units

- Use `rem` or `em` for font sizes and spacing where scalability is desired.
- Use `px` for borders or when fixed pixel precision is necessary.
- Use percentages (`%`) for fluid layouts.

### Performance

- Avoid overly complex selectors.
- Minimize the use of `!important`.
- Group and minify CSS files for production.

## JavaScript

### Syntax and Features

- Use modern JavaScript (ES6+ features) where appropriate, ensuring browser compatibility or providing fallbacks if necessary for the target audience.
- Prefer `const` and `let` over `var`.
- Use strict mode: `'use strict';` at the beginning of your scripts or modules.

### Naming Conventions

- Variable and function names should be in `camelCase`.
- Class names should be in `PascalCase`.
- Constants (if any) can be in `UPPER_SNAKE_CASE`.

### Comments

- Use comments to explain complex logic, assumptions, or workarounds.
- Use JSDoc-style comments for functions and classes to describe parameters, return values, and purpose.

### Performance

- Avoid manipulating the DOM excessively. Batch DOM updates where possible.
- Be mindful of event listeners and remove them when elements are no longer needed to prevent memory leaks.
- Optimize loops and algorithms.

### Error Handling

- Implement basic error handling (e.g., `try...catch` blocks) for operations that might fail, especially asynchronous ones.

## Accessibility (WCAG)

- Strive for WCAG 2.1 Level AA compliance.
- Regularly test with accessibility tools (e.g., Lighthouse, axe DevTools) and assistive technologies (screen readers).
- Refer to the [W3C WCAG guidelines](https://www.w3.org/TR/WCAG21/) for detailed information.

## Performance

### Lighthouse Scores

- Aim for Lighthouse scores of 90+ across all categories (Performance, Accessibility, Best Practices, SEO).

### Optimization Techniques

- **Critical CSS**: Inline critical above-the-fold CSS if possible.
- **Efficient Animations**: Use hardware-accelerated CSS transforms and opacity for animations.
- **Optimized Images**: Use appropriate image formats (e.g., WebP with fallbacks), compress images, and use responsive images (`<picture>` element or `srcset` attribute).
- **Minimal JavaScript**: Use vanilla JavaScript where possible. Avoid heavy frameworks if not necessary for the project's scope.
- **Resource Hints**: Use `<link rel="preconnect">`, `<link rel="dns-prefetch">`, `<link rel="preload">` where appropriate.
- **Minification & Compression**: Minify HTML, CSS, and JavaScript files. Enable Gzip or Brotli compression on the server (GitHub Pages handles this automatically).

## Images and Assets

- Store images in `assets/images/`.
- Store icons (favicons, etc.) in `assets/icons/`.
- Store documents (PDFs, etc.) in `assets/documents/`.
- Optimize all assets for web use to reduce file sizes.

## Commit Messages

Follow the [Conventional Commits](https://www.conventionalcommits.org/) specification as outlined in `CONTRIBUTING.md`. This ensures a clean, understandable, and automated commit history.

## Editor Configuration (Recommended)

For consistency, consider using an `.editorconfig` file in the project root to define and maintain consistent coding styles between different editors and IDEs.

Example `.editorconfig` content:

```editorconfig
# EditorConfig is awesome: https://EditorConfig.org

# top-most EditorConfig file
root = true

[*]
indent_style = space
indent_size = 2
end_of_line = lf
charset = utf-8
trim_trailing_whitespace = true
insert_final_newline = true

[*.md]
trim_trailing_whitespace = false
```

---

By following this style guide, we can create a high-quality, maintainable, and performant website that effectively represents Elevated Vector Automation.
