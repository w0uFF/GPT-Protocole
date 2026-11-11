# ChatGPT General Protocol — v1.0.0

**Languages: [Français](README.fr.md) | English (here) | [Home](../README.md)**

🌐 **English version.** The French edition is available as a separate download in GitHub Releases.

A **free, general-purpose workflow protocol for ChatGPT**: practical phases, explicit progress tracking, human verification, and a continuation interface where you can add notes, preview the next prompt, and either send or copy it.

> **Tested with ChatGPT Plus.** Independent, unofficial project; not developed or endorsed by OpenAI. No browser extension or application installation is needed. These are instruction files that you provide to ChatGPT. Features vary by model, account, and interface.

## Download the English edition

**[Download GPT-Protocol-EN.zip](https://github.com/w0uFF/GPT-Protocole/releases/download/ENv1.0.0/GPT-Protocol-EN.zip)**

## Download — GitHub Releases

1. Open **Releases** on the GitHub repository page.
2. Select the English release `ENv1.0.0`.
3. Under **Assets**, download **[`GPT-Protocol-EN.zip`](https://github.com/w0uFF/GPT-Protocole/releases/download/ENv1.0.0/GPT-Protocol-EN.zip)**.
4. Extract the archive: it contains the English-language protocol only.

> **Important:** avoid **Code → Download ZIP** if you only want to install the protocol. That option downloads the entire repository, which may include both languages.

The new video tutorial will be linked from the [repository home page](../README.md). The written instructions below are sufficient to get started.

---

## What does this protocol do?

Without a defined workflow, you may need to restate decisions and write every follow-up prompt yourself. This protocol asks ChatGPT to:

- **Do the available work immediately**, rather than generate unnecessary plans.
- **Divide longer tasks into useful phases**, with concrete outputs, decisions, and completion criteria.
- **Carry forward an explicit project state**: goals, constraints, decisions, completed results, and outstanding work.
- Show **`HUMAN VERIFICATION: REQUIRED` or `HUMAN VERIFICATION: NOT REQUIRED` at the end of every phase**, with a practical test guide when required.
- Keep **verification** separate from **permission to perform an action**. Clicking Continue never counts as a passed check or authorization.
- When another step makes sense and the interface supports it, offer **an optional notes field**, a **live preview**, and real **Continue — next step** / **Copy next prompt** actions. Both actions share exactly the same prompt.
- Suggest an **MVC-inspired modular organization** for complex projects when useful, without imposing programming concepts on simple requests.
- **Stop when the requested task is actually complete**.

No programming knowledge is necessary. Use it for writing, research, learning, personal planning, content creation, or technical projects.

---

## Recommended installation — ChatGPT Project

A **ChatGPT Project** is the most practical way to use the same protocol in **multiple conversations inside one workspace**, without reattaching the files each time.

### Step 1 — Download the protocol

1. Open the GitHub repository’s **Releases** section.
2. Under the English release `ENv1.0.0`’s **Assets**, download **[`GPT-Protocol-EN.zip`](https://github.com/w0uFF/GPT-Protocole/releases/download/ENv1.0.0/GPT-Protocol-EN.zip)**.
3. Extract the archive. The English-language files are directly inside it.

You only need these English files when setting up an English-language Project. There is no need to upload both language sets.

### Step 2 — Create a ChatGPT Project

1. Open [ChatGPT](https://chatgpt.com/).
2. In the sidebar, select **New project** (the exact label may vary).
3. Name it, for example, **ChatGPT — General Protocol**.
4. Optionally choose a color or icon.

> A ChatGPT **Project** groups conversations, reference files, and project instructions. It is **not** the same as creating a custom GPT in the GPT builder.

### Step 3 — Add the English protocol files as Project sources

1. Open your new Project.
2. Find **Project sources**, **Add files**, or the equivalent option in your interface.
3. Upload the extracted Markdown files from `GPT-Protocol-EN.zip`. Include the two files in `en/Templates/` if you plan to work on longer projects.

**Essential files:**

| File | Purpose |
|---|---|
| [`RULES.md`](../en/RULES.md) | Standing behavioral rules |
| [`WORKFLOW.md`](../en/WORKFLOW.md) | Phases, handoff, completion |
| [`CONTINUATION_UI.md`](../en/CONTINUATION_UI.md) | Notes, preview, Continue, Copy, fallback |
| [`QUALITY_AND_VERIFICATION.md`](../en/QUALITY_AND_VERIFICATION.md) | Human checks, approval, errors |
| [`MODULAR_ARCHITECTURE.md`](../en/MODULAR_ARCHITECTURE.md) | Optional modular approach for complex projects |

Also recommended: [`START_HERE.md`](../en/START_HERE.md), [`START_PROMPT.md`](../en/START_PROMPT.md), [`EXAMPLES.md`](../en/EXAMPLES.md), and the [`Templates/`](../en/Templates/) documents. Uploading individual `.md` files is more reliable than assuming every ChatGPT environment can inspect ZIP files. File limits depend on the user's plan and product features.

### Step 4 — Set Project instructions (important)

1. Open the Project's **•••** menu.
2. Select **Project settings** and locate **Project instructions**.
3. Paste the following text:

```text
In every conversation in THIS Project, follow the ChatGPT General Protocol v1.0.0 contained in this Project's source files.

At the start of a task, consult the relevant files, prioritizing RULES.md, WORKFLOW.md, CONTINUATION_UI.md, and QUALITY_AND_VERIFICATION.md. Consult MODULAR_ARCHITECTURE.md for complex projects and the templates when useful. If a file is missing or inaccessible, say so instead of inventing its content.

Execute simple requests immediately. For longer tasks, work in useful phases while tracking goals, constraints, decisions, results, and handoff state.

At the end of EVERY phase, including the last, write exactly one status: HUMAN VERIFICATION: REQUIRED or HUMAN VERIFICATION: NOT REQUIRED. If REQUIRED, explain exactly how to test and report the result. Never treat Continue as proof of a passed test or permission to act.

If meaningful next steps remain and real interactive controls are supported, display an optional notes field, a dynamic complete-prompt preview, and two functional actions: "Continue — next step" and "Copy next prompt". Both must send or copy the exact same text, including original notes to be faithfully reformulated in the next turn. Otherwise provide a complete ready-to-copy prompt.

Do not invent extra phases. Finish normally when the work is complete.
```

**Why both source files and Project instructions?** The files hold the full rules; the Project instructions explicitly ask ChatGPT to apply them. Adding files alone does not guarantee every rule will be followed. Project instructions apply **inside that Project**, not across your entire account.

### Step 5 — Start working

Create a **new conversation within the Project**. You can simply say:

> Help me organize a move, with a budget, timeline, and priorities. Break it into steps only where useful.

You generally do not need to reattach the protocol for each conversation in the same Project. Create another chat in that Project whenever you have a separate task.

### Step 6 — Understand Project memory and context

Projects may use their files and conversations as context, depending on your settings and plan. **Project-only memory** (where offered) limits the context to the Project; **default memory** works according to applicable account and memory settings.

This does **not** mean every line of every file or conversation will be preserved word for word forever. Keep the instruction documents in Project sources. For longer work, use [`Templates/STATE_AND_HANDOFF.md`](../en/Templates/STATE_AND_HANDOFF.md) and [`Templates/DECISION_LOG.md`](../en/Templates/DECISION_LOG.md) to make the state explicit.

If your UI offers **Move to project** for an existing conversation, it may inherit the Project's instructions and sources. Some chats cannot be moved.

---

## Alternative — one ordinary conversation

You do not need a Project to try the protocol:

1. Open an ordinary ChatGPT conversation.
2. Attach the files from `en/` (or a ZIP if the interface can actually read it).
3. Open [`START_PROMPT.md`](../en/START_PROMPT.md) and replace `[MY REQUEST]` with your task.
4. Send the prompt. For a separate new conversation, provide the required protocol files again.

**Sending "remember this protocol for every future conversation" in one chat does not reliably install it everywhere.** Memory is not a guaranteed full-text instruction-file storage mechanism.

### Can I enable it for every normal ChatGPT conversation?

You can put a **shortened version** of the behavior in **Settings → Personalization → Custom instructions** (labels may vary):

```text
By default, work in a structured but efficient way: finish simple requests directly; split complex tasks into useful phases, track important decisions and constraints, and identify the next action. At the end of each phase, explicitly show HUMAN VERIFICATION: REQUIRED or NOT REQUIRED. If REQUIRED, give a precise test guide and do not claim a passed check without the user's result. When useful and supported, offer optional notes, a dynamic preview, and synchronized Continue — next step / Copy next prompt actions; otherwise provide a copyable prompt. Never invent tests, authorization, or unnecessary phases. Use modular organization for complex projects when it helps.
```

These global custom instructions **summarize** the protocol. They do not automatically attach all the Markdown files to every chat. For the complete protocol, a ChatGPT Project is recommended. Project instructions take precedence over global custom instructions within that Project.

### What about a custom GPT?

A **custom GPT** is another option. Where supported, put the behavior in the GPT's instructions and upload protocol documents as knowledge. The protocol applies when people chat **with that custom GPT**; it does not silently modify their normal ChatGPT conversations.

---

## How the Continue / Copy interface should work

If meaningful work remains, the ideal experience is:

1. **Optional notes** — e.g., "use a smaller budget" or "add examples".
2. **Dynamic preview** — shows the complete next prompt with your notes.
3. **Continue — next step** — sends that prompt as a new message.
4. **Copy next prompt** — copies the exact same prompt for reuse elsewhere.

Notes are preserved verbatim and then faithfully rewritten into actionable instructions **in the following assistant turn**. Clicking Continue never confirms a human check.

**Interactive controls cannot be guaranteed**: availability depends on the ChatGPT interface and account capabilities. When unavailable, the protocol requires a ready-to-copy text prompt, **not fake buttons**. See [`CONTINUATION_UI.md`](../en/CONTINUATION_UI.md).

## Human verification — mandatory at every phase

- **`HUMAN VERIFICATION: REQUIRED`** — an indispensable check must be performed by the user. ChatGPT explains the exact procedure, expected outcome, and how to report success or failure. It cannot mark a blocked phase as verified without the result.
- **`HUMAN VERIFICATION: NOT REQUIRED`** — no indispensable manual check is needed to finish or proceed with that phase.

Approval to send, publish, purchase, or delete something is **separate from verification**. See [`QUALITY_AND_VERIFICATION.md`](../en/QUALITY_AND_VERIFICATION.md).

## English protocol files

| File | Description |
|---|---|
| [`START_HERE.md`](../en/START_HERE.md) | Quick start |
| [`START_PROMPT.md`](../en/START_PROMPT.md) | Universal starter prompt |
| [`RULES.md`](../en/RULES.md) | Core behavior |
| [`WORKFLOW.md`](../en/WORKFLOW.md) | Phases and handoff |
| [`CONTINUATION_UI.md`](../en/CONTINUATION_UI.md) | Interactive continuation and fallback |
| [`QUALITY_AND_VERIFICATION.md`](../en/QUALITY_AND_VERIFICATION.md) | Quality, permission, human checks |
| [`MODULAR_ARCHITECTURE.md`](../en/MODULAR_ARCHITECTURE.md) | Optional MVC-inspired organization |
| [`EXAMPLES.md`](../en/EXAMPLES.md) | Usage examples |
| [`Templates/STATE_AND_HANDOFF.md`](../en/Templates/STATE_AND_HANDOFF.md) | Handoff template |
| [`Templates/DECISION_LOG.md`](../en/Templates/DECISION_LOG.md) | Decision log |
| [`CHANGELOG.md`](../en/CHANGELOG.md) | Version history |
| [`CONTRIBUTING.md`](../en/CONTRIBUTING.md) | Contribution guidelines |

## Limitations

- The protocol cannot unlock tools, permissions, external access, or background execution.
- Results depend on the model, available context, interface, and higher-priority ChatGPT rules.
- Project source files are not the same as conversational memory.
- Global custom instructions do not guarantee access to files uploaded in other conversations.
- This is an independent project, **not an official OpenAI product**.

## Official documentation

- [Projects in ChatGPT — OpenAI Help Center](https://help.openai.com/en/articles/10169521-projects-in-chatgpt)
- [Custom instructions for ChatGPT — OpenAI Help Center](https://help.openai.com/en/articles/8096356-custom-instructions-for-chatgpt)
- [Creating and editing a custom GPT — OpenAI Help Center](https://help.openai.com/en/articles/8770868-creating-a-gpt)

## Version

Protocol version: **v1.0.0**. See [`CHANGELOG.md`](../en/CHANGELOG.md).

---

*Independent, unofficial project; not affiliated with OpenAI.*
