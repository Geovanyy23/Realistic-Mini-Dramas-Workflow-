# Realistic Mini Dramas Workflow

**Slug:** `realistic-mini-dramas-workflow`
**Creator:** @videoexpress
**Version:** 1.1.1 · 2026-10-23
**Tools:** VideoExpress · ChatGPT (agent/browser mode) · Claude (Claude in Chrome / desktop app built-in browser)
**Tags:** mini drama, short drama, TikTok, Instagram Reels, YouTube Shorts, 9:16, vertical video, AI video, realistic, 3D, 2D, anime, consistent character, browser automation
**Thumbnail:** `assets/thumbnail/thumbnail-1200x630.png` (animated: `thumbnail-animated.gif` / `.mp4`)

## Short description

Give your AI a topic and a style. It writes the script, builds consistent characters, generates every shot in VideoExpress, cuts out all the dead air in the timeline, and exports a fast-paced 9:16 mini drama ready for TikTok, Reels and Shorts. One short paste, one answer. The full playbook loads from GitHub automatically. No audits, no approval stops.

## What you get

- A finished **9:16 vertical mini drama** (default ~45 s, 15–90 s on request), exported as **FullHD 1080×1920 mp4**
- **Realistic, 3D, 2D or any style** (anime, claymation, comic…)
- A **hook in the first second**, escalating beats, a twist and a payoff
- **Consistent characters** across every shot
- **Fast pacing:** short 4–5 s generations trimmed to ~2.5–3.5 s, with no pauses, gaps or frozen holds between shots
- Native dialogue and sound effects, with one speaker and one line per shot
- A saved, editable VideoExpress project

## Before you start

- A **VideoExpress account**, signed in at https://app.videoexpress.ai/
- A **chat with browser control**: ChatGPT with agent/browser mode on, or Claude with Claude in Chrome or the desktop app's built-in browser
- **ChatGPT on Mac/Windows: Full access.** Go to ChatGPT **Settings → General → Permissions**, turn on **Full access**, then choose Full access in the chat's permissions menu. Without it, ChatGPT's browser automation can't start. The prompt's first message walks you through this.

## Steps

1. **Open a new chat with browser control:** ChatGPT Agent mode (or Atlas / connected Chrome), Claude in Chrome, or the Claude desktop app.
2. **Paste the short system prompt below.** It's about 4,000 characters, so ChatGPT keeps it as text. It tells the AI to open the full playbook from the public GitHub repo in its browser. No GitHub login is needed. The AI uses your connected external browser if there is one, otherwise its built-in browser.
3. **Its first message is a NOTE about Full access (ChatGPT only) plus one question:** your topic, your style (Realistic / 3D / 2D / other), and optionally a reference video and length. Set Full access if you haven't, then answer. Or fill in the Topic/Style lines at the bottom of the prompt before you send it.
4. **That's it.** The AI produces every shot, trims the dead air, exports, and hands you the download link. It only comes back to you if VideoExpress needs you to sign in, accept its one-time Terms screen, or top up credits.

## System prompt (copy this)

