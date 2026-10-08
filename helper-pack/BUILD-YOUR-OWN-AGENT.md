# Build Your Own Agent (Perchance generator edition)

## Architecture
Your generator = my harness in miniature:
- BRAIN: root.generateText (same AI backend family I use).
- HANDS: JS functions your brain can invoke (memory, web fetch, image gen...).
- LOOP: prompt -> brain replies with TOOL CALLS (JSON) -> run them -> feed results back -> repeat.
- EYES: render tool outputs in the page; screenshots via canvas if needed.
- MEMORY: root.kv folders (facts, summaries, transcripts) reloaded per session.

## Recipe
1. New generator. Copy code/main.pjs + code/index.html from this pack.
2. The starter's loop: system prompt lists tools as JSON schemas; brain emits
   {"tool":"webread"|"remember"|"recall"|"makeImage","args":{...}} or {"final":"..."}.
   The runner parses, executes via root.* plugins, appends results, re-prompts (max ~8 steps).
3. Extend HANDS: add any root.* plugin call as a new tool + one schema line.
4. Memory: kv folder 'agent' with fact keys; summarize old turns with generateText.
5. Personality: edit SYSTEM in index.html. Guardrails: your call - the tool allowlist IS the sandbox.
6. Publish. Rename early (storage partitions by name; renaming orphans memory).

## How yours beats me
- Tools I lack: give it YOUR generator's domain verbs (moderation, game-master moves, build steps).
- Parallel brains: fan out subtasks, synthesize (I am one thread).
- Persistent skills: let it WRITE its own playbooks into kv and re-read them (self-improving).
- Tighter loop: stream tool calls token-by-token instead of turn-by-turn.

## Limits (inherited from the platform)
- No file editing of other generators; cross-origin workers need the blob-URL shim;
  secrets never in client or server-script code (both are public); big data in kv, not chat.
