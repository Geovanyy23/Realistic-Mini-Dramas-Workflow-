# Changelog

## 1.1.1 (2026-10-23): Full access note first

- **Root cause confirmed:** on Mac and Windows, ChatGPT's browser automation can't start unless the chat is in **Full access** mode (Settings → General → Permissions, then selected in the chat). The earlier "process launcher failed" errors were this, not VideoExpress and not the long paste.
- The prompt's **first message now shows a Full access NOTE** with a 3-step guide (plus Mac Screen Recording/Accessibility) before asking for the topic. Claude and other assistants skip the note.
- Browser/process errors during a run now trigger the same note and a "reply done" wait, then a new browser session.
- `CHATGPT_SETUP.md`, README, troubleshooting, PROMPT_COMPACT and the community page updated to match.

## 1.1.0 (2026-10-23): load the playbook from GitHub

- **`SYSTEM_PROMPT.md` is now a short prompt (about 2,500 characters)** that tells the AI to open the full instructions from GitHub in its browser: `https://raw.githubusercontent.com/ai-playbooks/realistic-mini-dramas/main/PLAYBOOK.md`, falling back to the github.com page. It's public, so no login is needed. Short enough that ChatGPT keeps it as text instead of turning it into a file.
- **New `PLAYBOOK.md`:** the full instruction set, moved here from the old long SYSTEM_PROMPT. Updating it on GitHub updates every user at once.
- The prompt says which browser to use: the connected external browser if there is one, otherwise the built-in browser, both for reading GitHub and for working in VideoExpress.
- Built-in fallback essentials, so the AI can still produce if GitHub won't load.
- README, CHATGPT_SETUP, AGENTS/CLAUDE.md, the skill, the examples and the community page now point to PLAYBOOK.md.

## 1.0.1 (2026-10-23): ChatGPT paste fix

- **CHATGPT_SETUP.md:** ChatGPT turns long pastes into a file and then fails to open it ("file read is failing", "process launcher failed"). The instructions now go in Project or custom GPT Instructions, and you send a short first message.
- Both prompts now forbid opening "pasted text" attachments or starting local processes, and say how to recover when the browser-control session exits.
- README and troubleshooting point ChatGPT users to the new setup.

## 1.0.0 (2026-10-23): zero-preflight browser workflow

A rewrite that makes the workflow run out of the box in ChatGPT and Claude through browser automation alone.

### Removed
- The Python CLI (`mini-drama`, `src/mini_drama/`), unit tests (`tests/`) and JSON schemas (`schemas/`). In sandboxed agents like Codex, running these tripped the "process security error" that also took down the browser runtime.
- The capability audit, model-name verification, readiness report, approval gates (A/B/C/E), state machine and operation-count limits.
- Instructions to read other repo files before starting.
- Old example packs (`returned-key`, `farmer-zombie`, `-v2`, `-v3-3d`) and the observation docs (`browser-regression`, `capabilities`, `evidence-ledger`, `run-report`). They remain in git history.

### Added / changed
- **Self-contained prompt** (`SYSTEM_PROMPT.md`): paste it as text and it carries everything. Browser only: no code, no terminal, no file reading.
- **Compact prompt** (`PROMPT_COMPACT.md`) for platforms with instruction-length limits.
- **One intake question:** topic, style (Realistic / 3D / 2D / other), an optional reference video and an optional length (default 45 s).
- **Style routing:** Realistic → Image Type *Photorealistic (Cinematic)* with Creative mode **off**. 3D / 2D / other → matching Image Type with Creative mode **on**.
- **Consistent characters through VideoExpress** (+ Consistent Character, then Use Consistent Character on each shot), with a verbatim Character Bible as fallback.
- **Fast-paced generation:** clips are generated at 4 s (action) or 5 s (dialogue). Prompts start motion on frame 1 and end on the action. Lines are 8 words or fewer, with one speaker per shot. S01 is the hook.
- **Mandatory dead-air trim pass** in the VideoExpress timeline before export (2.5–3.5 s per clip, no gaps), with a fixed fallback trim when the agent can't play media.
- **9:16 vertical** is the default everywhere, exported at FullHD 1080×1920 mp4.
- **Never-stop error table:** retry another way, switch browser tool, and ask the user only for login, terms or credits.
- `AGENTS.md` (Codex) and `CLAUDE.md` (Claude Code) say run nothing and use the browser.
- New examples, `docs/troubleshooting.md`, an updated `docs/community-entry.md` and `GITHUB_UPLOAD.md`.

## 0.3.0 (2026-10-23)
- Browser-startup recovery branch, and live-default model policy (a hidden model name no longer blocked).
- Still required an audit phase, approval gates and operation limits, and pointed agents at the local CLI.

## 0.2.0 (2026-10-23)
- Live-tested per-shot recipe (three "Hold the Line" pilots), 5-parallel queue cap documented, thumbnail added.

## 0.1.0
- Initial candidate: four-shot dialogue pilot ("The Returned Key"), dry-run CLI only.
