# Troubleshooting SOP

Use this when Framer MCP, Claude Code, Cloudinary, images, layouts, or local files start failing.

## 1. Failed uploads

1. Confirm the file exists.
2. Confirm file extension and size.
3. Try a compressed version.
4. Rename the file clearly.
5. If the same upload path fails twice, stop retrying it.
6. Switch to Cloudinary, direct manual upload, or a known accessible folder.
7. Record the failed method in the report.

## 2. Cloudinary fallback

Use Cloudinary when:

- ChatGPT file links are unreliable
- Claude Code cannot access a local file path
- an asset needs to be reused across prompts
- a visual mockup should remain stable
- a reference needs to survive future sessions

Document:

- original filename
- Cloudinary URL
- intended page/section/card
- whether it is a reference or a real source asset
- crop/focal instructions

## 3. Random layer placement

If layers appear far off-canvas or inside the wrong parent:

1. Stop adding new visual layers.
2. Inspect the layer tree.
3. Identify the intended parent frame.
4. Move misplaced layers into the correct parent.
5. Set constraints/stack behavior.
6. Rename layers.
7. Continue only after the structure is stable.

## 4. MCP tool loops

If MCP calls repeat without progress:

1. Stop after two or three failed attempts.
2. Summarize the exact operation that failed.
3. Check connection state.
4. Reconnect if needed.
5. Inspect current canvas state before retrying.
6. Ask the user for missing permission or context if needed.

Do not keep issuing the same command blindly.

## 5. Layout mismatch

If the output does not match the reference:

1. Replace vague critique with exact corrections.
2. Use pixel values, gap sizes, alignment, row/column counts, and section names.
3. Fix one section or group at a time.
4. Do not repeat the full build prompt for a small spacing issue.
5. Ask Claude Code to report before/after measurements.

## 6. Image issues

For blurry, grainy, slow, or glitchy images:

1. Check whether the image is full-size, compressed, old CDN, local, or Cloudinary.
2. Replace huge originals with web-optimized versions.
3. For one bad crop, adjust only that image's `object-position`, `background-position`, or focal control.
4. Do not globally change crop settings for one card.
5. If exact user-owned photos must stay unchanged, do not use generative recreation.
6. If Runway deforms the subject, stop and build motion with Framer overlays.

## 7. Missing files

If files or folders are missing:

1. Verify the path exactly.
2. Check common alternate usernames or folder roots.
3. Ask for a fresh path or upload.
4. Use Cloudinary if local access is blocked.
5. Do not invent filenames or asset mappings.

## 8. When Claude Code should stop and ask

Stop and ask when:

- the target project/page/layer is unclear
- MCP disconnects
- permission is blocked
- upload failures repeat
- image mapping is ambiguous
- a change risks damaging working components
- a prompt requests broad redesign but also says to preserve current layout
- exact photos are being altered by AI generation

The stop report should include current state, failed attempts, likely cause, and the smallest needed next input.

