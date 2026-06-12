# Player/Core Feature Contract Template

Feature:

Owner: Polina

Owned scenes/scripts:

- `scenes/actors/Player.tscn`
- `scripts/actors/player/`
- `scripts/gameplay/`

Inputs:

- `move_left`
- `move_right`
- `move_up`
- `move_down`
- `action`
- `restart` if this feature owns isolated retry behavior

Emits:

- Local player signals:
  - `action_requested`
  - `health_changed(current: int, maximum: int)`
  - `hit_taken(amount: int, current: int, maximum: int)`
  - `died`
  - `reset_completed`
- Global events only through agreed `GameEvents` integration:
  - `player_hit(amount: int)`
  - `health_changed(current: int, maximum: int)`
  - `player_died`
  - `score_changed(value: int)`
  - `timer_changed(seconds_left: float)`
  - `level_completed`

Consumes:

- Player input actions.
- Optional `GameState` values after Alina implements them.
- Optional world collision/hit calls from Rinata-owned hazards.

Assets:

- Placeholder sprite or shape is allowed.
- Expected final names:
  - `assets/sprites/player_idle.png`
  - `assets/sprites/player_move.png`

Reset behavior:

- Position returns to spawn/start position.
- Velocity clears to zero.
- Health returns to maximum.
- Cooldowns clear.
- Death state clears.
- Transient listeners do not duplicate.

Isolation test:

1. Run `Player.tscn` or a temporary sandbox scene.
2. Move in four directions.
3. Press `action`.
4. Apply damage.
5. Confirm death signal at zero health.
6. Reset and confirm the player can move again.

Main-scene test:

1. Launch from `Main.tscn`.
2. Start a run.
3. Move and use the core action.
4. Trigger risk feedback.
5. Trigger success or failure.
6. Restart without relaunch.

Fallback/cut:

- Keep movement, health, one action signal, one success trigger, one failure trigger.
- Cut advanced movement, combo actions, procedural rules, and secondary resources first.
