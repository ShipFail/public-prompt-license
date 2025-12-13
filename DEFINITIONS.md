# Public Prompt License (PPL) Definitions

**Version:** 0.1
**Date:** 2025-12-13

These definitions are incorporated by reference into the Public Prompt License family (PPL-M, PPL-A, PPL-S). They are designed to provide clarity on what constitutes the "source code" of an AI agent, distinct from the underlying software infrastructure.

## 1. Prompt Source

**"Prompt Source"** means the human-readable natural language instructions, structured data, and configuration files that define the behavior, persona, logic, and capabilities of an AI agent.

**"Prompt Source" includes, but is not limited to:**
*   **System Prompts:** The core instructions that define the agent's role, constraints, and personality (e.g., "You are a helpful assistant...").
*   **Tool & Interface Descriptions:** The textual descriptions, schemas, and "help" text provided to the model to explain how to use external tools or APIs (e.g., JSON schemas for function calling, API documentation injected into context).
*   **Routing & Orchestration Logic:** Natural language instructions or structured decision trees used to determine control flow, sub-agent selection, or tool invocation.
*   **Contextual Examples:** Few-shot examples, dialogue templates, and demonstration pairs used to guide the model's output style or reasoning process.
*   **Knowledge Structure:** Index files, "bootloader" configurations, or file system maps that direct the agent to specific knowledge bases or skill libraries (e.g., the `init` or `kernel` configurations in Promptware OS).

**"Prompt Source" explicitly excludes:**
*   **Underlying Software:** The source code of the inference engine (e.g., vLLM, llama.cpp), the host operating system, the network stack, or the container orchestration platform.
*   **Model Weights:** The binary parameters of the foundation model itself.
*   **User Session Data:** Inputs provided by the end-user during a specific interaction session.
*   **Tool Implementation Code:** The underlying executable code (e.g., Python, JavaScript, Rust) that implements the logic of a tool, *unless* that code contains embedded natural language instructions that substantially alter the agent's persona or reasoning.

## 2. Agent Service

**"Agent Service"** means a service that enables users to interact with an AI agent or system powered by the Prompt Source, typically over a computer network or via an API.

## 3. Corresponding Prompt Source (for PPL-S)

**"Corresponding Prompt Source"** means the Prompt Source used to generate the specific behavior, responses, and capabilities of the Agent Service with which a user is interacting.

For the purpose of the PPL-S (Service) license, the obligation to share Corresponding Prompt Source applies to:
1.  **The Narrative Core:** All system prompts and persona definitions active for that interaction.
2.  **The Cognitive Architecture:** Any logic that directs the agent's reasoning path or tool selection.
3.  **The Interface Definitions:** The full textual descriptions of any tools available to the agent during the interaction.

**Scope Limitation (Infrastructure Exclusion):**
The obligation to provide Corresponding Prompt Source does **not** extend to the underlying software infrastructure, inference engines, hardware drivers, or the implementation code of tools, provided that such software is not required to understand or modify the *cognitive behavior* of the agent defined in the Prompt Source.
