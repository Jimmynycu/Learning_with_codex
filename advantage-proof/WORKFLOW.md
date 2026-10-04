# Build Your Next Advantage
60 seconds, English, 1920×1080, 30 fps. Independent TSMC commercial concept.

## Reproduce
Preserve this archive's `tsmc-studio` directory structure. From that directory, install Python packages `numpy pillow scipy` and FFmpeg. The included clean plates and normalized score allow reproduction without Chromium or Node:

    python commercial-film/scripts/film.py stills
    python commercial-film/scripts/film.py final

The output directory and evidence directory must exist (create them if your ZIP extractor omits empty directories).

To rebuild clean plates, run `npm ci`, install Chromium at `/usr/bin/chromium`, then `node commercial-film/scripts/plates.mjs`. This uses Remotion + Three.js and the included director-cut World.tsx. Clean plates are still renders; continuous explanatory 3D geometry is projected and rendered by film.py, not Remotion.

Original score: `python commercial-film/scripts/score.py`, then FFmpeg loudnorm to -16 LUFS / -1.5 dBTP / LRA 9 into public/commercial-film/score.wav. The normalized WAV is included for exact visual/audio reproduction.

## Editorial decisions
The commercial promise is a product design opportunity, not a guaranteed financial return. Thirty two-second beats connect constraint, mechanism, application, economic scenario, roadmap and an official technology-portfolio call to action. Source and comparison conditions stay visible. See SCRIPT.md and research/TECHNICAL-SOURCES.md.

Remotion/Three.js, Pillow/NumPy, FFmpeg and original synthesized music were actually used in this cut. HyperFrames and Diffusion Studio were not used. No narration voice or third-party reference footage is included.
