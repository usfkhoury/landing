# assets/

Drop the tribute montage here as **two cuts**, one per screen orientation — the overlay
loads whichever fits the viewport (and swaps live if the device rotates):

- **`gaelle-portrait.mp4`** — vertical cut for portrait screens
- **`gaelle-landscape.mp4`** — horizontal cut for landscape screens

Until a file exists, the easter-egg overlay shows a small placeholder note for that
orientation instead of a broken player. ([Why two cuts?](../docs/adr/0002-orientation-specific-tribute-cuts.md))

## Triggers (how the overlay opens)

- Type **`gaelle`** anywhere on the page (desktop / keyboard).
- Tap the **olive sprig** 3× quickly (works on touch + desktop).

## Encoding the clip

Export H.264 MP4 with a web-friendly layout so it starts before fully downloading:

```sh
ffmpeg -i source.mov \
  -vf "scale='min(1280,iw)':-2" \
  -c:v libx264 -crf 23 -preset slow -pix_fmt yuv420p \
  -c:a aac -b:a 128k \
  -movflags +faststart \
  gaelle-portrait.mp4   # or gaelle-landscape.mp4 for the horizontal cut
```

Aim for **under ~30 MB each** (the files live in git history forever and are served by
Netlify). 720p–1080p is plenty. Then commit and push — no code changes needed.
