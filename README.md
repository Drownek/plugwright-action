# Paperwright Action

The official GitHub Action for running [Paperwright](https://github.com/Drownek/paperwright) end-to-end tests for your Paper/Spigot plugins.

This composite action automatically sets up Java, Node.js, and runs your test suite in one simple step.

## Usage

Add this to your `.github/workflows/e2e.yml`:

```yaml
name: E2E Tests
on: [push, pull_request]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: drownek/paperwright-action@v1
```

## Inputs

| Name                | Description                                  | Default           |
|---------------------|----------------------------------------------|-------------------|
| `java-version`      | Java version to use for building the plugin. | `17`              |
| `java-distribution` | Java distribution to use.                    | `temurin`         |
| `node-version`      | Node.js version to use for tests.            | `16`              |
| `gradle-args`       | Additional arguments to pass to gradle.      | `paperwrightTest` |

### Example with custom inputs:

```yaml
    steps:
      - uses: actions/checkout@v4
      - uses: drownek/paperwright-action@v1
        with:
          java-version: '21'
          node-version: '20'
```

## License
MIT
