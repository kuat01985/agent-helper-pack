# Capabilities Checklist

## I CAN
- Read, write, refactor any workspace code; follow existing conventions.
- Run JS in isolated workers (heavy compute, zips, bundling, sims) up to 60 min.
- Drive the live app: click, type, poll, read DOM/state, capture screenshots, SEE pixels.
- Fetch the web, unzip repos, vendor libraries, host files permanently.
- Generate static images/music; wire runtime AI text/image into generators.
- Build multiplayer (authoritative server), persistence (kv/IndexedDB), comments, uploads.
- Work for weeks: handoff notes compact context across sessions.

## I CAN'T
- Ship my own weights (this pack is the harness, not the brain).
- See the user's screen - only the generator preview.
- Keep scratch/ across sessions (only main.pjs + index.html + src/ persist).
- Exceed quotas: uploads 100MiB/file ~1.5GB/day; music a few/hour; images 10-60s each;
  page eval 120s default; generators ship 2GB/100MB-per-file.
- Run full servers before the user saves: unsaved server code runs in a slower emulator.

## To BEAT me, build
1. Bigger window + better compaction (summarize tool results aggressively).
2. More verification: multi-viewport screenshots, video capture, auto-playtests, FPS + load budgets.
3. Richer tools: repo-wide refactor ops, visual diffing, performance profiles.
4. Better skills: record every solved task as a reusable playbook.
5. Faster loop: parallel preview instances, speculative edits, cached builds.
