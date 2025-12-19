# Compatibility Guide

This document outlines how the Public Prompt License (PPL) family interacts with other common open source licenses.

## Summary Table

| License | Compatible with PPL-M? | Compatible with PPL-A? | Compatible with PPL-S? |
| :--- | :--- | :--- | :--- |
| **MIT** | ✅ Yes | ✅ Yes | ✅ Yes (One-way) |
| **Apache 2.0** | ✅ Yes | ✅ Yes | ✅ Yes (One-way) |
| **GPL v3** | ✅ Yes | ✅ Yes | ⚠️ Complex |
| **AGPL v3** | ✅ Yes | ✅ Yes | ⚠️ Complex |
| **Proprietary** | ✅ Yes | ❌ No (Attribution req) | ❌ No |

## Detailed Analysis

### PPL-M (MIT-style)
*   **Inbound:** You can include MIT, Apache, or BSD licensed text into a PPL-M project.
*   **Outbound:** You can include PPL-M prompts into *any* project (GPL, Proprietary, etc.), provided you retain the license file.

### PPL-A (Apache-style)
*   **Inbound:** You can include MIT or Apache licensed text.
*   **Outbound:** You can include PPL-A prompts into GPL v3 projects (Apache 2.0 is compatible with GPL v3). You cannot include them in GPL v2 projects.
*   **Patent Note:** The patent grant in PPL-A is identical to Apache 2.0. This provides strong protection for downstream users.

### PPL-S (Service-style)
*   **The "Viral" Effect:** PPL-S is a "strong copyleft" license for prompts.
*   **Combining with Code:**
    *   If you have a project with **AGPL Code** + **PPL-S Prompts**, the result is effectively a "Double AGPL" system. You must share the code (under AGPL) and the prompts (under PPL-S). This is a highly compatible and robust combination for open-source AI services.
    *   If you have **Proprietary Code** + **PPL-S Prompts**, you must be careful. You can keep your code closed, but you *must* share the prompts if you run the service. The PPL-S "Scope Limitation" protects your code from being infected, but you must strictly separate the two.

## License Headers & SPDX

We are in the process of submitting PPL to the SPDX registry. Until then, use the following identifiers in your `LICENSE` headers:

*   `License-Ref-PPL-M-0.2`
*   `License-Ref-PPL-A-0.2`
*   `License-Ref-PPL-S-0.2`
