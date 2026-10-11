# heyvale-miniapp

Telegram Mini App for @heyvale_bot: a 3D talking avatar of Vale in a dim industrial set.
Static, client-only. No secrets live in this page.

## What it does
- three.js 0.180.0 + @pixiv/three-vrm 3.5.5 from jsDelivr through an import map (pinned versions)
- VRM avatar framed waist-up, as if she's standing in front of you. Idle breathing, sway, blinking every 2-6 s, eyes/head follow touch or cursor, relaxed arms
- Lip-sync on the VRM `aa/ih/ou/ee/oh` expressions:
  - real audio via `playAudio(urlOrBuffer)`: Web Audio AnalyserNode (loudness + rough band-energy vowel guess)
  - browser `speechSynthesis`: `onboundary` word events + a procedural mouth pattern (it can't be analysed)
  - if no TTS voice is available, a timed word schedule drives the mouth
- Voice chat: mic button uses SpeechRecognition where available; otherwise a text box. "Say hi" demos lip-sync.
- Brain: `getReply(text)` in `index.html` is a small local placeholder (TODO: real backend).

## 3D model credit / license
"VRM1_Constraint_Twist_Sample" (c) 2022 pixiv Inc., from the pixiv/three-vrm repository
(`packages/three-vrm/examples/models/`, tag v3.5.5).
License: VRM Public License 1.0 (https://vrm.dev/licenses/1.0/): redistribution allowed,
modification and redistribution of modifications allowed, credit not required.
The page tints the hair dirty-blonde and darkens the top at runtime. The original file isn't changed.

The model (10.8 MB) loads from jsDelivr, pinned to the v3.5.5 tag of pixiv/three-vrm, with
raw.githubusercontent.com as a fallback.
