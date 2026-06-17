# Self-host the tribute video in the repo

The hidden "Gaelle" easter egg plays a personal montage. We host it as a committed
`assets/gaelle.mp4` and play it inline, rather than embedding an unlisted
Vimeo/YouTube iframe.

**Why:** it keeps the site's single-file, zero-third-party-dependency character
(no external iframe, branding, or tracking), and the player styles cleanly inside
the overlay card. The trade-off we accepted: the video is a binary in git history
(effectively permanent) and must be kept compressed (~<30 MB), and — like anything
on a static site — the file is publicly reachable by URL, so "hidden" means
*undiscoverable by the trigger*, not access-controlled.

**Reconsider if** the clip needs to be long/large or genuinely private; an unlisted
embed would be the fallback.
