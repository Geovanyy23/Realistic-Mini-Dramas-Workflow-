---
name: realistic-mini-dramas
description: Produce a fast-paced vertical 9:16 mini drama (TikTok / Reels / Shorts) end to end in the VideoExpress web app with a browser - script, storyboard, consistent characters, image-to-video generation, dead-air trimming and export. Use when the user asks for a mini drama, short drama, micro drama, TikTok/Reels/Shorts drama or a VideoExpress drama video, in any style (realistic, 3D, 2D, anime, other).
---

# Mini Dramas in VideoExpress

The full recipe is `../../SYSTEM_PROMPT.md` at the repository root. Follow it exactly. It is self-contained.

## Non-negotiables
1. **Browser only.** Work at https://app.videoexpress.ai/. Run no code, shell, tests or file processing.
2. **No preflight.** No capability audit, readiness check, model verification, cost estimate or approval gate.
3. **One question.** Ask for the topic, style (Realistic / 3D / 2D / other), an optional reference video and an optional length (default 45 s). Then produce without stopping.
4. **Style routing.** In Create Video From Prompt:
   - Realistic → Image Type **Photorealistic (Cinematic)**, **Use Creative mode OFF**
   - 3D → Image Type **3D**, Creative mode **ON**
   - 2D → Image Type **2D**, Creative mode **ON**
   - other → Image Type **Other**, Creative mode **ON**
5. **Fast pacing.** Shots = length ÷ 3. Generate each clip at 4 s (no dialogue) or 5 s (dialogue). Motion starts on frame 1. Lines are 8 words max, one speaker per shot.
6. **Dead-air trim.** Before export, cut every frozen or silent head and tail on the timeline (Cut + right-click Delete, or edge drag), then **Auto Align Clips**. Leave no gaps.
7. **Export** High / FullHD 1080×1920 / mp4, then deliver the My Videos download link.

## Only stop for
A login page, a one-time Terms screen, or an out-of-credits screen. The user clicks it, says "done", and you continue where you stopped.

## References
- `references/videoexpress-ui-map.md`: every control, label, default and quirk
- `references/fast-pacing-and-trim.md`: hook formulas, verb bank, banned words and the trim procedure with pixel math
- `../../examples/`: complete storyboards (realistic, 3D, 2D) to imitate
