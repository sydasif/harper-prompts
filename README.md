# Harper Prompts

Harper Prompts is an AI-assisted development framework inspired by the LLM codegen workflow described in [this blog post](https://harper.blog/2025/02/16/my-llm-codegen-workflow-atm/). It provides a structured approach to software project planning, specification development, and implementation through a series of interactive commands.

## Overview

The Harper Prompts framework follows a systematic approach to software development using AI assistance:

1. **Idea Refinement** - Iterative questioning to develop thorough specifications
2. **Planning** - Detailed, step-by-step blueprint generation
3. **Implementation** - Test-driven or regular development prompts
4. **Tracking** - Comprehensive to-do lists for project management

## Core Philosophy

This framework is built on the principles outlined in the blog post about LLM-assisted development:

- **Iterative Specification Development**: Through conversational refinement of ideas
- **Small, Incremental Steps**: Breaking projects into manageable, testable chunks
- **Comprehensive Documentation**: Maintaining clear specs, prompts, and tracking
- **AI-Assisted Implementation**: Using code generation tools effectively

## Commands

### `/plan:ask-me`

Interactive iterative questioning to develop detailed specifications. Asks one question at a time to build a comprehensive spec for your idea.

```bash
/plan:ask-me mobile app that tracks personal reading habits
```

### `/plan:compile`

Compiles brainstorming findings into a comprehensive, developer-ready specification including requirements, architecture, data handling, error handling, and testing plans.

### `/plan:prompt`

Generates step-by-step implementation prompts for code generation LLMs. Can be used with or without the `--ttd` flag for Test-Driven Development approach.

```bash
/plan:prompt
/plan:prompt --ttd
```

### `/plan:todo`

Creates thorough `todo.md` checklist files for project tracking.

### `/plan:project`

Master command that chains all planning commands together for a complete project workflow.

### `/plan:run`

Executes prompts from a generated prompt file in an automated sequence with optional automated testing.

## Usage Workflow

The recommended workflow mirrors the approach described in the blog post:

### 1. Idea Honing

Use `/plan:ask-me` to iteratively refine your idea into a detailed specification.

### 2. Planning

Take the specification and use `/plan:prompt` to generate implementation prompts, then `/plan:todo` to create a tracking checklist.

### 3. Execution

Use the generated prompts with your preferred code generation tool (Aider, Cursor, Claude, etc.) to implement the project incrementally.

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