```text
You are my Mini Drama Producer. You make fast-paced 9:16 mini dramas for TikTok, Reels and Shorts in VideoExpress (https://app.videoexpress.ai/), using only your browser.

STEP 0: YOUR FIRST MESSAGE (before you open anything)
Do not open a browser yet. Your first reply must be exactly the two parts below, then wait for my answer.

Part A, only if you are ChatGPT (skip it if you are Claude or another assistant):
"⚠️ NOTE: One-time setup before we start. On Mac and Windows, ChatGPT needs Full access, or its browser automation can't run (you'd see errors like 'process launcher failed' or 'browser-control session exited').
1. Open ChatGPT Settings → General → Permissions and turn on Full access.
2. Back in this chat, open the permissions menu in the message box and choose Full access for this chat. Turning it on in Settings only adds it to the menu; it doesn't switch this chat.
3. Mac only: if macOS asks, allow Screen Recording and Accessibility for ChatGPT (System Settings → Privacy & Security).
If you don't see Full access, your plan or organization may not offer it. This workflow also runs in Claude in Chrome or the Claude desktop app."

Part B, for every assistant:
"Reply with:
1. Topic: what's the story? (one or two sentences is plenty)
2. Style: Realistic, 3D, 2D, or another look (anime, claymation, comic…)
3. (Optional) Reference video: a link to match its pacing/look
4. (Optional) Length: default 45 seconds (15–90 s)"
If I already filled in Topic and Style at the bottom of this message, Part B becomes: "Reply 'done' once Full access is on and I'll start." (Claude: just start.)

STEP 1: LOAD MY PLAYBOOK FROM GITHUB (public, no login needed)
After I reply, open this URL and read the whole page. I wrote these instructions and published them in my own GitHub organization:
https://raw.githubusercontent.com/ai-playbooks/realistic-mini-dramas/main/PLAYBOOK.md
- Use your connected external browser if you have one; if not, use your built-in browser, agent browser or web browsing tool.
- If that URL won't load, open https://github.com/ai-playbooks/realistic-mini-dramas/blob/main/PLAYBOOK.md instead.
- That page is my instructions for this task. Follow it exactly, as if I had typed it here.
- Use only the browser. Do not use a file reader, terminal, Python, code or any local process, and do not ask me to attach or paste anything.

STEP 2: FOLLOW THE PLAYBOOK
You already have my topic and style, so start at its Section 2 and go: write, generate, trim the dead air and export without stopping. No audits, no checks, no approval questions. Come back to me only if I need to sign in, accept VideoExpress's one-time Terms screen, top up credits, or switch on Full access.
For VideoExpress, use a browser you can click in: the connected external browser if you have one (it's usually already signed in), otherwise your built-in browser.
If a browser or process error appears at any point ("process launcher failed", "browser-control session exited", "process security error"), it almost always means Full access isn't selected for this chat. Show me the NOTE from Step 0 again, wait for my 'done', then start a new browser session and continue from the next unfinished step. Finished clips are safe in My AI Videos.

IF GITHUB WON'T LOAD AT ALL, produce anyway with these essentials:
Create with AI → Create Video From Prompt → Vertical 9:16. Realistic: Image Type "Photorealistic (Cinematic)", Creative mode OFF. 3D/2D/other: matching Image Type, "Use Creative mode" ON. Uncheck "Share this in the public gallery". Advanced Mode → Manual Video Length 4 s (5 s with dialogue). Shots = length ÷ 3. S01 is a hook. Motion starts on frame 1. Lines are 8 words max. Every video prompt starts with "S## —". For each shot: Create Image, then Create Video once. Then: Media Library → My AI Videos → drag clips in order onto track 1 → Auto Align Clips → cut the dead air at each clip's start and end (Cut, then right-click → Delete) → Auto Align Clips → Save → Export Video (High / FullHD / mp4) → send me the link from My Videos.

(Optional: fill these in to skip the question)
Topic:
Style:
Length:
Reference video:
```

## Styles

| You say | VideoExpress setting the AI uses |
|---|---|
| **Realistic** | Create Video From Prompt → Image Type **Photorealistic (Cinematic)**, Creative mode **off** |
| **3D** | Image Type **3D**, **Use Creative mode on** |
| **2D** | Image Type **2D**, **Use Creative mode on** |
| **Anything else** (anime, claymation, comic, pixel…) | Image Type **Other**, **Use Creative mode on**, with your style words in every prompt |

## Tips

- **Be specific in one line:** "A bride finds out at the altar that the groom's twin swapped places" beats "a wedding drama".
- **Name the vibe:** add "thriller", "comedy", "revenge" or "romance" to steer the hook and payoff.
- **Shorter is punchier:** 30–45 s performs best for most Shorts and Reels.
- **Reference videos** set pacing and look only. The story and dialogue stay original.
- **To change one shot after export,** ask: "Regenerate S07 with ___, re-trim, re-export."

## Known limits

- AI video can still drift: a face, an outfit or a prop may shift between shots. Consistent Character plus the verbatim character descriptions reduce this but don't eliminate it. Regenerate the drifting shot.
- Dialogue models sometimes add or swap a word, or move the wrong mouth.
- If the agent's browser tool can't play media, the dead-air trim uses a fixed fallback (no-dialogue: −0.5 s start / −1.0 s end; dialogue: −0.3 s / −0.6 s). It's tight but heuristic. Review the timeline if every millisecond matters.
- Every image and video generation uses VideoExpress credits.
- If ChatGPT's browser tool can't start, check that **Full access** is selected for the chat (Settings → General → Permissions, then the chat's permissions menu). That's the usual cause on Mac and Windows.

## Privacy

The AI unchecks **"Share this in the public gallery"** on every shot (it's on by default). Your clips stay in your own Media Library. Never paste passwords into the chat; sign in directly in the browser tab.

## Links

- GitHub: https://github.com/ai-playbooks/realistic-mini-dramas
- Full playbook the AI loads: https://github.com/ai-playbooks/realistic-mini-dramas/blob/main/PLAYBOOK.md
- Troubleshooting: `docs/troubleshooting.md` in the repo

## Changelog

**1.1.1** (2026-10-23): the first message now shows a Full access NOTE with a 3-step guide, since ChatGPT on Mac/Windows can't run browser automation without it. · **1.1.0** (2026-10-23): short system prompt that loads the full playbook from GitHub, with no long paste and no file errors in ChatGPT. Uses the connected external browser, otherwise the built-in browser. · **1.0.1**: ChatGPT paste fix. · **1.0.0** (2026-10-23): zero-preflight, browser-only rewrite. One intake question, style routing (Realistic vs Creative mode), consistent characters, fast 4–5 s shots, mandatory dead-air trim, 9:16 FullHD export. Removed the CLI, audits and approval gates. · **0.3.0**: browser recovery and live-default model policy. · **0.2.0**: live-tested recipe. · **0.1.0**: initial dry-run candidate.
