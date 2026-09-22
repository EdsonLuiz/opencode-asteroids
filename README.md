# Asteroids

Clone of the classic arcade **Asteroids** implemented in pure HTML5 canvas, with no dependencies or bundler.

## Description

Spaceship in an asteroid field with edge wrapping (space is toroidal). Destroy asteroids to score points: large ones split into medium ones, medium ones into small ones. Includes special power-ups and an occasional one-time shooting star that crosses the screen.

## Technologies

- **HTML5 Canvas** — 2D rendering
- **JavaScript (ES6+)** — game logic in a single `game.js` file
- No frameworks, no bundler, no dependencies

## How to run

Open `index.html` directly in the browser (double click), or use a local server:

```bash
npx serve .
```

Then visit `http://localhost:3000`.

## Controls

| Key       | Action      |
| --------- | ----------- |
| `←` `→`   | Rotate ship |
| `↑`       | Thrust      |
| `Space`   | Shoot       |

## Scoring

| Target | Points |
| ------ | ------ |
| Large    | 20     |
| Medium   | 50     |
| Small    | 100    |
| Shooting star | 200 |

## Features

- 3 lives with temporary invincibility upon respawn (blinking)
- Asteroids split into smaller fragments when destroyed
- Explosion particles when destroying asteroids
- **Speed powerup** (`S`): doubles ship thrust for 5 seconds (8% chance to spawn when destroying an asteroid)
- **Shooting star**: a one-time meteor that crosses the screen without wrapping; it has a 51% chance to appear per level, moves faster than asteroids, and awards 200 points when destroyed
