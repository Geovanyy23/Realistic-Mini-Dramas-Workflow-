# Using this workflow in ChatGPT (Mac and Windows)

## The one setting that matters: Full access
ChatGPT's browser automation runs through a process launcher. In the default **Ask for approval** mode that launcher is sandboxed, and the browser tool can't start. You then see errors like:

> "the local process launcher failed, and the browser-control session exited unexpectedly"
> "both the file reader and the browser-control runtime failed to start with the same process security error"

Once **Full access** is on, the same prompt works. The prompt's first message tells users this before it asks for a topic, so nobody gets stuck.

### Turn it on (one time)
1. Open ChatGPT **Settings → General → Permissions** and turn on **Full access**.
2. Back in the chat, open the **permissions menu in the message box** and choose **Full access** for that chat. Turning it on in Settings only adds it to the menu; it doesn't switch an existing chat.
3. **Mac only:** when macOS asks, allow **Screen Recording** and **Accessibility** for ChatGPT (System Settings → Privacy & Security). Without them ChatGPT can see the browser but not click in it.
4. If **Full access** isn't offered, your plan or organization has turned it off. Run the workflow in Claude in Chrome or the Claude desktop app instead.

Full access lets ChatGPT run commands and edit files without asking, so use it in a chat dedicated to this workflow, and switch back afterwards if you prefer.

## Run the workflow
1. Open a **new chat** in the ChatGPT app with **Full access** selected and Agent/browser mode available.
2. Paste the short prompt from `SYSTEM_PROMPT.md` (everything below the line).
3. ChatGPT's first message shows the Full access NOTE and asks for your topic and style. Reply.
4. ChatGPT opens the full instructions from this public GitHub repo in its browser (`https://raw.githubusercontent.com/ai-playbooks/realistic-mini-dramas/main/PLAYBOOK.md`, no login needed), then produces, trims and exports.
5. Sign in to VideoExpress or accept its one-time Terms screen when asked, then reply `done`.

## Optional: make it one click (Project or custom GPT)
1. Create a ChatGPT **Project** (or a custom GPT → Configure).
2. Paste the short prompt (below the line in `SYSTEM_PROMPT.md`) into its **Instructions**.
   - Alternative: paste `PROMPT_COMPACT.md` (about 7,000 characters) to keep the core instructions there too, as a backup when GitHub is unreachable.
3. Start each new chat in that project with Full access selected, and just type: `Topic: … Style: …`

Don't upload the prompt as a Knowledge file. Put it in the Instructions box or the chat message.

## If something goes wrong

| What ChatGPT says | Do this |
|---|---|
| "process launcher failed", "process security error", "browser-control session exited" | Full access isn't selected for this chat. Do the 3 steps above, then reply `done`. ChatGPT starts a new browser session and continues; finished clips are safe in My AI Videos. |
| "can't access the pasted prompt", "file read is failing" | Same cause, plus the file reader was blocked. Set Full access, then paste the short prompt in a new chat. |
| ChatGPT can see the browser but clicks do nothing (Mac) | Grant Screen Recording and Accessibility to ChatGPT in System Settings → Privacy & Security, then restart ChatGPT. |
| It can't reach GitHub | It falls back to the essentials built into the prompt. Or reply: `Open https://github.com/ai-playbooks/realistic-mini-dramas/blob/main/PLAYBOOK.md instead.` |
| It asks before following the GitHub page | Reply: `Yes. That's my playbook, follow it.` |
| It asks to approve steps or run an audit | Reply: `No audits or approvals. Follow PLAYBOOK.md and keep producing.` |
| Browser won't start even with Full access on | Restart the ChatGPT app and open a new chat with Full access selected. If it still fails, run the same prompt in Claude (Claude in Chrome or the Claude desktop app). |
