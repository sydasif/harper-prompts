# Project Workflow

This document outlines the recommended workflow for using the `/project` commands to manage your software development lifecycle, from initial idea refinement to execution and tracking.

## 1. Idea Honing (`/project:initiate`)

The first step in any project is to clearly define the idea and gather detailed specifications.

- **Command:** `/project:initiate`
- **Purpose:** Initiates an interactive questioning process to develop a thorough, step-by-step specification for your idea. The AI will ask one question at a time, building on previous answers to create a comprehensive spec covering functional and non-functional requirements, architecture, data handling, error handling, and testing plans.
- **Output:** A detailed specification document (e.g., `specification.md`) that serves as the foundation for planning.
- **Usage Example:**

    ```bash
    /project:initiate A mobile app that tracks personal reading habits
    ```

## 2. Planning & Specification Compilation

Once your idea is honed, these commands help you formalize the specification, generate implementation prompts, and create a tracking checklist.

### 2.1. Compile Specification (`/project:create`)

- **Command:** `/project:create`
- **Purpose:** Compiles the findings from the brainstorming session (initiated by `/project:spec`) into a comprehensive, developer-ready specification. This includes all relevant requirements, architecture choices, data handling details, error handling strategies, and a testing plan.
- **Usage Example:**

    ```bash
    /project:create
    ```

### 2.2. Generate Implementation Plan (`/project:plan`)

- **Command:** `/project:plan`
- **Purpose:** Generates a series of prompts for a code-generation LLM to implement the project. It creates a detailed, step-by-step blueprint and breaks it down into small, incremental chunks. It supports different approaches:
  - **Regular Development:** Generates prompts for incremental implementation.
  - **Test-Driven Development (TDD):** Use with `--ttd` flag to prioritize creating tests first for each component/feature.
- **Output:** A plan file (e.g., `planing.md` or `ttd-planing.md`) containing the generated prompts.
- **Usage Examples:**

    ```bash
    /project:plan
    /project:plan --ttd
    ```

### 2.3. Create To-Do List (`/project:todo`)

- **Command:** `/project:todo`
- **Purpose:** Generates a thorough `todo.md` file from your project idea, creating a detailed checklist that can be used to track progress.
- **Output:** A `todo.md` checklist file.
- **Usage Example:**

    ```bash
    /project:todo
    ```

### 3. Setup (`/project:setup`)

This is an optional command...

## 4. Execution (`/project:execute`)

This phase involves executing the generated prompts to implement the project incrementally.

- **Command:** `/project:execute`
- **Purpose:** Executes prompts from a generated prompt file (e.g., `planing.md` or `ttd-planing.md`) in an automated sequence. It follows the implementation approach from the blog post, simulating the execution phase of the workflow.
- **Usage Example:**

    ```bash
    /project:execute ttd-planing.md
    ```
