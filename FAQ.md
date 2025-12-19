# Frequently Asked Questions (FAQ)

## General

### Q: Why do we need a license for prompts? Can't I just use MIT?
**A:** **Yes!** PPL-M v0.2 *is* the MIT license, just with a clause that explicitly includes Prompts. Standard MIT was written for "Software", and it's ambiguous if it covers prompts. PPL removes that ambiguity.

### Q: Is PPL OSI-Approved?
**A:** Not yet. PPL is currently a **Draft (v0.2)**. Since PPL v0.2 is just a wrapper around OSI-approved licenses (MIT, Apache, AGPL), we believe it is fully compliant with the Open Source Definition (OSD).

## Scope & Definitions

### Q: Does PPL-S require me to open-source my backend code (Python/Go/Rust)?
**A:** **Yes, for your application code.** PPL v0.2 explicitly includes "Source Code" (TypeScript, Python, etc.) in its scope.
*   **Included:** Your agent's "glue code", tool implementations, and business logic.
*   **Excluded:** The "Underlying Software" infrastructure (vLLM, Ollama, OS, Drivers) is still explicitly excluded. You don't need to open-source the platform, just your agent.
*   *Exception:* If your Python code contains "hardcoded prompts" that are essential to the agent's persona, those specific strings are considered Prompt Source.

### Q: What about my API keys and secrets?
**A:** **Never share secrets.** The definition of Prompt Source excludes "User Session Data" and implies that configuration secrets (like `OPENAI_API_KEY`) should be redacted or separated from the logic. You should share the *structure* of your agent, not your credentials.

### Q: Does PPL cover the LLM weights (e.g., Llama-3, GPT-4)?
**A:** **No.** PPL covers the *prompts* you write to steer the model. The model weights themselves are governed by their own license (e.g., Llama Community License). PPL is for the "Software 2.0" code you write on top of the foundation model.

## Usage

### Q: Can I use PPL-M prompts in a closed-source commercial product?
**A:** **Yes.** Just like the MIT license, PPL-M allows you to use the prompts in proprietary software, provided you keep the copyright notice and license file in your distribution (or credits).

### Q: If I fine-tune a model on PPL-S prompts, is the fine-tuned model covered?
**A:** This is a complex area. PPL-S applies to the "Prompt Source". If you "compile" that source into a fine-tuned model (a "Compiled Form"), PPL-S requires that if you serve that model, you must make the original Prompt Source available. It does *not* necessarily force the model weights to be open, but it forces the *training data/prompts* derived from the PPL-S source to be open.

### Q: How do I attribute a PPL-licensed agent in my UI?
**A:** A simple link in your "About" page or footer is sufficient.
> "This agent uses prompts from [Project Name], licensed under PPL-S."
