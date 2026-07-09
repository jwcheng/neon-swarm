# Neon Swarm

A lane-based mob growth runner in a rain-slicked cyberpunk megacity. Steer a swarm of chrome runner-bots through multiplier gates, dodge danger gates, and slam the horde into a boss mech at the end of every sector.

**Play:** open `index.html` in a browser, or hit the live link (Vercel deploy).

## The loop

- Your swarm auto-runs down a 3-lane elevated highway.
- Steer left/right to pass through gates: **+N** adds units, **xN** multiplies, red gates subtract or halve.
- Every gate does exactly what it displays. No bait gates, no rigged difficulty.
- At the end of each level the swarm pours into a boss with a visible HP bar. 1 unit = 1 damage. Bring more units than the boss has HP.

## Controls

| Input | Action |
|---|---|
| Touch drag | Steer (mobile) |
| Mouse drag | Steer (desktop) |
| A / D or arrow keys | Shift one lane |

All three inputs are live simultaneously.

## Levels

10 sequential sectors. Levels 1-4 are onboarding. Level 5 is the hinge: split-path forks, two-phase bosses, faster speed. Levels 6-10 escalate hard: shrink gates hidden in multiplier clusters, back-to-back forks, multi-phase bosses, and a finale gauntlet that demands near-perfect lane discipline. Every level is beatable through skill alone.

Progress persists in localStorage. Dying never revokes unlocked levels: retry instantly or jump back via level select.

## Stack

- Single HTML file, no build step
- [Three.js r128](https://threejs.org/) (CDN) for rendering
- GPU-instanced swarm (500+ visible units at 60fps)
- UnrealBloomPass + custom grain/vignette/chromatic-aberration shader for the neon look
- WebAudio synth SFX, no audio assets
- Adaptive quality: drops pixel ratio, shadows, then bloom before it ever drops frames

## Design constraints (on purpose)

No ads, no IAP, no energy system, no currency, no fake gates, no forced losses. The core mechanic, played straight.

## Deploy

Static file. Push to GitHub, import the repo in [Vercel](https://vercel.com), done. No config needed.

## License

MIT
