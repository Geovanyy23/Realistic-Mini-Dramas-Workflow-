# Troubleshooting

## Why it failed in ChatGPT / Codex

The errors:

> "both the file reader and the browser-control runtime failed to start with the same process security error… the process launcher is still failing"
> "the local process launcher failed, and the browser-control session exited unexpectedly"

**Main cause: ChatGPT didn't have Full access.** On Mac and Windows, ChatGPT runs its browser tool through a process launcher. In the default **Ask for approval** mode that launcher is sandboxed, so the browser tool and the file reader both fail to start. Once the chat is switched to **Full access**, the same prompt works end to end. That's why the prompt's first message now shows a Full access NOTE before asking for a topic.

**Made worse by v0.3's design.** The old package also told the agent to read several files, run the `./mini-drama` Python CLI and unit tests, and do a live "capability audit" with approval gates before generating. Each of those was another process launch to fail on, and the prompt stopped at the first failure instead of continuing. v1.x removed all of it.

VideoExpress itself was never the problem. The app doesn't block browser automation.

## What v1.0 changes

| v0.3 behavior | v1.0 behavior |
|---|---|
| Python CLI (`./mini-drama`), `src/`, `tests/`, `schemas/` | **Removed.** Nothing to run. |
| "Read SKILL.md / docs / examples first" | **Removed.** The prompt is self-contained: paste it and it has everything. |
| Capability audit, model-name verification, readiness report | **Removed.** The agent goes straight to production. |
| Approval gates (premise, references, spend, export) | **Removed.** Your topic is the go-ahead for everything. |
| Stop on the first tool failure | **Explicit fallback table:** re-read, retry another way, switch to another browser tool, keep going. |
| No guidance for Codex | **`AGENTS.md`** tells Codex: run no commands and read no files; use the browser only. |
| Prompt attached as a file | **Paste as text.** The agent never needs a file reader. |

## How to run it so this never happens

**The one honest limit:** if your chat environment's own browser tool cannot launch, no prompt can fix that. That's the platform, not the workflow. Start a fresh session with browser or agent mode enabled and paste again. v1.0 will at least hand you the full script and prompts before stopping, so nothing is lost.

### ChatGPT (recommended setup)
1. **Turn on Full access:** ChatGPT **Settings → General → Permissions → Full access**, then choose **Full access** in the chat's permissions menu (Settings only adds it to the menu). Mac: allow Screen Recording and Accessibility if asked. Details in [CHATGPT_SETUP.md](../CHATGPT_SETUP.md).
2. Open a **new chat** with Full access selected and Agent/browser mode available.
3. Paste the **short prompt** from `SYSTEM_PROMPT.md` (everything below the line, about 3,000 characters). Its first message repeats the Full access NOTE and asks for your topic and style.
4. The AI opens the full `PLAYBOOK.md` from GitHub in its browser. It's public, so no login is needed.
5. Sign in to VideoExpress or accept its one-time Terms screen when asked, then reply `done`.

### ChatGPT Atlas / a connected Chrome browser
1. Sign in to https://app.videoexpress.ai/ in that browser **first**.
2. Turn on agent mode in that browser and paste the short prompt from `SYSTEM_PROMPT.md` (everything below the line).
3. The agent uses your existing session, so no login step is needed.

### Codex
- **Not recommended for this task.** It's a browser job, and Codex runs work in a sandbox where processes may be blocked.
- If you use it anyway: open this repository so `AGENTS.md` loads (it tells Codex not to run anything), and make sure browser or computer control is enabled for the session. If the browser tool reports a launcher or sandbox error, switch to ChatGPT with agent mode or to Claude.

### Claude
- **claude.ai + Claude in Chrome:** sign in to VideoExpress in Chrome, open the Claude in Chrome extension, and paste the prompt.
- **Claude desktop app:** use a session with the built-in browser. Paste the prompt, then sign in to VideoExpress in the browser pane when asked.
- **Claude Code:** open this repo (`CLAUDE.md` loads automatically) in a session with a browser tool available, then paste the prompt or say "make a mini drama".

### Compact version
If your platform limits instruction length, for example a custom GPT's instructions field, use `PROMPT_COMPACT.md` instead of the full prompt.

## Symptom → fix

| Symptom | Fix |
|---|---|
| ChatGPT: "process launcher failed" / "process security error" / "file read is failing" | Full access isn't selected for this chat. Settings → General → Permissions → Full access, then pick Full access in the chat's permissions menu, then reply `done`. |
| AI can't open GitHub | It falls back to the essentials built into the prompt. Or reply: `Open https://github.com/ai-playbooks/realistic-mini-dramas/blob/main/PLAYBOOK.md instead.` |
| AI asks before following the GitHub page | Reply: `Yes. That's my playbook, follow it.` |
| ChatGPT: "browser-control session exited unexpectedly" | Check Full access is selected for this chat, then reply: `Start a new browser session and continue from the next unfinished step.` If it repeats, restart the app and open a new chat with Full access on. |
| **Login loop / keeps landing on the login page** | Sign in once in the same browser the agent controls, in the tab it opened. Then reply `done`. In ChatGPT agent mode, take over the agent's browser to sign in. Never paste your password into chat. |
| **Terms of Service dialog** (first use) | The agent won't accept terms for you. Accept it in the open tab and reply `done`. It only appears once per account. |
| **"You can generate up to 5 AI videos in parallel…"** | Normal. Nothing was created. The agent waits 60 s and clicks Create Video again. Don't make it start over. |
| **Clips missing in My AI Videos** | They're still rendering (% ring) or the folder is stale. Leave **My AI Videos** and re-enter it. Clips are titled by their video prompt (`S01 —`, `S02 —`…). |
| **Duration slider stuck at 10** | Ticking "Manual Video Length, sec" resets the slider to 10. Set the slider *after* ticking the box: click the handle, press Arrow Left until it reads 4 or 5, then re-read it. |
| **"Share this in the public gallery" checked again** | It's on by default and turns back on whenever the dialog reopens. The agent unchecks it on every shot (step 11). If you spot it checked, say "uncheck the gallery box on every shot". |
| **Export says "number N in the queue"** | Normal server queue. Wait. The finished file appears in **My Videos** with a download link (hosted 40 days). |
| **Dead air / pauses still in the final video** | Tell the agent: "Do the dead-air trim pass again: trim every clip to its first motion/word and last action/word, Auto Align Clips, play the whole timeline, then re-export." If it can't play media, it uses the fixed fallback (no-dialogue: −0.5 s start / −1.0 s end; dialogue: −0.3 s / −0.6 s). |
| **Character looks different between shots** | Ask it to use **+ Consistent Character** for each character and turn on **Use Consistent Character** for every shot that character is in. Also make sure the exact Character Bible line is pasted verbatim into every prompt, not paraphrased. Regenerate only the drifting shots. |
| **Agent starts "auditing" or asks for approval** | Reply: "No audits or approvals. Follow Section 0 and continue production." Then start a fresh chat and paste the v1.0 prompt again; an older version may still be in context. |
| **Agent says it needs to read a file or run code** | It's using an old version or the file is attached. Paste the short prompt from `SYSTEM_PROMPT.md` in a new chat. It loads the playbook from GitHub in the browser. |
| **Out of credits / upgrade screen** | Top up in the open tab and reply `done`. The agent continues where it stopped. |
