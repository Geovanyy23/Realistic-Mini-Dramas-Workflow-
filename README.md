# Realistic Mini Dramas: VideoExpress Workflow v1.0

Paste one prompt, name a topic and pick a style. Your AI agent then builds a **fast-paced 9:16 mini drama** for TikTok, Reels and Shorts inside [VideoExpress](https://app.videoexpress.ai/). It writes the script and storyboard, creates consistent characters, generates every shot, **cuts the dead air** on the timeline and exports a 1080×1920 MP4.

![Realistic Mini Dramas](assets/thumbnail/thumbnail-1200x630.png)

**Community page:** [Realistic Mini Dramas Workflow](https://community.dualup.com/@videoexpress/workflows/realistic-mini-dramas-workflow)

## Quick start (2 minutes)

1. **Sign in** to https://app.videoexpress.ai/ (or sign in when the agent asks).
2. Open a **new chat that can control a browser**:
   - **ChatGPT:** Agent mode (or Atlas agent mode, or connected Chrome)
   - **Claude:** Claude in Chrome, or the Claude desktop app's built-in browser
3. **Paste the short prompt** from [SYSTEM_PROMPT.md](SYSTEM_PROMPT.md) (everything below the line, about 2,500 characters). It tells the AI to open the full [PLAYBOOK.md](PLAYBOOK.md) from this public repo in its browser. No GitHub login is needed, and it's short enough that ChatGPT keeps it as text instead of turning it into a file.
4. Answer the one question (or fill in the Topic/Style lines at the end of the prompt):
   - **Topic:** e.g. "A bride finds out her groom is her sister's ex"
   - **Style:** **Realistic**, **3D**, **2D**, or anything else (anime, claymation…)
   - *(optional)* a reference video link, and a length (default 45 s)
5. Wait. The agent produces, trims and exports, then sends you the download link.

There's no audit, no preflight and no approval step. The agent only comes back to you if VideoExpress needs you to sign in, accept its one-time Terms or top up credits.

## How it works

| Stage | What the agent does in VideoExpress |
|---|---|
| Script and storyboard | Hook-first story, about 3 s per shot (45 s ≈ 15 shots), 8-word lines max, twist at ~70% |
| Characters | Character Bible plus **+ Consistent Character** references |
| Style routing | **Realistic** → *Create Video From Prompt*, Image Type **Photorealistic (Cinematic)**, Creative mode **off**. **3D / 2D / other** → Image Type 3D / 2D / Other with **Use Creative mode on** |
| Shots | Image first, then video. 4 s clips (5 s with dialogue), motion from frame 1, no music, public gallery off |
| Edit | Clips placed in order on track 1 with **Auto Align Clips** |
| **Dead-air trim** | Every frozen or silent head and tail cut out (Cut + Delete at 40 px/s), gaps closed |
| Export | High / FullHD 1080×1920 / MP4, with the link from **My Videos** |

## Files

| File | Use it for |
|---|---|
| [SYSTEM_PROMPT.md](SYSTEM_PROMPT.md) | **The prompt to paste.** Short, and loads PLAYBOOK.md from GitHub. Also what goes on the community page |
| [PLAYBOOK.md](PLAYBOOK.md) | **The full instructions** the AI reads from GitHub. Edit this to update every user at once |
| [CHATGPT_SETUP.md](CHATGPT_SETUP.md) | ChatGPT tips, plus an optional Project/custom GPT setup |
| [PROMPT_COMPACT.md](PROMPT_COMPACT.md) | Under 8,000 characters, for custom GPT instructions or Claude Project instructions |
| [examples/](examples/) | Complete storyboards (Realistic, 3D, 2D) with every prompt written out |
| [skills/realistic-mini-dramas/](skills/realistic-mini-dramas/) | Agent Skill version with the VideoExpress UI map and pacing/trim guide |
| [AGENTS.md](AGENTS.md) / [CLAUDE.md](CLAUDE.md) | Auto-loaded by Codex / Claude Code: "run nothing, use the browser" |
| [docs/troubleshooting.md](docs/troubleshooting.md) | Why v0.3 failed in ChatGPT/Codex, plus symptom → fix |
| [docs/community-entry.md](docs/community-entry.md) | Copy-ready text for the DualUp community page |
| [GITHUB_UPLOAD.md](GITHUB_UPLOAD.md) | How to replace the old repo contents with v1.0 |

## Make a custom GPT or Claude Project (optional)
Paste [PROMPT_COMPACT.md](PROMPT_COMPACT.md) (the part below the line) into the instructions field and turn on browsing/agent capability. Then every new chat starts with the intake question.

## Good to know
- Each image and video generation uses your VideoExpress credits. A 45 s drama is about 15 images plus 15 videos, plus a few retries.
- VideoExpress renders up to 5 videos in parallel. The agent waits and retries automatically when the cap is hit.
- AI video can still drift (a face changes, an extra word gets spoken). The Character Bible plus Consistent Character keep that to a minimum.
- Exports stay in **My Videos** for 40 days.

See [CHANGELOG.md](CHANGELOG.md) for what changed from v0.3.
