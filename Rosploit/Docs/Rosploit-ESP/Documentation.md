# Rosploit-ESP Documentation: Information
Official Documentation for Rosploit-ESP Library! This ESP Library is **NOT Stream-Proof**.


### + Pros
+ Perfect Outline on Object/Player
+ Built-In PlayerESP
+ Configurable Theme
+ Player Team Switch
+ 10 Preset Team Colors
+ High-Quality Documentation

### - Cons
- Not Streamproof
- No Tracers
- No Rainbow Color Support
- No Gradient Color Support
- Does not support naming Player or Non-player Instances.

## Update Changelogs (Latest Update: *Rosploit-ESP 1.0*)
All Updates and their changelogs.
### [Latest] Rosploit-ESP 1.0 Update Changelog
+ Configurable Player ESP, With team switching, and custom color themes.
+ Instance ESP for adding ESP  to non-player objects.
+ Toggleable ESP without complete destruction.
## Rosploit ESP Tree
The Full Rosploit-ESP Tree.
```lua
Rosploit-ESP -- Rosploit 1.0 Tree
|- Unload() -- Unloads Rosploit-ESP
|- FindFirstESPInstance(parent) -- Finds first ESP Instance from the parent.
|- CurrentVersion() -- Retruns current Rosploit-ESP Version.
|- InstsanceESP
	|- NewInstance(parent, name, outlineColor, outlineTransparency, fillColor, fillTransparency)
	|- RemoveInstance(path) -- removes an existing esp instance
	|- SetConfig(configTable, path) -- sets the color table of the esp instance
|- PlayerESP
	|- ToggleESP() -- Toggles ESP to the opposite of Current State
	|- SetESPState(state) -- Sets the state of the esp
	|- SetConfig(table, playerName) -- sets the color table of the esp for the players
	|- AddFriend(playerName) -- Adds friendly player color
	|- RemoveFriend(playerName) -- Removes friendly player color
	|- Friends -- Table with all of the names of friendly players
	|- Teams -- Table with all teams existant
	|- State -- A bool value with the state of the PlayerESP
|- Configuration
	|- InstanceESP
		|- OutlineColor -- RGB Color Value
		|- OutlineTransparency -- RGB Color Value
		|- FillColor -- RGB Color Value
		|- FillTransparency -- RGB Color Value
	|- PlayerESP
		|- Enemies -- Enemies Config
			|- OutlineColor -- RGB Color Value
			|- OutlineTransparency -- RGB Color Value
			|- FillColor -- RGB Color Value
			|- FillTransparency -- RGB Color Value
		|- Friends -- Friends Config
			|- OutlineColor -- RGB Color Value
			|- OutlineTransparency -- RGB Color Value
			|- FillColor -- RGB Color Value
			|- FillTransparency -- RGB Color Value
```
## Rosploit-ESP Example UI
Example UI That Uses Rosploit-ESP with most features! The example UI utilizes the Orion UI Library `Rosploit Edit` for the visual UI Interface.
```lua
loadstring(game:HttpGet('https://raw.githubusercontent.com/Dark-Networks/Rosploit/esp/Example.lua'))()
```
# Rosploit-ESP Documentation: Main Module
Documentation for Rosploit-ESP Main Module.
## Load Rosploit-ESP
First you need to define the `RosploitESP` Variable to use the library. This will always load the latest version of `RosploitESP`.
```lua
local RosploitESP = loadstring(game:HttpGet('https://raw.githubusercontent.com/Dark-Networks/Rosploit/esp/Latest.lua'))()
```
## Un-load Rosploit-ESP
Unloading `Rosploit-ESP` Prevents further creation of any more instances, see `Configuration` module to destroy all instances of ESP upon unloading.
```lua
RosploitESP:Unload() -- Completely Unloads Rosploit-ESP
```

## Get Rosploit-ESP Version
Get the current version of `Rosploit-ESP`.
```lua
RosploitESP:GetVersion() -- Return Current Rosploit Version: Ex. "Rosploit-ESP 1.0"
```

## Find First Rosploit-ESP Instance
Like roblox's `FindFirstChildWhichIsA()` but made to find only RosploitESP Instances.
+ `parent`: Parent folder/model to search for RosploitESP Instances.

