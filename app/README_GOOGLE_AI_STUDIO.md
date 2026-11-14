# Running in Google AI Studio (limited)

This app is a Vite + TypeScript + Three.js renderer that expects the repository layout:
- `app/` (this folder)
- `../audio/` and `../data/` (sibling folders used at runtime)
- `../app/public/` assets/fonts/plates as included

It is primarily designed for local use (`bun`/Node + browser; offline export also needs Chrome and ffmpeg). Hosted previews like Google AI Studio may fail due to filesystem layout, WebGL/headless limitations, or missing sibling data.

If you import this into Google AI Studio, try:
1. Use `app/` as the project root.
2. Ensure `audio/` and `data/` are available one level above `app/` with the expected files (e.g. `data/lyrics.json`, `data/audio.json`, `audio/pdoom.mp3`).
3. Run `npm install` then `npm run dev` (or `npm run build`).

`package.json` was adjusted for npm-based environments (removed non-existent `module` entry, added scripts, moved TypeScript to devDependencies, and pinned stable Vite/TypeScript versions).
