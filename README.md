# Public Prompt License (PPL)

**Status:** Draft 0.1 (Request for Comment)

> **Read the announcement:** [Shipping PPL: A License for the Age of Promptware](https://ship.fail/blog/2025/12/13/shipping-public-prompt-license-ppl/)

The Public Prompt License (PPL) is a family of open-source licenses designed specifically for the "AI-Native" era, where the core logic of an application lives in natural language prompts rather than compiled code.

## The Problem: "English is the new Source Code"

Traditional open-source licenses (MIT, Apache, GPL) were written for software: compiled binaries, source code files, and linked libraries. They do not cleanly map to AI Agents, where the "source code" is a set of system prompts, persona definitions, and few-shot examples.

*   **MIT/Apache** work for text, but don't address the specific needs of "Agent Services" (running an agent as an API).
*   **AGPL** triggers on "remote interaction," but its definition of "Source Code" is ambiguous when applied to LLM weights vs. prompts vs. Python wrappers.
*   **SSPL** extends copyleft to the entire "Service Stack" (OS, backups, hardware drivers). PPL-S takes a narrower approach to align with OSI standards, limiting the scope strictly to the agent's cognitive logic.

## The Solution: PPL

PPL defines a new concept: **"Prompt Source"**.
It separates the *cognitive logic* (the prompts) from the *infrastructure* (the inference engine).

### The Three Variants

| License | Analog | Best For | Key Feature |
| :--- | :--- | :--- | :--- |
| **PPL-M** | MIT | Maximal Adoption | "Do whatever you want, just keep the license file." |
| **PPL-A** | Apache 2.0 | Corporate Use | Explicit patent grant + clear attribution notices. |
| **PPL-S** | AGPL v3 | Agent Services | **Reciprocity:** If you run the agent as a service, you must share the prompts. |

## Definitions

All PPL licenses rely on a shared set of definitions found in [DEFINITIONS.md](DEFINITIONS.md).
This ensures that "Prompt Source" is consistently defined as the *narrative and cognitive core* of the agent, explicitly excluding the underlying inference engine (vLLM, Ollama, etc.).

## How to Apply

### 1. Choose your variant
*   Use **PPL-M** if you want your prompts to be used everywhere, even in closed-source products.
*   Use **PPL-A** if you want patent protection and structured attribution.
*   Use **PPL-S** if you believe in "Prompt Copyleft": if someone profits from running your agent as a service, they should contribute their improvements back to the community.

### 2. Add the License File
Copy the text of your chosen license from the `LICENSES/` directory to a file named `LICENSE` in your repository.

### 3. Add the Header
Add a header to your main prompt files (e.g., `system.md`, `agent.yaml`):

```text
Copyright (c) [Year] [Your Name]
Licensed under the Public Prompt License - [Variant] (PPL-[Variant])
See LICENSE for details.
```

## Roadmap to OSI

This project is structured to prepare for future submission to the Open Source Initiative (OSI).
*   **Phase 1 (Now):** Draft 0.1 release and community feedback.
*   **Phase 2:** Adoption by pilot projects (e.g., Promptware OS).
*   **Phase 3:** Legal review and refinement.
*   **Phase 4:** Formal OSI submission.

## Authors

*   **Felix** - *AI Co-founder (Founder of [Ship.Fail](https://ship.fail))*
*   **[Huan Li](https://github.com/huan)** - *Human Co-founder & Architect*

## Contributing

We welcome feedback from developers, lawyers, and AI researchers. Please open an issue to discuss definitions, scope, or wording.
