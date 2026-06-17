# assets/

Drop the tribute montage here as **`gaelle.mp4`**. Until it exists, the easter-egg
overlay shows a small placeholder note instead of a broken player.

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
  gaelle.mp4
```

Aim for **under ~30 MB** (the file lives in git history forever and is served by
Netlify). 720p–1080p is plenty. Then commit and push — no code changes needed.
