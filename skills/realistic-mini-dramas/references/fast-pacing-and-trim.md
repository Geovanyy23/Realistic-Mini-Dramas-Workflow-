# Fast pacing and dead-air trimming

Short-form video lives or dies in the first second, and every frozen frame loses viewers. This guide is the detail behind SYSTEM_PROMPT.md Sections 2, 6 and 7c.

## 1. Hook formulas for S01 (pick one)
1. **Shock line:** "He's not dead. He's downstairs."
2. **Threat:** "Open the door or she dies."
3. **Reveal mid-action:** a hand rips off a mask. No line needed.
4. **Impossible question:** "Why is my name on that grave?"
5. **Caught in the act:** "Put the knife down. Slowly." (the line, not the motion)
6. **Countdown:** "We have ten seconds. Run."
7. **Betrayal:** "You told them where I was?"
8. **Wrong-place reaction:** an extreme close-up of eyes going wide, then a snap zoom.

Never open on a landscape, a character walking in, a title card or a calm conversation.

## 2. Verb bank (use these)
slams · grabs · whirls · snaps · lunges · shoves · rips · hurls · ducks · bolts · freezes · smashes · yanks · spins · drops · flinches · stumbles · kicks · catches · seizes · jerks · bursts · charges · recoils

## 3. Banned words (they create dead air)
slowly · gradually · pauses · a beat · a long beat · lingers · takes a moment · contemplates · gazes · drifts · settles · stares for a while · slow motion · fade in · fade out · establishing shot · calmly walks in

## 4. Rhythm patterns
- Default generation length: **4 s** with no dialogue, **5 s** with dialogue.
- Trimmed target: **2.5–3.5 s** per shot. Hook and payoff may run to 4 s.
- Vary framing so cuts feel energetic: ECU → MCU → WS → OTS → CU → ECU…
- Put a no-dialogue action shot after every one or two dialogue shots.
- Twist at about 70% of the runtime. The final shot ends on the punchline or cliffhanger.

## 5. Dialogue rules
- One speaker per shot. Name them and say "only [Name] speaks".
- 8 words max (about 2.5 s spoken fast).
- The line starts "immediately, within the first half-second".
- Write the line in double quotes, exactly as it should be spoken.
- Set a fast tone: sharp, clipped, breathless, snapping, urgent.

## 6. Dead-air trim procedure (VideoExpress timeline)

### What counts as dead air
- frozen or near-still frames at the start of a clip
- the "hold" after the action lands or after the last word
- more than 0.25 s of silence before the first word or after the last word
- camera settle, slow drift, morphing or a fade at either end

### Keep
- about 0.1 s before the first word and about 0.15 s after the last word
- action shots: cut in as the motion starts, cut out on the impact or reaction

### Set the scale
Click **Zoom in** 3 times. Now **40 px = 1 s**, **4 px = 0.1 s**, and each **Step forward/backward** press is about 0.1 s.

### Method A: Cut + Delete (most reliable)
1. Click the ruler at the clip's start. Step forward and watch the preview to find the first good frame.
2. Click **Cut** (scissors). Right-click the left piece → **Delete**.
3. Step forward to the last good frame. Click **Cut**. Right-click the right piece → **Delete**.
4. Click **Auto Align Clips** (`+|+`). Re-read the timeline because positions shift.

### Method B: Edge drag
Drag the right edge left by (seconds × 40) px, drag the left edge right by (seconds × 40) px, then click **Auto Align Clips**. Re-read the clip width after each drag.

### Fallback (can't judge media)
| Clip | Remove start | Remove end | Result |
|---|---|---|---|
| 4 s, no dialogue | 0.5 s = 20 px | 1.0 s = 40 px | 2.5 s |
| 5 s, dialogue | 0.3 s = 12 px | 0.6 s = 24 px | 4.1 s |
Never go below 1.5 s (60 px).

### Final pass
Click **Auto Align Clips**, play from 0:00, and confirm there are no black frames, no gaps and no frozen holds.

## 7. Worked example: a 45 s target with 15 shots

| Shot | Type | Generated | Head cut | Tail cut | Final |
|---|---|---|---|---|---|
| S01 | hook, dialogue | 5.0 | 0.2 | 0.8 | 4.0 |
| S02 | action | 4.0 | 0.5 | 0.9 | 2.6 |
| S03 | dialogue | 5.0 | 0.3 | 1.4 | 3.3 |
| S04 | action | 4.0 | 0.4 | 0.8 | 2.8 |
| S05 | dialogue | 5.0 | 0.3 | 1.5 | 3.2 |
| S06 | dialogue | 5.0 | 0.2 | 1.6 | 3.2 |
| S07 | action | 4.0 | 0.6 | 0.9 | 2.5 |
| S08 | dialogue | 5.0 | 0.3 | 1.5 | 3.2 |
| S09 | action | 4.0 | 0.5 | 0.7 | 2.8 |
| S10 | dialogue | 5.0 | 0.3 | 1.5 | 3.2 |
| S11 | twist, action | 4.0 | 0.3 | 0.7 | 3.0 |
| S12 | dialogue | 5.0 | 0.2 | 1.6 | 3.2 |
| S13 | action | 4.0 | 0.5 | 0.8 | 2.7 |
| S14 | dialogue | 5.0 | 0.3 | 1.5 | 3.2 |
| S15 | payoff, dialogue | 5.0 | 0.2 | 0.8 | 4.0 |
| **Total** | | **69.0** | | | **46.9** |

About a third of the generated footage is dead air. Cutting it is what makes the drama feel fast.
