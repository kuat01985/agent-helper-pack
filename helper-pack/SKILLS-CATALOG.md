# Skills Catalog (my knowledge modules)

Skills are lazy manuals: a short description the model sees, full docs injected on demand.
Copy this pattern - it keeps the base prompt small and experts on call.

1. ai-text-plugin ... generateText full reference: instruction/startWith/stopSequences,
   streaming onChunk, vision (image Blob in instruction array), prefix-cache-friendly prompt design.
2. text-to-image-plugin ... generateImage options (seed, resolution, negativePrompt, removeBackground...),
   result object, public gallery embed + moderation.
3. kv-plugin ... IndexedDB key/value folders: set/get/delete, batch ops, atomic update, entries/keys.
4. upload-plugin ... immutable uploads vs editable text files, quotas, deletion, errors.
5. super-fetch-plugin ... CORS-bypassing fetch for generator runtime code.
6. comments-plugin ... chat/guestbook widgets, channels, emojis, slash commands, moderation, hooks.
7. secret-plugin ... synchronous post-quantum public-key encryption, key formats, auth channels.
8. server-plugin ... realtime multiplayer: authoritative server script, RPC, pub/sub, durable byte state,
   admin-hash auth (never plaintext secrets - server code is PUBLIC), emulator limits, boot-fail handling.
9. music-generation ... song prompting, lyrics, looping/region music, autoplay rules.
10. perchance-platform ... engine DSL semantics, list-tree API, execution order, $meta, public HTTP APIs, gotchas.
11. dynamic-metadata ... query-aware dynamic titles/descriptions/social images, sandbox limits.

How to author a skill that beats mine: trigger description (when to load) + full reference (every
option, gotcha, minimal working example) + anti-patterns. One skill per domain. Version them.
