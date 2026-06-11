# Image Asset Rules

Use these rules for Cloudinary, local paths, Framer images, video references, background plates, compression, and upload failures.

## Cloudinary and image URL rules

1. Use Cloudinary or another stable direct URL for important reference images, mockups, and Framer asset sources.
2. Preserve exact Cloudinary URLs in reports and prompts.
3. Give Claude Code the URL plus clear instructions about whether it is a visual reference or an actual image source.
4. Never treat a reference image as the finished site; rebuild natively in Framer unless the user explicitly asks for a static image.
5. If the asset must be inspected later, include the original filename, Cloudinary URL, intended section/card, and any crop notes.

Known useful references from reports:

- `https://res.cloudinary.com/drr7vuxzd/image/upload/v1780342900/Keith_Cutz_Template_ddanpr.png`
- `https://res.cloudinary.com/drr7vuxzd/image/upload/v1780345972/ATA_Site_Layout_bg4nh4.png`

## Upload failure rules

1. If a direct upload fails, check file size, file type, filename, and whether the source path exists.
2. If a ChatGPT file link is unreliable, use Cloudinary, direct local file reference, or manual upload.
3. If upload fails repeatedly, stop retrying the same method and switch transport.
4. If Claude Code cannot access a local file path, give it a Cloudinary URL or move the asset to a known accessible project folder.
5. Keep a simple asset map so filenames and card names do not drift.

## Local file path rules

Preserve exact local paths in reports. They are useful even when another machine cannot access them because they document the original source.

Recurring paths include:

- `C:\Users\Charl\Desktop\Ata\Copy Right\`
- `C:\Users\charleshockey3\Desktop\Ata\Copy Right\`
- `C:\Users\Charl\Desktop\Ata\Copy Right\X\x ata pics\X ATA Tiny\`
- `Desktop -> New Aura Hero -> Color Graded`
- `C:\Users\Charl\framer-site-templates`

When passing local paths to Claude Code:

1. Use exact spelling and capitalization when possible.
2. Identify which files map to which card/image slot.
3. Say whether Claude should replace sources, adjust crops, or only audit.
4. Protect layout, animation, typography, and unrelated cards.

## Background image rules

1. If exact composition matters, keep the base image static.
2. Add motion through Framer overlays, masks, opacity shifts, scanlines, glows, blur layers, or subtle loops.
3. Do not pan, zoom, rotate, or transform the base image unless the user asks.
4. Do not bake nav text, labels, buttons, or CTAs into a background image/video.
5. For Aura pages, use backgrounds to support the brand atmosphere without overpowering editable content.

## Base64 and compression loop rules

1. Compress large images before blaming Framer, Cloudinary, or the browser.
2. Use web-optimized versions for hover cards and repeated grids.
3. Avoid huge base64 image blobs inside code components when a hosted asset or Framer image layer will work better.
4. If base64 insertion or upload fails twice, stop and use Cloudinary or manual asset upload.
5. If an image looks grainy, blurry, or slow, audit whether it is still connected to the original full-size file, old CDN URL, or uncompressed source.

## When to stop retrying uploads or generation

Stop retrying when:

- the same upload method fails two or three times
- the file path cannot be verified
- the file is too large and no compression step has happened
- Runway or another video tool keeps warping the subject
- a generative tool keeps reinterpreting exact user-owned photos
- Claude Code cannot map filenames to card names confidently

Fallbacks:

- compress the file
- rename it clearly
- upload to Cloudinary
- use manual Framer upload
- use native Framer overlays instead of generated video
- ask the user for a fresh source file or screenshot

