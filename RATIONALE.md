# Rationale for the Public Prompt License (PPL)

## 1. The "Gap" in Existing Open Source Licenses

The Open Source Initiative (OSI) asks new license submitters to demonstrate a clear "gap" that existing approved licenses do not fill. The Public Prompt License (PPL) addresses a fundamental shift in software architecture: **The rise of Natural Language as Source Code.**

### 1.1 The Definition Problem
Traditional licenses (MIT, Apache 2.0, GPL v3) rely on the definition of "Source Code" as *"the preferred form of the work for making modifications to it."*
While this definition is technically broad, in practice, it has 40 years of case law and community understanding tied to **programming languages** (C, Python, Java).

In an AI Agent, the "logic" is often defined entirely in English (System Prompts, Few-Shot Examples).
*   **Ambiguity:** If I release an agent under AGPL v3, and you access it over a network, must I provide the *Python wrapper* (which is trivial) or the *System Prompt* (which contains the real value)?
*   **The PPL Solution:** PPL v0.2 solves this by **incorporating the standard license by reference** and adding a **Scope Extension**. It explicitly defines **"Prompt Source"** (see `DEFINITIONS.md`) and states that for the purposes of the license, "Source Code" includes "Prompt Source".

### 1.2 The "Service" Gap (AGPL vs. PPL-S)
The GNU Affero GPL (AGPL) was designed to close the "ASP Loophole" (Application Service Provider). It requires source disclosure when users interact with the software over a network.

*   **The Problem:** AGPL's scope is often interpreted as "the program." In an AI context, "the program" might be interpreted as the inference engine (e.g., vLLM) or the application wrapper. It is unclear if the *prompts* themselves are considered part of the "program" or merely "data" fed into it.
*   **The PPL-S Solution:** PPL-S explicitly targets the **"Agent Service"**. It mandates that if you expose the *behavior* defined by the prompts to a user, you must share those *prompts*. It clarifies that the "interaction" is with the *cognitive agent*, not just the HTTP server.

### 1.3 The "Stack" Scope (SSPL vs. PPL-S)
The Server Side Public License (SSPL) attempted to address the cloud era but was rejected by OSI because it claimed rights over the entire "Service Stack" (OS, backups, hardware drivers).

*   **The Context:** SSPL requires the release of the entire service stack. While this ensures full reproducibility, it has faced challenges with OSI approval regarding the "Fields of Endeavor" criterion.
*   **The PPL-S Solution:** PPL-S includes a specific **Scope Limitation** (Infrastructure Exclusion). It explicitly *excludes* the underlying infrastructure (OS, Inference Engine, Hardware Drivers) from the disclosure requirement. It focuses strictly on the **Prompt Source**—the creative work of the author—and not the commodity infrastructure it runs on.

## 2. Comparison with Existing Licenses

| Feature | MIT / Apache | AGPL v3 | SSPL | PPL-S |
| :--- | :--- | :--- | :--- | :--- |
| **Primary Target** | Software Code | Networked Software | Cloud Services | **AI Agents / Prompts** |
| **"Source" Def.** | Implicit (Code) | Implicit (Code) | Implicit (Code) | **Explicit (Prompts)** |
| **Network Trigger** | No | Yes | Yes | **Yes** |
| **Scope** | Work itself | Program + Libraries | Entire Service Stack | **Prompt Source Only** |
| **OSI Status** | Approved | Approved | Rejected | **Draft (Targeting Approval)** |

## 3. Why a New Family?

We chose to create a *family* of licenses (M, A, S) rather than a single license because the AI ecosystem mirrors the software ecosystem:

1.  **PPL-M (MIT-analog):** Needed for "building block" prompts (e.g., standard tool definitions) that should be usable anywhere without friction.
2.  **PPL-A (Apache-analog):** Needed for corporate collaboration where patent grants (for prompting techniques) and clear attribution are required.
3.  **PPL-S (AGPL-analog):** Needed for "Agent Services" to ensure that the *knowledge* embedded in prompts remains a commons, preventing a future where all high-level AI behavior is locked behind black-box APIs.

## 4. Conclusion

PPL does not seek to rewrite copyright law. It seeks to **map** the proven principles of Open Source (Freedom 0-3) onto the new reality of AI Agents. By defining "Prompt Source" and scoping the reciprocal obligations correctly, PPL fills the gap between "Code" and "Cognition."
