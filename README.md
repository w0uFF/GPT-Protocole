<div align="center">

# ChatGPT General Protocol

**A practical workflow for ChatGPT — from everyday requests to long-term projects.**

**v1.0.0 · Free · English / Français · Tested with ChatGPT Plus**

### [Download English](https://github.com/w0uFF/GPT-Protocole/releases/download/ENv1.0.0/GPT-Protocol-EN.zip) · [English Installation Guide](docs/README.en.md)

### [Download French](https://github.com/w0uFF/GPT-Protocole/releases/download/v1.0.0/GPT-Protocol-FR.zip) · [French Installation Guide](docs/README.fr.md)

### [Video Guide & Usage Example](https://www.youtube.com/watch?v=coU8KSVffeQ)

</div>

---

## What is this?

ChatGPT General Protocol is a set of **Markdown instructions**, not a separate app or browser extension. It encourages ChatGPT to complete straightforward requests directly and break down complex work into useful, verifiable phases.

Instead of writing a fresh "continue" prompt after every step, you can use a continuation interface that **incorporates your feedback, previews the next prompt, and lets you either send it or copy it**—when supported by your ChatGPT interface.

### What it adds

| Capability | What it means for you |
|---|---|
| **Continue — Next Step** | Send a contextual follow-up without writing it manually. |
| **Optional feedback** | Add corrections or new requirements before continuing. |
| **Live prompt preview** | Inspect the next prompt as your notes change. |
| **Copy Next Prompt** | Copy precisely the same prompt the Continue action would send. |
| **Human verification** | Every phase explicitly reports `REQUIRED` or `NOT REQUIRED`; required checks come with instructions. |
| **State & handoff** | Keep goals, constraints, decisions, completed work, and the next action organized. |
| **Modular organization** | Use an optional MVC-inspired separation for complex projects, without imposing it on simple tasks. |
| **Meaningful completion** | Stop when the task is done instead of adding artificial phases. |

**Protocol source files:** [English (`en/`)](en/START_HERE.md) · [French (`fr/`)](fr/START_HERE.md)

## Download & install

| English | French |
|:--|:--|
| **[Download GPT-Protocol-EN.zip](https://github.com/w0uFF/GPT-Protocole/releases/download/ENv1.0.0/GPT-Protocol-EN.zip)** | **[Download GPT-Protocol-FR.zip](https://github.com/w0uFF/GPT-Protocole/releases/download/v1.0.0/GPT-Protocol-FR.zip)** |
| [English setup guide](docs/README.en.md) | [French installation guide](docs/README.fr.md) |
| [English Release](https://github.com/w0uFF/GPT-Protocole/releases/tag/ENv1.0.0) | [French Release](https://github.com/w0uFF/GPT-Protocole/releases/tag/v1.0.0) |

**Quick setup:** download and extract your language's ZIP → create a **ChatGPT Project** → upload the Markdown files as Project sources → paste the Project instructions from your language's guide → start a chat **inside that Project**.

**Use the Release ZIP, not `Code → Download ZIP`,** if you just want the protocol in one language. You do not need Git or any development tools.

## See how it works

### Example 1 — Add feedback, preview, continue or copy

A meal-planning request can become a step-by-step workflow. Before moving on, you might add the note:

> Reduce the budget by 20% and include a vegetarian alternative.

The next prompt preview incorporates the note along with the confirmed decisions and current task status. **Continue — Next Step** sends that prompt; **Copy Next Prompt** copies the identical text. On the next turn, ChatGPT must interpret the note faithfully before proceeding.

```text
Feedback (optional)
┌──────────────────────────────────────────────────────────────┐
│ Reduce the budget by 20%; include a vegetarian alternative. │
└──────────────────────────────────────────────────────────────┘

Next prompt preview
Continue planning the meal for 80 guests. Preserve confirmed
constraints and decisions. Include the user's budget reduction
and vegetarian option request. Verify quantities and costs ...

[ Continue — Next Step ]       [ Copy Next Prompt ]
```

*Illustrative example, not a screenshot or a promise of a specific interface.*

### Example 2 — Structured questions when truly needed

If a request requires several independent choices, ChatGPT may offer a concise interactive form (for instance, service style, event date, dietary requirements, and budget). **Forms are optional**; the protocol does not force them for straightforward questions.

### Example 3 — Human verification

At the end of **every phase**, the protocol requires a clear status:

```text
HUMAN VERIFICATION: REQUIRED
Check: Confirm the quantities and dietary restrictions with the organizer.
How: Compare the proposed plan against the guest list and constraints.
Expected result: No missing restrictions or unresolved quantities.
Next: Report your findings before the blocked phase is considered validated.
```

If no human check is needed, the status is `HUMAN VERIFICATION: NOT REQUIRED`. Clicking Continue **never** means a check passed or permission was granted.

<!-- When real user-approved examples are available, place their images in assets/
     and replace these illustrative text examples with linked screenshots. -->

## Video tutorial

Watch the silent step-by-step installation and usage demonstration. It shows how to download the protocol, configure a ChatGPT Project, and use it to organize a move, including the feedback and continuation workflow.

[![Watch the ChatGPT General Protocol installation and usage tutorial](https://img.youtube.com/vi/coU8KSVffeQ/hqdefault.jpg)](https://www.youtube.com/watch?v=coU8KSVffeQ)

**[Watch the full video guide & usage example on YouTube](https://www.youtube.com/watch?v=coU8KSVffeQ)**

## Documentation

- **[English setup guide](docs/README.en.md)** — full instructions, Project setup, and alternatives.
- **[Guide français](docs/README.fr.md)** — installation et utilisation en français.
- **[English protocol source](en/START_HERE.md)** — protocol documents for inspection and contribution.
- **[French protocol source](fr/START_HERE.md)** — documents du protocole en français.
- **[Contributing](fr/CONTRIBUTING.md)** — contribution guidelines.

## Compatibility & limitations

**Tested using ChatGPT Plus.** The protocol is an independent, unofficial project and is not affiliated with OpenAI.

Interactive forms, input fields, and buttons depend on the model, client and available UI features; they cannot be guaranteed by a Markdown instruction alone. If interactive controls are unavailable, the protocol calls for a complete next prompt that you can copy manually. Project files and Project instructions apply to that Project, **not automatically to every chat in your account**. The protocol organizes work; it does not extend ChatGPT's technical capabilities.
