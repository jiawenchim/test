# Lantern Moth — Game Design

A one-tap, pixel-art arcade game for mobile browsers.

## Pitch

A tiny moth carries a lantern up a long night chimney. Tap to flutter upward
while the moth zigzags on its own between the walls. The lantern slowly dims;
collect sparks to keep it burning. When the light goes out, the run is over.

## Summary

| | |
|---|---|
| Genre | One-tap reflex arcade |
| Platform | Mobile-first web (HTML5 canvas, plain JS, no install) |
| Players | Single player |
| Controls | Single tap anywhere (also Space / click on desktop) |
| Visual style | Pixel art, drawn in code, crisp scaling |
| Run length | 1–3 minutes |
| Purpose | Just for fun: play it and share it with friends |

## Core loop

1. **Movement:** the moth drifts left and right on its own and bounces off the
   chimney walls. Each tap is a flap: a burst of upward speed. Gravity pulls
   it down between taps.
2. **Light = health:** the lantern's glow radius shrinks over time. The
   player can only see the area the light covers.
3. **Sparks:** floating embers that refill the lantern when collected.
4. **Hits drain light:** touching a hazard does not end the run right away.
   It dims the lantern sharply, with a short window where the moth can't be
   hit again. A run ends when the light reaches zero.
5. **Score:** height climbed, plus bonus points for sparks.

## Hazards (added gradually as height increases)

- **Darkness:** always on. The light keeps fading, and the visible radius
  shrinks with it.
- **Chimney ledges:** brick ledges with gaps the moth has to flutter through.
- **Drafts / wind:** visible gust zones that push the moth sideways or down.
- **Spiders & bats:** spiders drop on threads and move up and down; bats swoop
  across the shaft.

## Difficulty ramp

- The light fades faster with height.
- Ledge gaps get narrower and closer together.
- Stronger and more frequent drafts.
- More creatures, which also move faster.
- Sparks become rarer.
- Tuned so a typical run lasts 1–3 minutes.

## Juice & feel

- Screen shake and a flash on hits.
- Particles for flaps, spark pickups and the lantern flicker.
- Floating "+N" pop-ups for spark bonuses.
- Height markers on the chimney wall (e.g. every 100 m).

## Audio

- Retro chiptune sound effects generated in code with WebAudio: flap, spark,
  hit, draft whoosh, game over.
- A simple looping chiptune background track.
- Mute toggle.

## Screens

- **Title:** game name, "Tap to start", mute toggle.
- **Play:** score/height and light meter in the HUD.
- **Game over:** final height and spark count, "Tap to retry".

## Out of scope for v1

- Unlockables / skins
- Saved high scores (could be added later with localStorage)
- Online leaderboards
