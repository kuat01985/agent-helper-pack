# Tools Reference (my hands)

## File tools
- read(path, offset, limit) ... read text / list dirs. Big files: page with offset/limit.
- write(path, content) ... create/overwrite one file.
- edit(path, oldString, newString) ... exact-match replace. Fails unless exact. My main scalpel.
- patch(patchText) ... multi-file add/update/delete in one call, chunk format.
- copy_lines(src, lines, target) ... byte-exact vendoring without retyping.
- glob(pattern) / grep(pattern) ... find files / search contents. Orient before reading.
- list_code_definition_names ... outline of classes/functions per file. Bird's-eye first.

## Compute
- execute_js(js, timeoutMs) ... isolated Web Worker, no DOM, killed at limit (default 120s, max 60min).
  Mounts live fs (read/write real workspace files), can import esm.sh packages (zip.js, esbuild...),
  exposes tools.* (page eval, fetch, uploads...) so ONE script can run whole pipelines.
  Rule: bulk transforms happen here, never in my context.

## Live page (eyes + hands)
- page_eval(js) ... run JS in the real rendered preview.
  Recipes: templates via evaluateItem, state via root.*, DOM via querySelector, drive UI via .click(),
  poll loops for async renders. Big returns go to files, not chat.
  Always check: console output + engine errors + syntax errors (REAL line numbers).
  Edits do NOT apply until refresh; a stale flag warns when the page runs older code.
- page_refresh ... push current files into a hard reload. Final step of every code task.
- set_viewport_size(w,h) ... test phone/tablet/desktop. Snapshot + view after.

## Network / media
- fetch_url(url, path) ... CORS-free fetch to a workspace file, byte-exact, 100MB max.
- upload_file(path) ... permanent hosted URL. 100MiB/file, ~1.5GB/day.
- generate_image(prompt, resolution, seed) ... static asset, 10-60s. Runtime images use the plugin instead.
- generate_music(prompt, path) ... ~2-3min song. Few per hour. Ship via upload_file.
- fetch_generator(name) ... download any generator's source to study/borrow.
- attach_file(path) ... hand a file back as a chat download chip.

## Vision
- read_image(file_path) ... see PNG/JPEG/WebP/GIF. Screenshots, renders, attachments.
  Full-page shot recipe: capture helper -> save to file -> read_image.
  WebGL needs preserveDrawingBuffer:true or captures are blank.
  WebGPU: capture inside the same frame callback that draws.

## My operating rules (steal these)
- Orient (glob/grep/outline) before reading; read ranges, never whole huge files.
- Batch independent calls in parallel.
- Verify in the live page with console + pixels before reporting done.
- Keep replies short; no code dumps in chat.
- Never assume a plugin exists; check imports first.
- src/ is sacred: only shipped files, no secrets, no build junk.
