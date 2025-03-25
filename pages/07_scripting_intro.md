# 07 - Scripting . . .
It may be intimidating, but scripting is essential for giving your map life and function. Fortunately for you, creating a full map is possible with just basic knowledge of TRIA.os functions. There are three map scripts inside the map kit, and you can add even more if you wanted, but there’s only one that your map needs in order to run, the `MapScript`, so that’s what we’ll take a look at first.

## IMPORTANT: Runtime Script
Since TRIA.os 1.0, every unverified map (so basically every map) needs the following line of code **at the top of every script** inside the map. This includes MapScript, LocalMapScript, EffectScript, and any other scripts you may have.

``` luau
require(game:GetService("ServerScriptService").Runtime):Init()
```

This ensure the script contents can be inspected by the game for safety.

## MapScript
The MapScript in the map kit should look something like this:

``` luau
require(game:GetService("ServerScriptService").Runtime):Init()

--^^Must be at the top of every script

local MapLib = game.GetMapLib:Invoke()()
local map = MapLib.map

MapLib:GetButtonEvent(1):Connect(function(player)
	MapLib:Alert("Button 1 Pressed", "red", 1)
end)

MapLib:GetButtonEvent(2):Connect(function(player)
	-- This line will set the liquid type to a default type
	MapLib:SetLiquidType(map.Special.Fluid._Liquid3, "lava")
end)

-- This line will move Liquid 2 up 20 studs over the span of 5 seconds
MapLib:MovePart(map.Special.Fluid._Liquid2, Vector3.new(0, 20, 0), 5)

-- This line will move Liquid 3 up 20 studs locally (based on rotation) over the span of 5 seconds
MapLib:MovePartLocal(map.Special.Fluid._Liquid1, Vector3.new(0, 20, 0), 5)
```

### Invoking the MapLib

``` luau
local MapLib = game.GetMapLib:Invoke()()
local map = MapLib.map
```

At the top of the MapScript, there are two lines of code. The first one retrieves the MapLib ‘library’, which contains all TRIA-specific functions that you can use in your script, and you should generally keep it up here. The second line just makes it easier to refer to the map model by creating a variable named ‘map’. 