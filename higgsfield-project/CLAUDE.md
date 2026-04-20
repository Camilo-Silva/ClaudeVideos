# My Higgsfield Workflow

## Tools
- Image generation: Higgsfield NanoBanana 2
- Video generation: Higgsfield Seedance 2.0

## Default Image Settings
- Aspect ratio: 9:16
- Image count: 8
- Quality: 2K unlimited ON
- Extra free gens: OFF

## Video Generation Settings (Seedance 2.0)
- URL: higgsfield.ai/create/video/
- Model: Seedance 2.0 Fast
- Aspect ratio: 9:16
- Duration: 8s
- Resolution: 720p
- Reference image: OFF by default unless specified

## Prompt Bar Fix — Image Page
Use this JS snippet to clear the prompt bar before every prompt:
```js
const editor = document.querySelector('[id="hf:tour-image-prompt"] [contenteditable]')
  || document.querySelector('[contenteditable="true"]');
editor.innerHTML = '<p><br></p>';
editor.dispatchEvent(new Event('input', { bubbles: true }));
```

## Prompt Bar Fix — Video Page
Use this JS snippet when on the video generation page (different selector):
```js
const editor = document.querySelector('[id="hf:tour-video-prompt"] [contenteditable]')
  || document.querySelector('[contenteditable="true"]');
editor.innerHTML = '<p><br></p>';
editor.dispatchEvent(new Event('input', { bubbles: true }));
```

## Image Workflow
1. Navigate to higgsfield.ai/image/nano_banana_2
2. Confirm all image settings before generating
3. For each prompt:
   a. Clear prompt bar via JS (image page snippet)
   b. Take screenshot to verify bar is empty
   c. If not empty, clear again and re-verify
   d. Type prompt slowly
   e. Click Generate
   f. Clear bar via JS again immediately after clicking Generate
   g. Wait 7 seconds
   h. Repeat for next prompt
4. Save outputs to /images/YYYY-MM-DD/

## Video Workflow
1. Navigate to higgsfield.ai/create/video/
2. Confirm all video settings before generating
3. Always confirm model is set to Seedance 2.0 before generating
4. For each prompt:
   a. Clear prompt bar via JS (video page snippet)
   b. Take screenshot to verify bar is empty
   c. If not empty, clear again and re-verify
   d. Type prompt slowly
   e. Click Generate
   f. Clear bar via JS again immediately after clicking Generate
   g. Wait and poll every 15 seconds until the download button appears
   h. Click download and confirm the file saves
   i. Rename file using prompt keyword + index (e.g. beach-walk-01.mp4)
   j. Move file to /videos/YYYY-MM-DD/
   k. Repeat for next prompt
5. Do not start the next generation until the current video has fully downloaded

## Rules
- Always clear the prompt bar via JS before typing. Never skip this step.
- Always screenshot after clearing to confirm it's empty.
- Never skip settings confirmation.
- Go straight to generating, no prompt previews.
- Save all outputs to /images/YYYY-MM-DD/ or /videos/YYYY-MM-DD/
- Naming convention: [prompt-keyword]-[index].ext (e.g. beach-walk-01.mp4, char-01.png)
- Wait times for video: 60–180 seconds. Do not time out early.
- Use the IMAGE JS snippet on the image page and the VIDEO JS snippet on the video page. Never mix them.
