# 🔐 MODULE 3 — ONE CONTROL CARD (PRIVATE)

**Audience title:** AI Can Help Me Create — From Idea to Finished Video  
**Project:** SmartLife, fictional everyday planner  
**Target film:** Two 8-second video scenes + one 4-second closing card = 20 seconds  
**Suggested delivery:** 25–40 minutes depending on audience and generation latency.

## BEFORE PARTICIPANTS ARRIVE

Open browser tabs in this order:

1. [Google Flow](https://labs.google/fx/tools/flow) — Image and Video creation
2. [Google AI Studio](https://aistudio.google.com/) — Generate Speech / TTS
3. [Canva Video Editor](https://www.canva.com/video-editor/) — assemble MP4

Use a new empty Flow project to show the **from-scratch** process. Keep two generated example images and the local preview MP4 available only as fallbacks. Confirm credits and generation settings on your actual account; do not assume every model or feature is free. Use 16:9 and the shortest appropriate video duration, preferably 8 seconds for each moving clip.

**Client request (read aloud):** “Create a short promotional film for our fictional planning product, SmartLife. Show the everyday problem and how organised planning can help. Finish with the line ‘Plan clearer. Live brighter.’”

## EXACT SEQUENCE — WHAT TO OPEN AND WHAT TO PASTE

### 1 — Establish the story

Explain: **Problem → Better way → Brand message.**

Scene 1: Overloaded day. Scene 2: More organised day. Closing card: SmartLife.

### 2 — Flow: Image mode → Generate Scene 1 image

Copy:

```text
Create a cinematic, photorealistic 16:9 advertising still image for a
FICTIONAL productivity product called SmartLife. A young South Asian adult
woman in a teal shirt is at a modern home-office desk, looking slightly
overwhelmed by an untidy collection of everyday tasks. Show a laptop,
planner, sticky notes, a mug and warm sunset light through a window.
Natural credible face and hands, tasteful warm-and-teal colour palette,
shallow depth of field, professional commercial photography. Leave room
for later titles. No visible logos, readable words, watermarks or captions.
```

Wait for image; inspect the result; use it for Scene 1. If generation is delayed use `Scene_01_Generated_Image.jpg` and clearly say it is a prepared reference rather than newly generated.

### 3 — Flow: Generate Scene 2 image using Scene 1 as character reference

Attach/select the Scene 1 image as reference if supported in the current Flow image workflow. Copy:

```text
Using the attached first-scene image as a character and visual reference,
create a matching photorealistic 16:9 advertising image. Show the same
young woman in the same teal shirt and home office, now looking relaxed
and confident while using a clean, attractive productivity planner on
her laptop. The interface should suggest organised tasks and a calendar
using simple abstract shapes. Preserve the character's face, outfit and
warm sunset atmosphere. Cinematic quality. No readable text, branding,
watermarks or subtitles.
```

**What to teach:** A reference image improves continuity but does not guarantee perfect identity.

### 4 — Flow: Animate Scene 1 image (Image → Video / Animate)

Select Scene 1 and copy:

```text
Animate this exact supplied image into a realistic cinematic shot.
The woman glances between the planner and laptop and takes a small,
thoughtful breath. Add a very slow camera push-in; gentle natural
motion only. Preserve the person's face, teal clothing, desk objects
and background. Subtle room ambience, no speech. No scene changes,
unwanted text, titles, logos or extra people.
```

Select Video / Animate, appropriate model, 16:9 and available duration. Download the approved MP4 as `CLIP_01_Problem.mp4`.

### 5 — Flow: Animate Scene 2 image

Select Scene 2 and copy:

```text
Animate this exact supplied reference frame into a realistic commercial
shot. The same woman smiles naturally and briefly interacts with the
planning dashboard on the laptop. Keep the camera steady with one
subtle push-in, preserving identity, room and layout. Quiet positive
room ambience, no speech, no subtitles or readable UI text. Avoid
morphing hands, laptop or background.
```

Download `CLIP_02_Solution.mp4`. If a clip is longer than needed, trim it in Canva. For any Flow-generated audio, mute it in Canva if it clashes with the music or narration.

### 6 — Google AI Studio: Generate a single consistent AI narration

Use an available single-speaker speech/TTS workflow. Paste this as the **verbatim script**:

```text
Too many tasks, too little time? Meet SmartLife, your personal planning
companion. Organise priorities, track progress, and make room for what
matters. SmartLife. Plan clearer. Live brighter.
```

Voice style (separate instruction/control if available):

```text
One friendly, confident, warm professional narrator. Natural conversational
English, relaxed optimism, clear pronunciation, medium-fast pace. Read
only the script. Do not insert extra words or sound effects.
```

Select a voice; generate; listen; download WAV or MP3. If voice is too long, shorten script before regenerating. Never imitate a real person's voice without permission. If the TTS tool asks for billing or is unavailable, use any licensed recording or Canva's accessible narration option; explain the substitution.

### 7 — Canva: Combine video + narration + background music

1. Create a Video (16:9 landscape) design.
2. Upload `CLIP_01_Problem.mp4` and `CLIP_02_Solution.mp4`.
3. Place each on the timeline and trim toward **8 seconds each**.
4. Add a final **4-second** clean background/closing card with **SmartLife — Plan clearer. Live brighter.**
5. Upload AI-generated narration and place it on the audio track. Align the opening sentence with Scene 1, the benefit statement with Scene 2 and the closing slogan with the end card.
6. Open **Audio** and choose an appropriately licensed **free instrumental** (gentle uplifting technology/corporate); avoid Pro-marked or restricted tracks. Alternatively, upload a track you have rights to use.
7. Set music lower than narration; avoid overlapping conflicting clip audio; fade the music at the end.
8. Play from beginning to end; correct timing, captions, rights, volume and spelling; export **MP4** and check audio playback.

### 8 — The take-home insight

“Two short generated video clips, one AI voice and one music track became a finished commercial concept. Add more carefully planned scenes and edit them consistently to create a longer film.”

## BACKUP (IF GENERATION STALLS)

In this ZIP, `Scene_01_Generated_Image.jpg` and `Scene_02_Generated_Image.jpg` are pre-created reference images. `Illustrative_20s_Promo_WITH_AUDIO.mp4` is a **locally assembled illustrated preview with basic synthetic speech and original instrumental music**, NOT a Google Flow-rendered cinematic result and NOT an AI Studio voice. It illustrates the intended pacing and components. Use it openly as a reference or fallback, never as proof that the full Flow/Canva pipeline ran.

## DELIVERY PRIORITIES

Essential: prompt one image, animate one clip, generate AI narration, show the Canva timeline and play/export a complete video. If production latency is high, use prepared second image and clip; never skip narration/music/editing explanation to wait for processing. All session timing, fallback details and instructions stay private. The audience slides contain none of these.

## CLIENT BRIEF SAFETY

SmartLife is fictional. Never assert real product functionality, customer testimonials, security certifications or measurable results. Use consented fictional people and licensed music; check current terms, geographic eligibility and credits.

## VERIFIED HELP PAGES

- Flow: https://support.google.com/flow/answer/16353334
- AI Studio Speech: https://ai.google.dev/gemini-api/docs/speech-generation
- Canva Video: https://www.canva.com/help/creating-and-editing-videos/
- Canva Audio: https://www.canva.com/help/stock-music/
