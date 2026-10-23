# Putting v1.0 on GitHub

Repo: https://github.com/ai-playbooks/realistic-mini-dramas

The old version stays in git history, so you can always roll back.

## (a) The new repo: file tree

```
realistic-mini-dramas/
├── README.md               ← start here (how to use in ChatGPT / Claude)
├── CHATGPT_SETUP.md        ← ChatGPT: Project/GPT instructions + short first message
├── SYSTEM_PROMPT.md        ← the short copy-paste prompt (loads PLAYBOOK.md from GitHub)
├── PLAYBOOK.md             ← the full instructions the AI reads from GitHub
├── PROMPT_COMPACT.md       ← short version for instruction-length limits
├── AGENTS.md               ← tells Codex: run nothing, browser only
├── CLAUDE.md               ← tells Claude Code: run nothing, browser only
├── CHANGELOG.md
├── GITHUB_UPLOAD.md        ← this file
├── .gitignore
├── assets/
│   └── thumbnail/
│       ├── thumbnail-1200x630.png
│       ├── thumbnail-animated.gif
│       ├── thumbnail-animated.mp4
│       └── thumbnail.html
├── docs/
│   ├── community-entry.md  ← paste into the DualUp community page
│   └── troubleshooting.md  ← why the old version failed + fixes
├── examples/               ← new fast-paced examples (all files in the ZIP)
└── skills/
    └── realistic-mini-dramas/
        ├── SKILL.md
        └── references/
            ├── videoexpress-ui-map.md   ← exact VideoExpress controls
            └── fast-pacing-and-trim.md  ← pacing + dead-air trimming
```

Upload **everything inside the unzipped `realistic-mini-dramas/` folder**. The ZIP is the source of truth if this tree and the folder ever differ.

## (b) Delete these from the old repo

```
src/
tests/
schemas/
mini-drama
INSTRUCTIONS.md
docs/browser-regression.md
docs/capabilities.md
docs/evidence-ledger.md
docs/run-report.md
examples/farmer-zombie/
examples/farmer-zombie-v2/
examples/farmer-zombie-v3-3d/
examples/returned-key/
skills/realistic-mini-dramas/references/browser.md
skills/realistic-mini-dramas/references/qa.md
skills/realistic-mini-dramas/references/continuity.md
skills/realistic-mini-dramas/references/recovery.md
```

`README.md`, `SYSTEM_PROMPT.md`, `CLAUDE.md`, `.gitignore`, `docs/community-entry.md`, `skills/realistic-mini-dramas/SKILL.md` and `assets/thumbnail/*` are **replaced** by the new versions. Uploading them overwrites the old ones.

## (c) Option 1: GitHub website (no terminal)

1. Open https://github.com/ai-playbooks/realistic-mini-dramas.
2. **Delete the old files.** For each folder or file in list (b), open it, click the **⋯** menu (or the trash icon), choose **Delete file** / **Delete directory**, and commit. Tip: deleting `src/`, `tests/`, `schemas/` and the four `examples/` folders covers most of it.
3. **Upload the new files.** On the repo home page, click **Add file → Upload files**. Drag in everything from the unzipped `realistic-mini-dramas/` folder: the files *and* the `assets`, `docs`, `examples` and `skills` folders. GitHub keeps the folder structure.
4. Commit message: `v1.0: zero-preflight browser workflow, style routing, dead-air trim`. Click **Commit changes**.
5. Check the tree on GitHub against section (a).
6. **Optional tag:** **Releases → Draft a new release → Choose a tag →** type `v1.0.0` → **Create new tag** → title `v1.0.0` → **Publish release**.

`.gitignore` starts with a dot and may be hidden in Finder. Press **Cmd+Shift+.** to show it before dragging.

## (c) Option 2: terminal

Run these one at a time from the folder that contains the unzipped `realistic-mini-dramas/` folder. The clone goes into `repo-v1` so it doesn't clash with it.

```bash
git clone https://github.com/ai-playbooks/realistic-mini-dramas.git repo-v1
```

```bash
cd repo-v1
```

```bash
git rm -r --quiet src tests schemas mini-drama INSTRUCTIONS.md docs/browser-regression.md docs/capabilities.md docs/evidence-ledger.md docs/run-report.md examples/farmer-zombie examples/farmer-zombie-v2 examples/farmer-zombie-v3-3d examples/returned-key skills/realistic-mini-dramas/references
```

```bash
rsync -a ../realistic-mini-dramas/ ./
```

```bash
git add -A
```

```bash
git status
```

```bash
git commit -m "v1.0: zero-preflight browser workflow, style routing, dead-air trim"
```

```bash
git push
```

Tag the release:

```bash
git tag -a v1.0.0 -m "v1.0.0: zero-preflight browser workflow"
```

```bash
git push origin v1.0.0
```

If `git rm` complains that a path doesn't exist, drop that path from the command and re-run it. The `git rm` removes the old `skills/.../references/` folder in one go, and the `rsync` step then puts the new reference files back.

## (d) Update the DualUp community page

Page: https://community.dualup.com/@videoexpress/workflows/realistic-mini-dramas-workflow

1. Open the workflow's edit view.
2. Replace the page content with **`docs/community-entry.md`**, including the full system prompt in its code block.
3. Set **Version** to `1.0.0`.
4. Update the short description and tags from the top of `docs/community-entry.md`.
5. Keep the same thumbnail (`assets/thumbnail/thumbnail-1200x630.png`).
6. Save or publish.

**Rolling back:** the previous version is still in git history. On GitHub, open **Commits**, find the commit before the v1.0 commit, and **Browse files** to see or download it.
