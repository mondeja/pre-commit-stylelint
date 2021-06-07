stylelint mirror
================

Mirror of [stylelint][stylelint-link] package for [pre-commit][pre-commit-link].

### Using stylelint with pre-commit

Add this to your `.pre-commit-config.yaml`:

```yaml
- repo: https://github.com/mondeja/pre-commit-stylelint
  rev: ''  # Use the sha / tag you want to point at
  hooks:
    - id: stylelint
```

When using plugins with [stylelint][stylelint-link] you'll need to declare them
under `additional_dependencies`. For example:

```yaml
- repo: https://github.com/mondeja/pre-commit-stylelint
  rev: ''  # Use the sha / tag you want to point at
  hooks:
    - id: stylelint
      additional_dependencies:
        - stylelint-config-standard@21.0.0
        - stylelint-scss@3.19.0
```

By default only `*.js` files are taken into consideration. If you want to use
[stylelint][stylelint-link] on TypeScript codebases you need to start from this
template:

```yaml
-   repo: https://github.com/mondeja/pre-commit-stylelint
    rev: ''  # Use the sha / tag you want to point at
    hooks:
    -   id: stylelint
        files: \.[jt]sx?$  # *.js, *.jsx, *.ts and *.tsx
        types: [file]
```

[stylelint-link]: https://github.com/stylelint/stylelint
[pre-commit-link]: https://github.com/pre-commit/pre-commit