# ChatGPT setup (do this once)

## The error this fixes
> "I can't access the pasted prompt: the file read is failing before the command can start…"
> "…the local process launcher failed, and the browser-control session exited unexpectedly."

**Cause:** ChatGPT turns a long paste into an attached file. `SYSTEM_PROMPT.md` is about 23,000 characters, so your paste became a file. To read a file, ChatGPT starts a sandbox process, and that process launch is what failed. The browser session went down with it. VideoExpress was never reached.

**Fix:** never paste the long prompt into a chat message. Put the instructions in an **instructions field**, which ChatGPT reads directly with no file and no process. Then send a short message (below) that's small enough to stay as text.

## Step 1: Put the instructions in an instructions field (pick ONE)

**Option A: a ChatGPT Project (simplest)**
1. In ChatGPT's sidebar, create a new **Project** called `Mini Dramas`.
2. Open the project's **Instructions** setting.
3. Open `PROMPT_COMPACT.md`, copy everything **below the `---` line** (about 6,500 characters) and paste it into Instructions. Save.

**Option B: a custom GPT**
1. Explore GPTs → **Create** → **Configure**.
2. Paste the same text (everything below the `---` in `PROMPT_COMPACT.md`) into **Instructions**. It fits the 8,000-character limit.
3. Turn on the browsing/agent capability if it's offered, then save it (Only me is fine).

Don't upload the prompt under "Knowledge" or "Files". It has to be in the Instructions box.

## Step 2: Start a fresh chat the right way
1. Open a **new chat inside the project** (or with your GPT).
2. Turn on **Agent mode** (the mode where ChatGPT controls its own browser). Use chatgpt.com or ChatGPT Atlas.
3. Don't attach anything. Paste ONLY the short message below as your first message.

## Step 3: Paste this as your first message (short enough to stay as text)

```
Follow your Mini Drama Producer instructions. They are already in your instructions. There is no file to read, so do not open, read or request any file or attachment, and do not start a terminal, Python or any local process. Use only your browser: open https://app.videoexpress.ai/ and work there. If the browser session closes, start a new browser session once and continue. Finished clips are saved in My AI Videos.

Topic: [your story in one or two sentences]
Style: [Realistic / 3D / 2D / other]
Length: [optional, default 45 seconds]
Reference video: [optional link]
```

Fill in the topic and style yourself, or leave the brackets in and it will ask you.

## If it still fails

| What ChatGPT says | What it means | Do this |
|---|---|---|
| "can't access the pasted prompt", "file read is failing" | Your message became a file | Your message is too long. Send only the short message from Step 3. The long prompt goes in Instructions. |
| "local process launcher failed" | ChatGPT tried to start a sandbox or terminal | Paste: `Do not start any process or tool except the browser. Open https://app.videoexpress.ai/ now.` |
| "browser-control session exited unexpectedly" | ChatGPT's own browser crashed | Paste: `Start a new browser session and continue from the next unfinished step.` If it happens again, open a new chat in the project with Agent mode on. |
| Browser won't start at all, in a new chat too | ChatGPT's browser isn't available in this mode or app | Switch to Agent mode on chatgpt.com, or use Claude (Claude in Chrome or the Claude desktop app). The same prompt works there. |
| It asks you to approve steps or run an audit | It's not reading the instructions field | Check that the text is in **Instructions**, not uploaded as a file. |

**The honest limit:** if ChatGPT's own browser tool crashes in every chat, that's a ChatGPT platform issue, and no prompt text can repair it. Agent mode on chatgpt.com is the most reliable place to run this in ChatGPT. Codex isn't a good fit for this task.
