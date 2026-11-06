# Click Before Frames

An input buffer for Geometry Dash.

When you click (or release, in wave and robot), a hidden **ghost player** is simulated a short way ahead with your input. If the ghost would die, the mod retries the input with 1 to N physics ticks of delay. If a delayed version clearly survives longer, your input is held back and delivered that many ticks later. Taps and hold lengths are kept, so nothing gets swallowed.

1 tick = 1/240 s = 0.25 frames at 60 fps.

## Stages

Cycle the stage with the stage key, or with the arrows in the in-game menu.

| Stage | Max delay | Max delay in wave |
| ----- | --------- | ----------------- |
| 1 | 0.5 frames | 0.5 frames |
| 2 | 1 frame | 1 frame |
| 3 | 2 frames | 2 frames |
| 4 | 4 frames | 2 frames |
| 5 | 6 frames | 3 frames |
| 6 | 8 frames | 4 frames |
| Custom | set in the mod settings | set in the mod settings |
| Off | no buffering | no buffering |

The in-game menu also has three presets: **Safe** (2 frames), **Balanced** (4 frames) and **Aggressive** (8 frames).

## Using it

- **Open the menu:** press `` ` `` in a level, or tap the round **BUFFER** button in the pause menu (works on touch devices, no keyboard needed).
- **Change stage:** the stage key (default `6`) or the arrows in the menu.
- **Other keys:** `F8` copy console log, `F9` show/hide the in-game console, `F10` path view, `F11` forget the current level. All keys can be rebound in the mod settings.
- **Practice mode only:** turn this on in the settings if you only want buffering while practicing.
- **Training mode:** predicts every input but never delays it. It only shows how early or late you were, so you can learn the timing yourself.

## Compatibility

- Geometry Dash 2.2081 with Geode 5.11.2 or newer 5.11 releases.
- Works with Click Between Frames (the prediction starts from the exact click moment). CBF Extrapolate is visual only and does not affect predictions.

## Fair play

This mod changes when your inputs reach the game. Auto-click, auto-release and any physics TPS other than 240 are not legit for records. Check the rules of the list or leaderboard you play on before using it for a completion.
