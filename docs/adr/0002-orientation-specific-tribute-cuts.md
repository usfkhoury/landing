# Ship two orientation-specific cuts of the tribute video

The hidden "Gaelle" tribute popup adapts to the viewport: a tall stacked card in
portrait, a wide two-pane card in landscape. Rather than letterbox a single clip into
both shapes, we ship **two cuts** — `assets/gaelle-portrait.mp4` and
`assets/gaelle-landscape.mp4` — and load whichever matches the screen orientation
(`matchMedia('(orientation: landscape)')`), swapping live if the orientation changes.

**Why:** a montage framed for one orientation looks bad in the other — a vertical phone
clip leaves large side bars on a laptop, and a 16:9 clip is tiny on a portrait phone.
Two purpose-cut edits fill each shape properly. Only the needed file is fetched, so the
bandwidth cost on any single view is unchanged.

The trade-off we accepted: the montage must be edited and encoded **twice**, and both
binaries live in git history (see [0001](0001-self-hosted-tribute-video.md) for the
self-hosting rationale and size guidance). Swapping cuts mid-view restarts playback,
since the edits differ and a shared timestamp is meaningless.

**Reconsider if** maintaining two edits becomes a burden or the clips converge in
framing — a single responsive clip with `object-fit: contain` would be the fallback.
