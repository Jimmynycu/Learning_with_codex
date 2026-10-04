# TSMC: three native motion pipelines

Three original 16-second, 1920×1080, 30 fps creative studies. This is independent work, not an official TSMC advertisement. Wafer and package graphics are conceptual illustrations, not manufacturing specifications.

## Reproduce

Node 24, npm, Chromium, FFmpeg and Python Playwright are used in this environment. Run `bash scripts/install.sh`. Exact dependency versions are pinned in package-lock.json. No MCP, account or paid license was added.

- **Remotion 4.0.532:** React/SVG Composition, frame interpolation and springs; native Audio. Source: remotion/main.tsx. Render: `npx remotion render remotion/main.tsx TSMC output/tsmc-remotion.mp4 --browser-executable=/usr/bin/chromium --concurrency=2 --codec=h264`.
- **HyperFrames 0.8.119:** HTML/CSS artwork and registered, seekable GSAP timeline; native timed audio. Source: hyperframes/index.html. Render: `HYPERFRAMES_BROWSER_PATH=/usr/bin/chromium npx hyperframes render hyperframes --fps 30 --output output/tsmc-hyperframes.mp4 --no-browser-gpu --workers 1`.
- **Diffusion Studio Core 4.0.3:** native Composition, Layers, TextClip, RectangleClip, EllipseClip, AudioClip and Encoder. Source: diffusion/main.ts. Start `npx vite --host 127.0.0.1`, then `python scripts/render-diffusion.py`. Browser WebCodecs outputs AVC and Opus. For compatibility, FFmpeg copies the native video unchanged and converts only the audio to AAC. The free license watermark is retained. This is the installed Core SDK, not the hosted Studio account/UI.

`evidence/` preserves successful native rendering logs and ffprobe results. Each main output has 480 video frames. The first diffusion visual review exposed its percentage-based opacity convention; correcting 1 to 100 restored the text and shape visibility before publication.

## What was learned and applied

From the tutorial's public transcript: define the visual direction before rendering, divide the story into shots, keep animation deterministic, synchronize picture and audio to a common beat, and inspect actual output frames. Original YouTube visuals were not directly played; transcript sources are recorded in ../motion-study/LEARNING.md.

All three versions use four 4-second scenes and an original 120 BPM soundtrack, with cuts on eight-beat phrase boundaries. Remotion demonstrates procedural wafer geometry and perspective layers; HyperFrames uses kinetic typography and a GSAP timeline; Diffusion Studio uses native visual clips and keyframes. They are separately authored and rendered, not three wrappers around a pre-rendered video.

## Sources

- https://www.tsmc.com/english/aboutTSMC — dedicated foundry; founded 1987.
- https://www.tsmc.com/english/dedicatedFoundry/technology/logic
- https://www.tsmc.com/english/dedicatedFoundry/services/advanced-packaging
- https://github.com/heygen-com/hyperframes
- https://www.remotion.dev/docs/
- https://docs.diffusion.studio/docs

TSMC is the subject company's trademark. The fetched official logo is kept among research assets; the films use plain-text company naming and original diagrams. Space Grotesk font license is bundled with assets. System Noto CJK provides Chinese glyphs.
