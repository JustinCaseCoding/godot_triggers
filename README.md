# godot_triggers

Source-like triggers for Godot 4: an `Area2D`/`Area3D` with a list of outputs in the inspector. Each output calls a method on a node, optionally after a delay.

Based on [godot-trigger](https://github.com/smolsosig/godot-trigger) by sosigmidget (MIT-0). See LICENSE.

## Usage

1. Add a `Trigger2D` or `Trigger3D` to your scene and give it a `CollisionShape2D`/`3D`.
2. Set the collision **mask**. Anything in the layers it scans activates the trigger; the trigger's own layer has no effect.
3. Add outputs in the inspector.

## Output

| field | type | meaning |
| --- | --- | --- |
| `output` | String | what fires it: `body_entered`, `body_exited`, `area_entered`, `area_exited` |
| `target` | NodePath | node to call |
| `target_method` | StringName | method name on that node |
| `arguments` | Array | arguments passed to the method |
| `delay` | float | seconds to wait before firing |

## Trigger

- `enable_on_start` — turn monitoring off on startup
- `repeatable` — if false, monitoring is disabled after the first fire
- `enable_monitoring(enable)` — toggle at runtime
