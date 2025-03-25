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

At the top of the MapScript, there are two lines of code. The first one retrieves the MapLib ‘library’, which contains all TRIA-specific methods that you can use in your script, and you should generally keep it up here. The second line just makes it easier to refer to the map model by creating a variable named ‘map’. 

### Making Variables
If you want to reduce the amount of typing you have to do later, now would be a good time to start making some additional variables as shown:

``` luau
local geometry = map.Geometry
local special = map.Special

local button = special.Button
local exit = special.Exit
local fluid = special.Fluid
local interactables = special.Interactable
local medal = special.Medal
```

### Button Functions
Next are button functions, which execute when a button is pressed. The number inside the parentheses next to `GetButtonEvent` is the button number, and the `end)` line closes the function. In between are whatever lines of code you want to run, which can include standard MapLib functions as shown below.

#### MapLib:Alert
``` luau
MapLib:GetButtonEvent(1):Connect(function(player)
	MapLib:Alert("Button 1 Pressed", "red", 1)
end)
```
Pressing button 1 will cause the MapScript to run the method `MapLib:Alert` which will alert players that the first button is pressed with red text for one second, which is pretty redundant but ok. 

#### MapLib:SetLiquidType
``` luau
MapLib:GetButtonEvent(2):Connect(function(player)
	-- This line will set the liquid type to a default type
	MapLib:SetLiquidType(map.Special.Fluid._Liquid3, "lava")
end)
```

Using `MapLib:SetLiquidType` here will change `_Liquid3` to lava once button 2 is pressed.
