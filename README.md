# Harper Prompts

Harper Prompts is an AI-assisted development framework inspired by the LLM codegen workflow described in [this blog post](https://harper.blog/2025/02/16/my-llm-codegen-workflow-atm/). It provides a structured approach to software project planning, specification development, and implementation through a series of interactive commands.

## Installation

This is a CLI agent extension. Install it in your Qwen/AI CLI agent:

```bash
# Installation location
~/.qwen/extensions/harper-commands/
```

## Quick Start

```bash
# 1. Start with your idea
/project:spec mobile app that tracks personal reading habits

# 2. Compile the specification
/project:spec-create

# 3. Generate implementation plan (with TDD)
/project:plan --ttd

# 4. Create tracking checklist
/project:todo

# 5. Execute the plan
/project:execute ttd-plan.md

# 6. Review your code
/review:code
/review:security
```

## Core Philosophy

This framework is built on principles of LLM-assisted development:

- **Iterative Specification Development** through conversational refinement
- **Small, Incremental Steps** breaking projects into testable chunks
- **Comprehensive Documentation** maintaining clear specs and tracking
- **AI-Assisted Implementation** using code generation tools effectively
- **Quality Assurance** built-in validation and security reviews

## Command Reference

### 🎯 Planning Commands

#### `/project:spec <idea>`

Interactive questioning to develop detailed specifications. Asks one question at a time.

```bash
/project:spec mobile app that tracks personal reading habits
```

#### `/project:spec-create`

Compiles brainstorming findings into a developer-ready specification.

#### `/project:plan [--ttd]`

Generates implementation prompts for code generation LLMs.

```bash
/project:plan        # Regular development
/project:plan --ttd  # Test-driven development
```

#### `/project:todo`

Creates a thorough `todo.md` checklist file.

#### `/project:execute <plan-file>`

Executes prompts from a generated plan file in sequence.

```bash
/project:execute plan.md
/project:execute ttd-plan.md
```

### ✅ Validation & Setup Commands

#### `/project:validate`

Validates that required files exist before proceeding.

```bash
/project:validate                # Full validation
/project:validate --check-spec   # Check spec only
/project:validate --check-plan   # Check plan only
```

#### `/project:setup-lang <language>`

Configures language-specific standards and tooling.

```bash
/project:setup-lang python
/project:setup-lang typescript
/project:setup-lang go
```

**Supported Languages:**

- Python (uv, pytest, ruff, mypy, black)
- JavaScript/TypeScript (npm/yarn/pnpm, jest/vitest, eslint, prettier)
- Go (modules, testing, golangci-lint, gofmt)
- Rust (cargo, clippy, rustfmt)
- Java (Maven/Gradle, JUnit)

### 🔍 Code Review Commands

#### `/review:code`

Reviews new code with fresh eyes to find bugs and issues.

#### `/review:missing-tests`

Identifies missing test cases and creates GitHub issues.

#### `/review:security`

Performs comprehensive security review:

- Authentication & Authorization
- Input Validation & Injection vulnerabilities
- Data Protection
- API Security
- Dependency vulnerabilities

### 🛡️ Quality Assurance Commands

#### `/project:error-handling [--audit-only]`

Reviews and improves error handling throughout the codebase.

```bash
/project:error-handling              # Review and implement
/project:error-handling --audit-only # Report only
```

### ⚙️ Configuration (Optional)

#### `/project:config-create [language]`

Creates an optional `harper.config.toml` file to customize behavior.

```bash
/project:config-create              # Full config
/project:config-create --minimal    # Minimal config
/project:config-create python       # Python preset
/project:config-create typescript   # TypeScript preset
```

**Note:** Configuration is completely optional! All commands work with sensible defaults.

## Typical Workflow

### 1. Project Setup

```bash
# Optional: Configure language-specific settings
/project:setup-lang python
```

### 2. Idea to Specification

```bash
# Interactive refinement
/project:spec [your idea]

# Compile into spec
/project:spec-create

# Validate everything
/project:validate
```

### 3. Planning

```bash
# Generate implementation plan
/project:plan --ttd

# Create tracking checklist
/project:todo
```

### 4. Implementation

```bash
# Execute prompts sequentially
/project:execute ttd-plan.md
```

### 5. Quality Assurance

```bash
# Review code
/review:code

# Check security
/review:security

# Audit error handling
/project:error-handling --audit-only

# Find missing tests
/review:missing-tests
```

## Optional Configuration

Create a `harper.config.toml` file to customize behavior:

```bash
/project:config-create python
```

Example config:

```toml
[standards.python]
enabled = true
package_manager = "uv"
test_framework = "pytest"

[workflow]
approach = "tdd"
auto_test = true

[quality]
min_test_coverage = 80
```

**When to use config:**

- Setting team-wide standards
- Customizing test coverage requirements
- Specifying language-specific tools
- Defining quality thresholds

**When NOT needed:**

- Quick projects or experiments
- Default settings work fine
- Just trying out the framework

## Generated Files

Harper Prompts creates these files in your project:

- `spec.md` - Comprehensive specification document
- `plan.md` - Implementation prompts (regular approach)
- `ttd-plan.md` - TDD implementation prompts
- `todo.md` - Progress tracking checklist
- `harper.config.toml` - Optional configuration

## Best Practices

### 1. Start Small

Begin with `/project:spec` to thoroughly understand requirements.

### 2. Validate Early

Use `/project:validate` before running plans.

### 3. Review Often

Run `/review:code` after each major step.

### 4. Security First

Include `/review:security` before deployment.

### 5. Track Progress

Update `todo.md` as you complete tasks.

### 6. Small Steps

Follow the incremental approach - don't skip steps.

## Language Support Matrix

| Language | Package Manager | Test Framework | Linter | Formatter |
|----------|----------------|----------------|---------|-----------|
| Python | uv | pytest | ruff, mypy | black |
| JavaScript | npm/yarn/pnpm | jest/vitest | eslint | prettier |
| TypeScript | npm/yarn/pnpm | jest/vitest | eslint | prettier |
| Go | go modules | testing | golangci-lint | gofmt |
| Rust | cargo | built-in | clippy | rustfmt |
| Java | maven/gradle | JUnit | checkstyle | google-java-format |

## Benefits

✅ **Structured Approach** - Clear guidance from idea to implementation
✅ **Multi-Language** - Support for major programming languages
✅ **Quality Assurance** - Built-in validation and security scanning
✅ **Small Steps** - Manageable, testable incremental progress
✅ **AI-Optimized** - Works effectively with code generation tools
✅ **Flexible** - TDD or regular development approaches
✅ **Optional Config** - Works great out of the box, customize when needed

## Examples

### Building a REST API (Python)

```bash
/project:spec REST API for a bookstore with inventory management
/project:spec-create
/project:setup-lang python
/project:plan --ttd
/project:execute ttd-plan.md
/review:security
```

### Building a CLI Tool (Go)

```bash
/project:spec CLI tool for managing Docker containers
/project:spec-create
/project:setup-lang go
/project:plan
/project:execute plan.md
/review:code
```

### Building a Web App (TypeScript)

```bash
/project:spec React dashboard for analytics
/project:spec-create
/project:setup-lang typescript
/project:config-create typescript
/project:plan --ttd
/project:execute ttd-plan.md
```

## Troubleshooting

### Commands not working?

```bash
# Check extension is installed
ls ~/.qwen/extensions/harper-commands/

# Validate your project setup
/project:validate
```

### Missing files?

```bash
# See what files are expected
/project:validate
```

### Want to customize behavior?

```bash
# Create config file
/project:config-create --minimal
```

## Inspiration

This project is directly inspired by ["My LLM codegen workflow atm"](https://harper.blog/2025/02/16/my-llm-codegen-workflow-atm/) which outlines an effective approach to using AI for software development.

## License

MIT License - Open source and free to use.

## Changelog

### v1.1.0 (2025-11-01)

- ✨ Added complete security review command
- ✨ Added project validation command
- ✨ Added error handling audit and implementation
- ✨ Added optional configuration system
- ✨ Added multi-language support (Python, JS/TS, Go, Rust, Java)
- 📝 Simplified setup - config is now optional
- 🔧 Improved documentation

### v1.0.0

- 🎉 Initial release with core commands
- 📋 Project planning workflow
- 🔍 Basic review commands
- ✅ TDD support
