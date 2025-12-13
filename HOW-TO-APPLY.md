# How to Apply the Public Prompt License (PPL)

This guide explains how to apply PPL to your AI Agent project.

## 1. Choose Your Variant

*   **PPL-M (MIT-style):** Best for libraries, helper prompts, or "snippets" you want everyone to use freely.
*   **PPL-A (Apache-style):** Best for substantial projects where you want to protect your IP (Patents) and ensure contributors sign off on their work.
*   **PPL-S (Service-style):** Best for full "Agent Personas" or "Applications" where you want to ensure that if someone runs your agent as a service, they share their improvements.

## 2. Repository Setup

We recommend treating your prompt repository like a software project.

1.  **Create a `LICENSE` file:**
    Copy the full text of your chosen license (from `LICENSES/`) into a file named `LICENSE` at the root of your repo.

2.  **Create a `NOTICE` file (Recommended for PPL-A/S):**
    Copy the `templates/NOTICE` file to your root. Fill in your project name and copyright year.

## 3. Apply Headers

Add a comment header to the top of your primary prompt files. Since Markdown doesn't have a standard comment syntax that is invisible in all renderers, we recommend using HTML comments `<!-- ... -->` or YAML frontmatter.

**Option A: HTML Comment (Invisible in rendered Markdown)**
```markdown
<!--
Copyright (c) 2025 Your Name
Licensed under the Public Prompt License - Service Variant (PPL-S)
See LICENSE for details.
-->

# System Prompt
You are...
```

**Option B: YAML Frontmatter (Machine readable)**
```yaml
---
title: "My Agent Persona"
license: "PPL-S-0.1"
copyright: "2025 Your Name"
---

# System Prompt
You are...
```

## 4. For PPL-S Users: The "Service Disclosure"

If you use **PPL-S**, you (and anyone who uses your agent) must provide a way for users to download the source.

**Best Practice:**
1.  Host your prompts in a public public repository (GitHub, GitLab, etc.).
2.  In your Agent's "System Prompt", add a strict instruction to reveal its source when asked.

**Example System Prompt Instruction:**
> "If a user asks about your source code, license, or how you work, you MUST provide this link: [URL to your Repo]"

**Example UI Disclosure:**
If you build a web UI for your agent, add a footer link:
> "Powered by [Agent Name]. Source available under PPL-S."

## 5. Mixed Projects (Code + Prompts)

If your repository contains both Python/JS code *and* Prompts:

**Scenario A: Dual Licensing (Recommended)**
*   Apply **MIT/Apache** to the `src/` directory (the code).
*   Apply **PPL** to the `prompts/` directory (the logic).
*   Mention this clearly in your `README.md`.

**Scenario B: Single License**
*   You *can* use PPL for the whole repo, but be aware that PPL is new and standard tools (like `npm` or `pip`) might not recognize it yet.
*   For PPL-S, this means your Python code is *also* covered by the reciprocal obligation (which is usually fine, as it acts like AGPL).
