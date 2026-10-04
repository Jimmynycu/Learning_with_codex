# TSMC — The Scale of Possibility

28-second independent brand film. Native Remotion composition with a Three.js 3D scene, original geometry/textures, Chinese/English typography and an original procedural score. The earlier three engine demonstrations are retained separately. The delivered master includes a frame-accurate FFmpeg join of a corrected 3.5-second native render; a fresh full render from this corrected source produces the revised movement directly. See CRITIQUE.md and the repair logs.

## Reproduce

From `tsmc-studio/`:

```bash
npm ci --cache /workspace/.cache/npm
python -m venv .venv
source .venv/bin/activate
python -m pip install -r director-cut/requirements.txt
python director-cut/scripts/score.py
ffmpeg -y -i public/director-cut/score-premaster.wav -af loudnorm=I=-16:TP=-1.5:LRA=8 -ar 48000 public/director-cut/score.wav
node director-cut/scripts/render.mjs stills
node director-cut/scripts/render.mjs draft
node director-cut/scripts/render.mjs final
```

Requirements: Node, Chromium at `/usr/bin/chromium`, FFmpeg, Python with NumPy/SciPy. Rendering uses local Chromium's SwiftShader-on-ANGLE (`swangle`) because this environment has no X display/GPU. No account, MCP or paid generation service is used.

The preview samples every third timeline frame at 10 fps, with lower 3D resolution, to inspect choreography. The final render evaluates every frame at 30 fps and full composition resolution. Preview is never substituted for the published master.

## Files

- `src/World.tsx`: deterministic camera choreography, physically based wafer and die materials, texture generation, instancing, layered package, moving circuit signals.
- `src/Film.tsx`: native Remotion typography, audio, overlays and final signature.
- `scripts/score.py`: original harmonic phrases, bass, arpeggios, percussive events, assembly ticks, sweeps and algorithmic room reverb.
- `beats.json`: shared beat grid and intended action hits.
- `DIRECTION.md`: concept, shot plan and acceptance criteria.
- `evidence/`: keyframe, render, audio and public playback checks.
- `output/tsmc-scale-of-possibility.mp4`: final film.

The official TSMC logo is a fetched research asset. Other diagrams, textures and audio are original. Space Grotesk and IBM Plex Mono licenses are included alongside fonts. Noto CJK must be installed for Chinese glyphs. Geometry is conceptual, not a real process or package specification. This is not an official TSMC advertisement.

## Reference honesty

The tutorial's publicly available transcript was reviewed by the research sub-agent. Its original visual frames could not be retrieved: YouTube requests were denied by the environment proxy and its embed player rejected playback. The methods were applied, but no claim of frame-by-frame similarity or objectively surpassing the tutorial has been verified. See `../evidence/reference-study/REFERENCE-STUDY.md`.
