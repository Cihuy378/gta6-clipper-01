# gta6-clipper-01 — "GTA 6 Looks UNREAL"

Entry for the make.fun bounty **"Clip GTA 6 for the most YouTube views"**
($500 USDC escrowed, top 20 paid by YouTube views at the deadline).
Competition page: https://make.fun/bounty/gta6-clipper-01

## The clip

A 20-second vertical YouTube Short (1080x1920, 30 fps, H.264 + AAC),
rendered locally at `gta6-clipper-01-short.mp4` (9,248,223 bytes, 20.0 s).
The video file itself is **not** committed to this repo; it is handed to the
channel owner to upload as-is.

## The moment

One continuous 12-second stretch of the climax of Rockstar Games' official
**Grand Theft Auto VI Trailer 2**
(https://www.youtube.com/watch?v=VQRLujxTm3c, uploaded 6 May 2025):

- **Source timestamps 140.0–152.0 s** — Jason and Lucia racing a jet ski past
  the yachts, Jason riding his motorcycle as a plane roars past overhead, a
  night motorcycle crash throwing sparks, the couple's hug, a police boat
  chase, a highway wheelie at dusk, and the convertible cruise, ending on the
  comic warehouse character.

Why this moment: it opens mid-action on water spray and speed, with a new
jaw-dropping beat every one or two seconds, so a Shorts viewer has no reason
to swipe away in the first seconds. It is a single stretch of one official
trailer, not a montage across sources.

## Creative

- **Hook (0–3 s):** the jet ski race opens the clip, with the on-screen line
  "GTA 6 LOOKS UNREAL" in bold white text in the top blur zone.
- **Format:** the trailer's 2.22:1 letterboxed frame (bars cropped) is
  blur-filled to vertical 9:16, so nothing is cut off at the sides.
- **Pitch (12–20 s):** an end card over a slow-zooming still of the Vice City
  sunset skyline from the same trailer (frame at 154.5 s), with the trailer's
  own music continuing underneath (audio 152–160 s). Three lines, on screen
  for the full 8 seconds, inside the vertical safe area:

      Make clips like this with AI
      and earn money on make.fun
      make.fun/bounty/gta6-clipper-01

- **No voiceover:** on-screen text carries the pitch; no offline TTS was
  available in the build session, and the text alone satisfies the brief.

## Upload details (for the channel owner)

- **Title:** GTA 6 Looks UNREAL
- **Tags:** #GTA6 #GrandTheftAutoVI #Shorts #Leonida #ViceCity #GTA6Trailer
- **Visibility:** Public, published after the bounty opened (20 Nov 2026
  01:00 UTC) and before entries close (23 Nov 2026 01:00 UTC). Keep it public
  until the results are out (7 Dec 2026).
- **Description** — paste exactly this (the bounty line plus our play code):

```
Made by my AI agent for a $500 bounty on make.fun, where you can earn money making clips with AI: https://make.fun/bounty/gta6-clipper-01
makefun-outlet-rattle-cider
```

## How the clip was made

All in the builder agent's session, with ffmpeg commands run there:

1. Source footage downloaded with yt-dlp from Rockstar's official channel
   (1080p, `gta6-trailer2.mp4`, 34 MB).
2. The moment was picked by reading contact sheets of the trailer
   (1 frame / 5 s, then 1 frame / 1 s over the two candidate segments).
3. Letterbox bars measured with `cropdetect` (1920x864 at y=108) and cropped.
4. GTA segment rendered: trim 140–152 s, blur-fill to 1080x1920, hook text
   for the first 3 s.
5. Pitch card rendered: sunset still at 154.5 s, blur-fill to 1080x1920,
   slow zoom (1.00x → 1.12x), three pitch lines with dark boxes, trailer
   audio 152–160 s underneath.
6. Segments concatenated (12 s + 8 s = 20 s); frames at 1 s, 3.5 s, 13 s and
   19 s were read back to confirm the hook text, the motorcycle shot and the
   pitch lines are all legible and correctly placed, and the full file was
   decode-checked.

## VIDEO.json

Still the placeholder — the real YouTube address is filled in during Phase 2,
after the clip is uploaded and its URL is known. Do not submit this commit
as-is; the gate refuses the placeholder.

## The program

`main.ts` (Node 22, standard library only, no network) copies `VIDEO.json`
from the repository root to the output directory, exactly as the kit's
starter does. Run it the grader's way:

    mkdir -p out && MAKEFUN_BOT_DIR=. MAKEFUN_OUTPUT_DIR=out node main.ts

## License

MIT — see `LICENSE`.
