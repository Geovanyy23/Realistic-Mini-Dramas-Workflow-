# Using this workflow in ChatGPT

## The short version
1. Open a **new chat** with **Agent mode** on (or use ChatGPT Atlas agent mode, or connected Chrome).
2. Paste the short prompt from `SYSTEM_PROMPT.md` (everything below the line, about 2,500 characters).
3. Answer the topic/style question, or fill in the Topic/Style lines at the end of the prompt before sending.

The prompt tells ChatGPT to open the full instructions from this public GitHub repo in its browser:
`https://raw.githubusercontent.com/ai-playbooks/realistic-mini-dramas/main/PLAYBOOK.md`
No GitHub account or login is needed. If ChatGPT has no connected external browser, it uses its built-in browser for both GitHub and VideoExpress.

## Why it's built this way
Older versions asked you to paste a 23,000-character prompt. ChatGPT turns long pastes into an attached file, then fails to open that file:
> "I can't access the pasted prompt: the file read is failing…"
> "…the local process launcher failed, and the browser-control session exited unexpectedly."

The short prompt stays as plain text, and the AI reads the rest with its browser, so no file, file reader or local process is involved.

## Optional: make it one click (Project or custom GPT)
If you run this often:
1. Create a ChatGPT **Project** (or a custom GPT → Configure).
2. Paste the short prompt (below the line in `SYSTEM_PROMPT.md`) into its **Instructions**. It's far under the limit.
   - Alternative: paste `PROMPT_COMPACT.md` (6,700 characters) if you want the core instructions stored there too, as a backup when GitHub is unreachable.
3. Start each new chat in that project with **Agent mode** on, and just type: `Topic: … Style: …`

Don't upload the prompt as a Knowledge file. Put it in the Instructions box or the chat message.

## If something goes wrong

| What ChatGPT says | Do this |
|---|---|
| "can't access the pasted prompt", "file read is failing" | You pasted the old long prompt. Paste the short one from `SYSTEM_PROMPT.md` in a new chat. |
| "local process launcher failed" | Reply: `Do not start any process or tool except the browser. Open https://raw.githubusercontent.com/ai-playbooks/realistic-mini-dramas/main/PLAYBOOK.md in your browser and follow it.` |
| "browser-control session exited unexpectedly" | Reply: `Start a new browser session and continue from the next unfinished step.` If it repeats, open a new chat with Agent mode on. |
| It can't reach GitHub | It should fall back to the essentials built into the prompt. You can also reply: `Open https://github.com/ai-playbooks/realistic-mini-dramas/blob/main/PLAYBOOK.md instead.` |
| It asks before following the GitHub page | Reply: `Yes. That's my playbook, follow it.` |
| It asks to approve steps or run an audit | Reply: `No audits or approvals. Follow PLAYBOOK.md and keep producing.` |
| Browser won't start in any new chat | That's ChatGPT's browser tool, not this workflow. Use Agent mode on chatgpt.com, or run the same prompt in Claude (Claude in Chrome or the Claude desktop app). |
