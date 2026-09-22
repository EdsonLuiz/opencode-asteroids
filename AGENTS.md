# Asteroids — Agent Guide

## Project
Classic Asteroids clone in pure HTML5 Canvas + vanilla ES6 JS. No dependencies, no bundler, no build step.

## Files
- `index.html` — Entry point, loads `game.js`
- `game.js` — All game logic (single file, ~590 lines)
- `favicon.svg` — Window icon

## Running
Open `index.html` directly in browser, or:
```bash
npx serve .
# then http://localhost:3000
```

## Architecture
- Single-file game loop: `requestAnimationFrame` → `update(dt)` → `draw()`
- State machine: `'playing'` | `'dead'` | `'gameover'`
- Toroidal wrapping via `wrap(v, max)` utility
- Classes: `Ship`, `Bullet`, `Asteroid`, `ShootingStar`, `Particle`, `Powerup`
- Input via global `keys` / `justPressed` objects

## Key Constants (game.js)
- Canvas: `W=800`, `H=600`
- Asteroid radii: `[0, 16, 30, 50]` (size 1=small, 3=large)
- Scoring: `POINTS = [0, 100, 50, 20]` (small=100, large=20)
- Ship: radius 12, thrust 260 px/s², rotation 3.5 rad/s
- Bullet speed: 520 px/s, TTL 1.1s
- Speed powerup (`speed`): 2x thrust for 5s (`speedBoost` timer on Ship), yellow diamond with `S`, 8% spawn on asteroid destroy (`powerups` array)
- Shooting star: 51% spawn chance per level, once per game; 120 px/s horizontal meteor with a fading trail, no wrapping, 200 points on destruction

## Controls
| Key | Action |
|-----|--------|
| ← → | Rotate |
| ↑   | Thrust |
| Space | Shoot / Restart (gameover) |

## No Testing / Linting / Typecheck
No tooling configured. Verify manually in browser.

## Commit Style
Use **Conventional Commits** with a short scope-less subject following the pattern seen in previous commits:
- `feat: <description>` - new feature/functionality
- `docs: <description>` - documentation changes
- `chore: <description>` - maintenance/tooling changes

Examples from the repo:
- `feat: add weather CLI application with multi-city support...`
- `docs: create agents.md`
- `chore: add build result`