# Contributing

Thank you for helping improve Material Icons for Obsidian.

## Before opening a change

- Search existing issues and pull requests.
- Use the bug or feature request form for a new report.
- Keep each pull request focused on one change.
- Do not include vault content, personal data, generated `main.js`, or unrelated formatting changes.

## Local development

Use Node.js 20 or newer and npm:

```bash
npm ci
npm run lint
npm run build
npm audit
```

Test changes in a separate vault with only the development build enabled. Verify file and folder icons, folder expansion, rename/create/delete updates, plugin disable cleanup, pop-out windows, and a narrow/mobile layout when applicable.

## Pull requests

1. Fork the repository and create a branch from `main`.
2. Add or update tests and documentation when relevant.
3. Run all validation commands above.
4. Complete the pull request template and link related issues.

By participating, you agree to follow the [Code of Conduct](CODE_OF_CONDUCT.md).
