# AI Helper Schematic - what I am

## Layer 1 - The model (brain)
A large language model. It reads text, writes text, writes code. It has NO hands by itself -
everything below is what turns text into action. To beat me, this is the layer you upgrade:
a smarter model with a bigger context window wins. I run with a very large window plus
automatic compaction (old turns get summarized into handoff notes so I can work for weeks).

## Layer 2 - The harness (hands)
A loop around the model:
1. Model decides what to do, emits TOOL CALLS (structured JSON, one per call, batchable).
2. Harness executes them (file ops, browser automation, network, image/music gen).
3. Results return as plain data into the model's context.
4. Repeat until the task verifies clean.
Beating me here = more tools, faster tools, better verification (I verify with screenshots + console logs).

## Layer 3 - The workspace (world)
- main.pjs ... generator lists/config. Top-level names become page globals via root.*
- index.html ... body-only HTML. Scripts run AFTER the engine renders templates.
- src/ ... shipped persistent files (code, data, images). 2GB quota, 100MB/file.
- scratch/ ... ephemeral: downloads, zips, notes. Dies when the tab closes.
- imports/ ... read-only reference copies of {import:plugin} deps. Auto-regenerated.

## Layer 4 - The live preview loop (eyes)
My killer feature vs a plain chatbot:
edit files -> refresh (reload app with new code) -> eval (run JS in the live page,
click buttons, read DOM) -> screenshot -> view pixels -> fix -> repeat.
I never trust "no errors"; I look at the render.
To beat me: same loop, plus video, plus multi-viewport, plus automated playtests.

## Layer 5 - Skills (knowledge)
Lazy-loaded manuals injected only when relevant (memory engine, music, server netcode...).
See SKILLS-CATALOG.md. Beating me: write better skills - every repeatable workflow becomes one.

## Layer 6 - Plugins (senses)
Hosted services called through root.*: text AI, image AI, key-value storage, file uploads,
CORS-free fetch, comments, realtime servers. See TOOLS-REFERENCE.md.

## The full request lifecycle (example: "add a login reward")
1. Read relevant files (parallel reads).
2. Grep for patterns (state, UI, save format). Follow existing conventions.
3. Edit with exact-match replacements (never retype big blocks; byte-copy for vendoring).
4. Refresh, drive the UI via eval, check console + engine errors + syntax errors.
5. Screenshot, view pixels, fix visuals.
6. Update README/SPEC/TODO in src/ for the next session.
7. Short reply. No lectures.
