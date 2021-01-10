
Spacecannon mod

# Overview

Adds three scifi/space cannons with various projectile-speed and explosion-strength.
The cannons need HV-Power from a `technic` network and can be controlled via formspec/hand, mesecons or digilines.
They also need to charge first, which can take a couple of seconds depending on cannon-type.

The projectile detonates on impact but only in _non-protected_ areas!

# Screenshots

<img src="./screenshot_1.png"/>
<img src="./screenshot_2.png"/>
<img src="./screenshot_3.png"/>


# Dependencies

Depends on:
* `technic`

Supports:
* `mesecons`
* `digilines`

# Mesecons

An "on" signal triggers a fire-action.

# Digilines

Fire a cannon:
```lua
if event.type == "program" then
 digiline_send("cannon", { command="fire" })
end
```

Example response from a "get" request:
```lua
{
        type = "digiline",
        channel = "c7",
        msg = {
                HV_EU_input = 0,
                HV_EU_demand = 0,
                dir = {
                        y = 0,
                        x = 0,
                        z = 1
                },
                powerstorage = 10000,
                ready = true,
                origin = "c7",
                name = "spacecannon:cannon_green",
                pos = {
                        y = 10,
                        x = -64,
                        z = -53
                }
        }
}
```

Example response from a "fire" request:
```lua
{
        type = "digiline",
        channel = "c2",
        msg = {
                pos = {
                        y = 10,
                        x = -59,
                        z = -53
                },
                origin = "c2",
                success = true
        }
}
```

# Contributors

* @BuckarooBanzay
* @dennisjenkins75

# License

Code: MIT
Textures: CC-BY-SA 3.0

# Attributions

* sounds/spacecannon_shoot.ogg https://freesound.org/people/jonccox/sounds/175261/
