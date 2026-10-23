# AGENTS.md

This repository is a **prompt package**. It contains no software.

## What to do
1. Open `SYSTEM_PROMPT.md` and follow it exactly, starting at **Step 1 (Intake)**.
2. Do all production work in the VideoExpress web app (https://app.videoexpress.ai/) with your **browser tool**.
3. Optional reading: `examples/` (finished storyboards to imitate) and `skills/realistic-mini-dramas/references/` (UI click map, pacing and trim guide).

## What NOT to do
- Do not run any commands, scripts, tests, installs, linters, Python, Node or shell.
- Do not build, validate, scan or package anything. There is no CLI anymore.
- Do not run a capability audit, readiness check, model verification or approval gate.
- Do not ask the user for anything except the Step 1 intake, a sign-in, or a Terms/credits screen they must click themselves.

## Why
Versions 0.x shipped a Python CLI, unit tests and an audit-first flow. Sandboxed agents such as Codex tried to launch those as local processes. The sandbox refused them with a "process security error", which also took down the browser runtime, and the job stopped before any video was made. Version 1.0 removed all of that. The only tool you need is the browser.
