# AppADay 129: Tap to Color

**Live:** https://augustineiacopelli.github.io/appaday-129-tap-to-color/

A tap to color coloring book. Ten hand drawn scenes, 667 individually fillable regions, twelve crayons, and no flood fill algorithm anywhere. Every region is its own SVG shape with its own id, so a tap colors exactly one space.

## What it does

Pick a crayon from the rail, then tap any shape in the picture to fill it with that color. The blank crayon at the end of the rail works as an eraser, clearing a region and removing it from the fill count. A thumbnail strip switches between the ten pictures, each of which keeps its own progress and earns a badge once every region is filled.

Progress shows as a live count of filled regions against the total for the current picture. Start over clears only the picture you are looking at, and it takes two taps to confirm so a stray press never wipes your work.

## The scenes

House, flower, fish, cat, tree, star, balloons, cupcake, sailboat, and butterfly. Region counts run from 50 on the cat to 98 on the house, deliberately dense so a picture takes real time to finish rather than a handful of taps.

## Saving

Fills are written to localStorage under one key per picture, `coloringbook-house` and so on, holding a map of region id to hex color. All reads and writes are wrapped in try/catch, and everything hydrates in a single pass at load, so a half colored page is still half colored when you come back. Nothing leaves your device and there is no account.

## Built with

One self-contained `index.html` with inline CSS and JavaScript. No frameworks, no build step, no dependencies beyond Google Fonts. The scene geometry was generated programmatically and baked into the markup, which is why the region ids never collide across pictures.

Part of [AppADay](https://augustineiacopelli.github.io/appaday/), one complete app shipped every day.
