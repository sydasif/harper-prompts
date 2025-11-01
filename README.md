# Harper Prompts

Harper Prompts is an AI-assisted development framework inspired by the LLM codegen workflow described in [this blog post](https://harper.blog/2025/02/16/my-llm-codegen-workflow-atm/). It provides a structured approach to software project planning, specification development, and implementation through a series of interactive commands.

## Overview

The Harper Prompts framework follows a systematic approach to software development using AI assistance:

1. **Idea Refinement** - Iterative questioning to develop thorough specifications
2. **Planning** - Detailed, step-by-step blueprint generation
3. **Code Review** - Quality and security review processes
4. **Implementation** - Test-driven or regular development prompts
5. **Tracking** - Comprehensive to-do lists for project management

## Core Philosophy

This framework is built on the principles outlined in the blog post about LLM-assisted development:

- **Iterative Specification Development**: Through conversational refinement of ideas
- **Small, Incremental Steps**: Breaking projects into manageable, testable chunks
- **Comprehensive Documentation**: Maintaining clear specs, prompts, and tracking
- **AI-Assisted Implementation**: Using code generation tools effectively

## Command Categories

### Planning Commands

#### `/project:compile`

Compiles brainstorming findings into a comprehensive, developer-ready specification including requirements, architecture, data handling, error handling, and testing plans.

#### `/project:init`

Interactive iterative questioning to develop detailed specifications. Asks one question at a time to build a comprehensive spec for your idea.

```bash
/project:init mobile app that tracks personal reading habits
```

#### `/project:plan`

Generates step-by-step implementation prompts for code generation LLMs. Can be used with `--ttd` for Test-Driven Development or `--gh` for GitHub Issues approach.

```bash
/project:plan
/project:plan --ttd
/project:plan --gh
```

#### `/project:todo`

Creates thorough `todo.md` checklist files for project tracking.

#### `/project:run`

Executes prompts from a generated prompt file in an automated sequence with optional automated testing.

### Code Review Commands

#### `/review:careful`

Performs a careful review of new code with fresh eyes to find bugs and issues.

```bash
/review:careful
```

#### `/review:missing-tests`

Reviews code to identify missing test cases and creates GitHub issues for them.

```bash
/review:missing-tests
```

#### `/review:security`

Performs a security review of code to identify vulnerabilities.

```bash
/review:security
```

### Setup Commands

#### `/project:setup`

Provides setup configuration information and workflow details.

```bash
/project:setup
```

## Usage Workflow

The recommended workflow mirrors the approach described in the blog post:

### 1. Idea Honing

Use `/project:init` to iteratively refine your idea into a detailed specification.

### 2. Planning

Take the specification and use `/project:plan` to generate implementation prompts, then `/project:todo` to create a tracking checklist.

### 3. Execution

Use the generated prompts with your preferred code generation tool (Aider, Cursor, Claude, etc.) to implement the project incrementally.

### 4. Quality Assurance

Use the review commands to ensure code quality and security.

## Benefits

- **Structured Approach**: Provides clear guidance for planning and implementing projects
- **Small Steps**: Breaks complex projects into manageable chunks
- **Documentation**: Maintains comprehensive specifications and tracking
- **AI Integration**: Designed to work effectively with modern code generation tools
- **Flexible**: Supports both TDD and regular development approaches

## Inspiration

This project is directly inspired by the blog post ["My LLM codegen workflow atm"](https://harper.blog/2025/02/16/my-llm-codegen-workflow-atm/) which outlines an effective approach to using AI for software development. The framework translates these concepts into actionable commands and tools.

## License

This project is open source and available under the MIT License.
