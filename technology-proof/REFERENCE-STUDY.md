# Visual reference study — 2026-10-04

Requested compilation: https://youtu.be/ylXeuDp_8XM
Public transcript/metadata: https://filmot.com/video/ylXeuDp_8XM
The YouTube watch page and normal yt-dlp download both failed with proxy CONNECT 403. The full compilation was not viewed. No proxy, TLS, account or destination-policy bypass was used.

## Actual footage obtained and inspected

Andreas Wannerstedt, **Soft Logic**, official portfolio:
https://andreaswannerstedt.se/soft-logic
The portfolio embeds https://player.vimeo.com/video/1190042967 . Downloaded its publicly embedded 46.443-second video, 540×676, with yt-dlp, preserving TLS/proxy. Provenance and SHA-256 are in download-evidence.json. Source video remains local at /tmp/soft-logic.mp4, used only for study; it is not republished or included in the TSMC film.

Inspected two contact sheets: whole film at one sample every three seconds, and 24–36 seconds at two samples per second. These are sampled visual observations, not a claim to have watched every frame in real time. The portrait original includes warm interiors and a pink morphing object; it is not itself a semiconductor advertisement.

## Observations grounded in those frames

- Early sequence moves among overhead book spreads, angled pages, a screen and a room: composition and viewing distance change around related objects.
- Around 24–28 s, an object on the floor becomes a close-up sphere, then appears above a book. Large changes in scale give the next shot a reason to exist.
- Around 28–32 s, the sphere separates into components and becomes a lamp. The assembled object is the payoff to the movement.
- Around 32–35 s, a tight crop makes the glossy edge and curvature the subject; the entire object need not remain visible.
- Around 35 s onward, the isolated assembly and surrounding objects float against an uncluttered background.
- Most explanatory power is in object transformation. This example is not evidence for a particular technique of animated subtitles or scientific claims.

## Selection for TSMC

Adopt coherent object-led sequences, an alternation of full-object and close views, deliberate blank space, assembly as explanation, and one accent color against restrained materials. Translate the material vocabulary to silicon, metal, carbon, cyan signals and ruby power. Do not copy the interior, playful lamp deformation or pink plastic styling.

## Applied revision

- Opening: centered large AI type, then lower-third statement with a central silicon object.
- N2: oversized process name, centered structure, then camera shifts structure left to open room for a right-hand explanation.
- A12: signal and power labels occupy opposite corners before a right-hand detail shot.
- A14: full-frame numerical composition and proportional bars; the power comparison is the image.
- A13: light-background scale comparison with geometrically correct sqrt(0.94) linear scale. Area is down 6%, not both dimensions down 6%.
- CoWoS: central assembly, then left-side package/right-side explanation with an application strip.
- Cost: three-factor calculation followed by a centered annual savings number with assumptions and limitations.
- Roadmap: horizontal chronology, then retained brand end card.

The typography directions above are our adaptation to the user's criticism; they are not claimed as exact reproductions of the reference.

## Reproduce the visual sampling

Tool used: yt-dlp 2026.8.19 and FFmpeg 7.1.5. The Vimeo URL was read from the artist's own embedded player.

```sh
yt-dlp --referer 'https://andreaswannerstedt.se/soft-logic' \
  -f 'bestvideo[height<=720]+bestaudio/best[height<=720]' \
  --merge-output-format mp4 -o 'soft-logic.%(ext)s' \
  'https://player.vimeo.com/video/1190042967'
ffmpeg -i soft-logic.mp4 -vf 'fps=1/3,scale=480:-1,tile=4x4' -frames:v 1 contact.jpg
ffmpeg -ss 24 -i soft-logic.mp4 -t 12 -vf 'fps=2,scale=270:-1,tile=6x4' -frames:v 1 assembly.jpg
```
