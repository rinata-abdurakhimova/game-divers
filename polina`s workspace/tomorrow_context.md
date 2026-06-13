# Tomorrow Context For Polina

Role: Polina, Core Systems.

Owned areas:

- `scenes/actors/Player.tscn`
- `scripts/actors/player/`
- `scripts/gameplay/`
- player behavior
- core mechanic
- rules
- health
- score
- timer
- win/lose calculation

Current project status:

- No `project.godot` yet.
- Core scenes are planned, not implemented.
- Existing reserved input actions:
  - `move_left`
  - `move_right`
  - `move_up`
  - `move_down`
  - `action`
  - `pause`
  - `restart`
- Existing reserved global signals:
  - `run_started`
  - `player_hit(amount: int)`
  - `health_changed(current: int, maximum: int)`
  - `score_changed(value: int)`
  - `timer_changed(seconds_left: float)`
  - `player_died`
  - `level_completed`
  - `game_over(won: bool, reason: StringName)`
  - `restart_requested`

First implementation target after concept lock:

Input -> player decision -> local feedback signal -> progress/risk update -> win or lose -> restart.

Ask Codex:

Use `$jam-architecture` first if the mechanic touches Player, World, UI, or autoloads together.
Use `$jam-implement` when the feature contract is clear.

Preferred prompt:

```text
I am Polina. Use $jam-implement. Implement the smallest Core Systems slice for [chosen concept].
Use my owned paths only unless the contract requires a shared edit. Start from the neutral snippets in
`polina`s workspace/snippets`.
```
