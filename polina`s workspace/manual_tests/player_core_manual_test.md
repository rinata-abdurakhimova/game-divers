# Player/Core Manual Test

Run this after copying snippets into the real project.

## Isolation Test

- [ ] Open the player sandbox or `Player.tscn`.
- [ ] Confirm the scene runs without errors.
- [ ] Press left/right/up/down.
- [ ] Confirm movement speed feels controllable.
- [ ] Release input.
- [ ] Confirm velocity stops or decelerates as intended.
- [ ] Press `action`.
- [ ] Confirm one local action signal or debug print fires.
- [ ] Call damage once.
- [ ] Confirm health decreases.
- [ ] Call damage again during invulnerability.
- [ ] Confirm duplicate hits are blocked if invulnerability is enabled.
- [ ] Reduce health to zero.
- [ ] Confirm `died` fires only once.
- [ ] Call reset.
- [ ] Confirm position, velocity, health, action cooldown, and alive state reset.

## Integrated Test From Main

- [ ] Launch from `Main.tscn`.
- [ ] Start a run.
- [ ] Move the player.
- [ ] Use the core action.
- [ ] Trigger one risk event.
- [ ] Confirm HUD/audio reacts through signals, not direct node paths.
- [ ] Trigger success.
- [ ] Restart.
- [ ] Trigger failure.
- [ ] Restart again.
- [ ] Run `tools\qa.cmd`.

## Fast Debug Prints To Remove Before Polish

```gdscript
print("action requested")
print("health changed: %s/%s" % [current, maximum])
print("player died")
print("reset complete")
```
