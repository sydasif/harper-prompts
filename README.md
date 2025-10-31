# Harper Prompts

Harper Prompts is an AI-assisted development framework inspired by the LLM codegen workflow described in [this blog post](https://harper.blog/2025/02/16/my-llm-codegen-workflow-atm/). It provides a structured approach to software project planning, specification development, and implementation through a series of interactive commands.

## Overview

The Harper Prompts framework follows a systematic approach to software development using AI assistance:

1. **Idea Refinement** - Iterative questioning to develop thorough specifications
2. **Planning** - Detailed, step-by-step blueprint generation
3. **Issue Handling** - GitHub issue management and workflow
4. **Code Review** - Quality and security review processes
5. **Implementation** - Test-driven or regular development prompts
6. **Tracking** - Comprehensive to-do lists for project management

## Core Philosophy

This framework is built on the principles outlined in the blog post about LLM-assisted development:

- **Iterative Specification Development**: Through conversational refinement of ideas
- **Small, Incremental Steps**: Breaking projects into manageable, testable chunks
- **Comprehensive Documentation**: Maintaining clear specs, prompts, and tracking
- **AI-Assisted Implementation**: Using code generation tools effectively

## Command Categories

### Planning Commands

#### `/plan:ask-me`

Interactive iterative questioning to develop detailed specifications. Asks one question at a time to build a comprehensive spec for your idea.

```bash
/plan:ask-me mobile app that tracks personal reading habits
```

#### `/plan:compile`

Compiles brainstorming findings into a comprehensive, developer-ready specification including requirements, architecture, data handling, error handling, and testing plans.

#### `/plan:prompt`

Generates step-by-step implementation prompts for code generation LLMs. Can be used with `--ttd` for Test-Driven Development or `--gh` for GitHub Issues approach.

```bash
/plan:prompt
/plan:prompt --ttd
/plan:prompt --gh
```

#### `/plan:todo`

Creates thorough `todo.md` checklist files for project tracking.

#### `/plan:run`

Executes prompts from a generated prompt file in an automated sequence with optional automated testing.

### Issue Handling Commands

#### `/issues:handle`

Handles a GitHub issue with a detailed plan, implementation, and PR workflow.

```bash
/issues:handle 123
```

#### `/issues:work-prompt-plan`

Works on issues from the prompt plan following a structured workflow.

```bash
/issues:work-prompt-plan
```

#### `/issues:work-todo`

Works on issues from the todo list following a structured workflow.

```bash
/issues:work-todo
```

#### `/issues:create`

Creates GitHub issues for code problems, missing tests, or security concerns.

```bash
/issues:create missing-tests
/issues:create code-issues
```

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

### Development Commands

#### `/dev:dot-file`

Creates a .dot file representing the project based on spec.md and other files.

```bash
/dev:dot-file
```

### Setup Commands

#### `/setup:config`

Provides setup configuration information and workflow details.

```bash
/setup:config
```

## Usage Workflow

The recommended workflow mirrors the approach described in the blog post:

### 1. Idea Honing

Use `/plan:ask-me` to iteratively refine your idea into a detailed specification.

### 2. Planning

Take the specification and use `/plan:prompt` to generate implementation prompts, then `/plan:todo` to create a tracking checklist.

### 3. Execution

Use the generated prompts with your preferred code generation tool (Aider, Cursor, Claude, etc.) to implement the project incrementally.

### 4. Issue Management

Use the issue handling commands to manage GitHub workflows.

### 5. Quality Assurance

Use the review commands to ensure code quality and security.

## Benefits

- **Structured Approach**: Provides clear guidance for planning and implementing projects
- **Small Steps**: Breaks complex projects into manageable chunks
- **Documentation**: Maintains comprehensive specifications and tracking
- **AI Integration**: Designed to work effectively with modern code generation tools
- **Flexible**: Supports both TDD and regular development approaches
- **Issue Management**: Built-in workflows for GitHub issue handling

## Inspiration

This project is directly inspired by the blog post ["My LLM codegen workflow atm"](https://harper.blog/2025/02/16/my-llm-codegen-workflow-atm/) which outlines an effective approach to using AI for software development. The framework translates these concepts into actionable commands and tools.

## License

This project is open source and available under the MIT License.
