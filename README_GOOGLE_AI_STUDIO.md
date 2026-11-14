# Note for Google AI Studio

This project is a local Vite + Three.js renderer (in `app/`) that depends on files outside `app/` (`../audio`, `../data`) via a custom Vite plugin and repo-root filesystem access. It is designed to run locally with `bun`/Node + Chrome/ffmpeg for preview and offline rendering, not as a standalone Google AI Studio app.

If you still want to try the web preview in a Node/npm environment:
1. Open/import the `app/` folder as the project root (not the repository root).
2. Ensure the sibling folders `audio/` and `data/` are available one level above `app/` with the same paths the app expects.
3. Run `npm install`, then `npm run dev`.
4. Heavy WebGL scenes and the export pipeline may not work in hosted/sandboxed previews.

Common install issues fixed in `app/package.json`:
- Removed invalid `"module": "index.ts"` entry (file did not exist).
- Moved `typescript` from peerDependencies to devDependencies and pinned to a stable version.
- Removed Bun/Playwright-specific dev dependencies and pinned Vite to a stable npm-compatible release.
- Added standard `dev`/`build`/`preview` scripts.
