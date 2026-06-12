# Polina Workspace

Neutral Core Systems prep for tomorrow. This folder is not the jam game and should not be wired into
`project.godot` until the theme, MVP, and integration contract are locked.

## What Is Here

- `snippets/player_controller_2d.gd`: reusable 4-direction `CharacterBody2D` controller.
- `snippets/health_component.gd`: reusable health, damage, healing, invulnerability, and reset logic.
- `snippets/action_cooldown.gd`: reusable primary-action cooldown and buffering helper.
- `snippets/timer_score_rules.gd`: generic score/timer/outcome rules node.
- `snippets/core_events_bridge.gd`: optional bridge from local Polina-owned signals to `GameEvents`.
- `snippets/player_sandbox.tscn.template`: copyable isolated scene template.
- `contract_templates/player_core_feature.md`: contract section to fill after concept lock.
- `manual_tests/player_core_manual_test.md`: shortest manual test for the player/core slice.
- `tomorrow_context.md`: compressed context to paste into tomorrow's prompt.

## Safe Use Tomorrow

1. Wait for theme and concept lock.
2. Pick only the snippets that match the chosen mechanic.
3. Copy them into owned paths:
   - `scripts/actors/player/`
   - `scripts/gameplay/`
   - `scenes/actors/Player.tscn`
4. Rename signals only by updating `INTEGRATION_CONTRACT.md`.
5. Keep UI, audio, and world content behind documented signals.
6. Run `tools\qa.cmd` after integration.

## Do Not Do Yet

- Do not create final enemies, collectibles, levels, or theme-specific rules here.
- Do not add autoloads from this folder.
- Do not edit `project.godot`, `Main.tscn`, or Alina/Rinata owned paths without handoff.