```lua
RosploitESP:FindFirstESPInstance(parent)
```
# Rosploit-ESP Documentation: Instance-ESP Module
This is about the `InstanceESP` Module for Rosploit
## New ESP Instance
Creates a new ESP Instance for non-player instances.
+ `parent`: Parent of the ESP Instance. ***Required***
+  `outlineColor`: Color of the outline on the Instance. ***Optional***
+  `outlineTransparency`: Transparency of the outline on the instance ***Optional***
+  `outlineColor`: Color of the fill on the Instance. ***Optional***
+  `outlineTransparency`: Transparency of the fill on the instance ***Optional***
```lua
RosploitESP.InstnaceESP:New(parent, outlineColor, outlineTransparency, fillColor,  fillTransparency)
```
## Remove ESP Instance
Removes an existing ESP instance for non-player instances.
+ `path`: Path to the ESP Instance
```lua
RosploitESP.InstanceESP:Remove(path)
```
## Set Color Config On ESP Instance
Set the color settings for ESP Instances
+ `table`: Table with all of the colors for the ESP Instance. See the configuration module section to create a table with the needed colors.
+ `path`: Path to the ESP Instance
```lua
local ColorTable = {
	-- See configuration module section for this
}

RosploitESP.InstanceESP:SetColor(table, path)
```

# Rosploit-ESP Documentation: Player-ESP Module
This is about the `InstanceESP` Module for Rosploit
## Toggle PlayerESP
Toggle the state of PlayerESP
```lua
RosploitESP.PlayerESP:ToggleESP()
```

## Set ESP State
Set the state of PlayerESP
+ `state`: Bool value of the current state of the PlayerESP.
```lua
RosploitESP.PlayerESP:SetState(state)
```

## Set Color Config For Player
Set the Color Config For A Specific Player or All Players.
+ `table`: Config table for the ESP.
+ `playerName`: Name of player to change color of. Can set `playerName` to `All`. Should not be a display name.
```lua
RosplitESP.PlayerESP:SetConfig(table, playerName)
```

## Add Friendly Players
Adds Friendly Players To A Different Color Theme.
+ `playerName`: Name of player add friend. Should not be a display name.
```lua
RosploitESP.PlayerESP:AddFriend(playerName)
```

## Remove Friendly Players
Removes Friendly Players From Their Special Color Theme
+ `playerName`: Name of player add friend. Should not be a display name.
```lua
RosploitESP.PlayerESP:RemoveFriend(playerName)
```

## Friends Varaible
Variable with every added friend.

```lua
RosploitESP.PlayerESP.Friends
```
### Total Number Of Friends
The total number of Friends in your added friends.
```lua
local TotalFriends = #RosploitESP.PlayerESP.Friends
-- Or you could do
local TotalFriends = table.getn(RosploitESP.PlayerESP.Friends)
```

## Teams Varaible
```lua
RosploitESP.PlayerESP.Teams
```

### Total Number Of Teams
The total number of Friends in your added friends.
```lua
local TotalTeams = #RosploitESP.PlayerESP.Teams
-- Or you could do
local TotalTeams = table.getn(RosploitESP.PlayerESP.Teams)
```

## PlayerESP State Variable
Bool varaible containing the state of the `PlayerESP`
```lua
RosploitESP.PlayerESP.State -- either true or false
```
# Rosploit-ESP Documentation: Configuration Module
This is about the `Configuration` Module for Rosploit
## Instance-ESP
This is an example theme for instance-esp
```lua
local customTheme = {
	OutlineColor = Color3.fromRGB(255, 0, 0)
	OutlineTransparency = 0
	FillColor = Color3.fromRGB(255, 0, 0)
	FillTransparency = 1
}

RosploitESP.Configuration.InstanceESP = customTheme
```
## Player-ESP
This is the example themes for player-esp
### Enemies
```lua
local customTheme = {
	OutlineColor = Color3.fromRGB(255, 0, 0)
	OutlineTransparency = 0
	FillColor = Color3.fromRGB(255, 0, 0)
	FillTransparency = 0.8
}

RosploitESP.Configuration.PlayerESP.Enemies = customTheme
```
### Friends
Add custom theme to only friends
```lua
local customTheme = {
	OutlineColor = Color3.fromRGB(255, 255, 0)
	OutlineTransparency = 0
	FillColor = Color3.fromRGB(255, 255, 0)
	FillTransparency = 0.8
}

RosploitESP.Configuration.PlayerESP.Friends = customTheme
```
### Both
Add custom theme to both enemies and friends.
```lua
local customTheme = {
	OutlineColor = Color3.fromRGB(255, 0, 0)
	OutlineTransparency = 0
	FillColor = Color3.fromRGB(255, 0, 0)
	FillTransparency = 1
}

RosploitESP.Configuration.PlayerESP.Enemies = customTheme
RosploitESP.Configuration.PlayerESP.Friends = customTheme
```

___
*©Dark Networks 2023*

*Rosploit-ESP is Developed by Dark Networks under the MIT License. The main branch is where the licence can be found. Maintained by Dark Networks.*
