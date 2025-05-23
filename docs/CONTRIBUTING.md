# Contributing to Elevated Vector Automation Website

First off, thank you for considering contributing to the Elevated Vector Automation website project! Your help is appreciated in making this project even better.

This document provides guidelines for contributing to the project. Please read it carefully to ensure a smooth and effective contribution process.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
  - [Reporting Bugs](#reporting-bugs)
  - [Suggesting Enhancements](#suggesting-enhancements)
  - [Your First Code Contribution](#your-first-code-contribution)
  - [Pull Requests](#pull-requests)
- [Development Setup](#development-setup)
- [Style Guides](#style-guides)
- [Commit Message Guidelines](#commit-message-guidelines)

## Code of Conduct

This project and everyone participating in it is governed by a Code of Conduct. (We recommend adding a `CODE_OF_CONDUCT.md` file, perhaps based on the [Contributor Covenant](https://www.contributor-covenant.org/version/2/1/code_of_conduct/)). By participating, you are expected to uphold this code. Please report unacceptable behavior to [admin@elevatedvector.com](mailto:admin@elevatedvector.com).

## How Can I Contribute?

### Reporting Bugs

If you find a bug, please ensure the bug was not already reported by searching on GitHub under [Issues](https://github.com/elevatedvector/elevatedvector.com/issues).

If you're unable to find an open issue addressing the problem, [open a new one](https://github.com/elevatedvector/elevatedvector.com/issues/new). Be sure to include a **title and clear description**, as much relevant information as possible, and a **code sample or an executable test case** demonstrating the expected behavior that is not occurring.

Consider using the bug report template if available (e.g., `.github/ISSUE_TEMPLATE/bug_report.md`).

### Suggesting Enhancements

If you have an idea for an enhancement, please first discuss the change you wish to make via a GitHub issue. This allows for discussion and refinement of the idea before any code is written.

Please provide a clear description of the enhancement, why it would be beneficial, and any potential implementation ideas.

### Your First Code Contribution

Unsure where to begin contributing? You can start by looking through `good first issue` or `help wanted` issues:

- **Good first issues** - issues which should only require a few lines of code, and a test or two.
- **Help wanted issues** - issues which should be a bit more involved than `good first issue` issues.

### Pull Requests

1. **Fork the repository** to your own GitHub account.
2. **Clone your fork** to your local machine:

    ```bash
    git clone https://github.com/YOUR_USERNAME/elevatedvector.com.git
    cd elevatedvector.com
    ```

3. **Create a new branch** for your changes. Choose a descriptive branch name (e.g., `feature/new-contact-form`, `fix/header-alignment`):

    ```bash
    git checkout -b name-of-your-feature-or-fix
    ```

4. **Make your changes** locally. Ensure you follow the [Style Guides](#style-guides).
5. **Test your changes** thoroughly across different browsers and devices.
6. **Commit your changes** using a descriptive commit message that follows our [Commit Message Guidelines](#commit-message-guidelines).

    ```bash
    git add .
    git commit -m "feat: add responsive contact form"
    ```

7. **Push your changes** to your fork:

    ```bash
    git push origin name-of-your-feature-or-fix
    ```

8. **Open a Pull Request (PR)** from your fork's branch to the `main` branch of the `elevatedvector/elevatedvector.com` repository.
9. Provide a clear title and description for your PR, explaining the changes and referencing any related issues (e.g., "Closes #123").
10. The team will review your PR. Be prepared to discuss your changes and make adjustments if requested.
11. Once approved and merged, your contributions will be part of the website!

## Development Setup

Please refer to the [Getting Started](#getting-started) section in the main `README.md` for instructions on how to set up your local development environment.

## Style Guides

All contributions should adhere to the coding standards outlined in the `STYLE_GUIDE.md` file located in the `/docs` directory. This includes guidelines for HTML, CSS, JavaScript, and commit messages.

Key highlights:

- **HTML**: Semantic markup, 2-space indentation.
- **CSS**: BEM methodology, custom properties.
- **JavaScript**: ES6+ features, clear variable names.
- **Accessibility**: WCAG 2.1 AA compliance.
- **Performance**: Maintain Lighthouse scores of 90+.

## Commit Message Guidelines

We follow the [Conventional Commits](https://www.conventionalcommits.org/) specification. This helps in automating changelog generation and makes the commit history more readable.

Each commit message consists of a **header**, a **body** and a **footer**.
The header has a special format that includes a **type**, a **scope** and a **subject**:

```html
<type>(<scope>): <subject>
<BLANK LINE>
<body>
<BLANK LINE>
<footer>
```

**Type** must be one of the following:

- `feat`: A new feature
- `fix`: A bug fix
- `docs`: Documentation only changes
- `style`: Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc)
- `refactor`: A code change that neither fixes a bug nor adds a feature
- `perf`: A code change that improves performance
- `test`: Adding missing tests or correcting existing tests
- `chore`: Changes to the build process or auxiliary tools and libraries such as documentation generation

Example:

```curl
feat(contact): add client-side validation to contact form
```

```curl
fix(nav): ensure mobile menu closes on item click

Resolves issue where the mobile navigation menu would remain open
after a navigation item was clicked, obscuring page content.
```

---

Thank you for contributing!
