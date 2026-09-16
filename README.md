# Turtle Flower

A generative flower pattern drawn with Python's built-in `turtle` module. Four curved petals are drawn and rotated 120 times, with the pen colour slowly cycling through the HSV colour wheel as it goes.

![Output](output.png)

## Requirements

- Python 3.x
- `turtle` and `colorsys` (both in the standard library — nothing to install)

`turtle` needs a graphical display, so run this on a desktop, not a headless server.

## Usage

```bash
python flower.py
```

The window stays open when the drawing finishes. Close it to exit.

## How it works

| Piece | What it does |
| --- | --- |
| `circle(40 + i*5, 90)` | Draws a 90° arc; the radius grows with each of the four petals |
| `forward(250)` + `left(90)` | The straight edge and corner that close off each petal |
| `rt(100)` | Rotates the whole four-petal group between repetitions — this is what creates the flower instead of one overlapping shape |
| `h += 0.003` | Advances the hue; over 480 petals the colour drifts about 1.4 times around the wheel |

## Tweaking it

The interesting knobs, all near the top of the loop:

- **Rotation angle** — change `rt(100)`. Angles that divide evenly into 360 give symmetric shapes; ones that don't (like 100) give the drifting spiral look.
- **Petal size** — change `forward(250)` for length, or `40 + i*5` for how much the arcs curve.
- **Number of layers** — change `range(120)`. Fewer layers means a sparser, more open flower.
- **Colour speed** — change `h += 0.003`. Larger values cycle through the rainbow faster.

## Notes

Drawing takes a few seconds even at `speed(0)`, since it's rendering 480 petals.

## Licence

MIT
