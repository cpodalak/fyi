---
slug: everything-about-yaml
title: Everything about yaml
tags: [yaml, utt]
---

## Introduction
YAML ("YAML Ain’t Markup Language") is a human-readable data-serialization format commonly used for configuration files, data exchange, and templating. 

It emphasizes simplicity and readability, supports comments, anchors, and complex data structures.

### Official Site & Specification

- [YAML Official Site](https://yaml.org/)
- [YAML Specification](https://yaml.org/spec/)

### YAML Syntax & Features
- **Scalars**: Strings, numbers, booleans
- **Sequences**: Ordered lists (dash-prefixed)
- **Mappings**: Key–value pairs (colon-separated)
- **Comments**: Start with `#`
- **Anchors & Aliases**: Reuse/refer to nodes
- **Multiline & Folded Blocks**: Handle long text

### Basic Rules

- Indentation-sensitive (use spaces, not tabs)
- Case-sensitive keys
- Quotes optional unless special characters appear

### Simple YAML Examples

#### Flat Mapping
```yaml
server:
  host: example.com
  port: 8080
debug: true
```

#### Sequence of Mappings
```yaml
databases:
  - name: users
    host: db1.local
  - name: logs
    host: db2.local
```

#### Anchors & Aliases
```yaml
defaults: &def
  adapter: postgres
  timeout: 5000

production:
  <<: *def
  database: prod_db
```

#### Advanced Anchors & Aliases

Anchors and aliases can be used to create complex reusable structures, reducing duplication and improving maintainability.

```yaml
# Define reusable anchor for default settings
defaults: &defaults
  adapter: postgres
  timeout: 5000
  retries: 3

# Use the anchor in multiple environments
development:
  <<: *defaults
  database: dev_db
  debug: true

staging:
  <<: *defaults
  database: staging_db
  debug: false

production:
  <<: *defaults
  database: prod_db
  debug: false
  timeout: 10000  # Override specific values
```

#### Nested Anchors & Aliases

You can also nest anchors and aliases to handle more complex configurations.

```yaml
# Define base anchor for server settings
server_defaults: &server_defaults
  host: localhost
  port: 8080

# Define another anchor for database settings
db_defaults: &db_defaults
  adapter: postgres
  timeout: 5000

# Combine anchors in a service configuration
services:
  web:
    <<: *server_defaults
    endpoints:
      - /api/v1
      - /api/v2
  database:
    <<: *db_defaults
    database: app_db
    replicas: 3
```

These examples demonstrate how anchors and aliases can simplify YAML configurations by reusing and combining settings across different sections.

#### Multiline Strings
```yaml
description: |
  This is a multiline
  literal block.
notes: >
  This is folded into
  a single line.
```

## Templating with ytt
`ytt` is a simple YAML templating tool that lets you add logic to your YAML files without making them complex.

### Installation (macOS/Linux via Homebrew)
```bash
brew install ytt
```

### Basic Usage
[YTT Basics](https://ayling.fyi/docs/category/ytt-basics)

For more examples and documentation, visit [Carvel ytt](https://carvel.dev/ytt/).

#### Can YAML Import from Another YAML File?

YAML itself does not natively support importing data from another YAML file. However, this functionality can be achieved using external tools or libraries. Here are some approaches:

1. **Using Templating Tools**: Tools like `ytt` (covered earlier) allow you to merge or include YAML files during rendering.

2. **Custom Scripts**: You can write scripts in Python, JavaScript, or other languages to load multiple YAML files and combine them programmatically.

3. **Third-Party Libraries**: Some libraries, like `ruamel.yaml` in Python, can be extended to support custom import logic.

While YAML does not natively support imports, tools like `ytt` or custom scripts can provide this functionality. This approach ensures modular and maintainable configurations.

## VS Code Extensions for YAML

- **YAML by Red Hat**: Provides YAML language support.
- **YAML Support by GitHub**: Enhances YAML editing.
- **YAML Path**: Simplifies navigation in YAML files.
- **YAML Formatter and Tools**: Formats and validates YAML.

## Python YAML Libraries

- **PyYAML**: A popular library for parsing and writing YAML.
- **ruamel.yaml**: A more advanced YAML library with better support for YAML 1.2.

## Pros & Cons of YAML

### Pros
- Human-readable & concise
- Supports comments & anchors
- Widely adopted (e.g., Ansible, Kubernetes, CI configs)
- Flexible data structures

### Cons
- Indentation-sensitive: Can cause errors
- Ambiguous syntax (e.g., tabs vs. spaces, boolean parsing "on/off")
- No built-in schema (relies on JSON Schema or custom validators)
- Harder to parse with regex

## Best Practices

- Use **2 spaces per indent**; never tabs.
- Quote strings with special characters or leading zeros.
- Define and reuse anchors for repeated data.
- Validate against JSON Schema (many CLI tools exist).
- Keep documents small to maintain readability.
- Use CI linting (e.g., `yamllint`).

YAML remains a dominant choice for config files and data exchange due to its readability and expressiveness. With tools like `ytt` for templating, VS Code extensions for editing, and robust Python libraries for parsing, you can build, manage, and validate YAML-based configurations efficiently.

Keep best practices in mind to avoid common pitfalls, and happy coding!
