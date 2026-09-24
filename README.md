After working on this mod the whole night, im glad as to how it turned out. Welcome to Color Sniper Enhanced(CSE)-- The only mod you will ever need for color related things. Sniper? Ofcourse. Priority list? Yes. Rainbow all? Yes. Force all to be Fortegreen? Yup. Phantom smoke bomb? Ofcourse. Permanently ban all players from the game? Ofcous- no...
This was supposed to be a simple color sniper with a priority list, but it turned into something much bigger( as the 2k+ lines of code suggests). Test it yourself to find out. Or if you time, also check out the README if you want a description of all the features as some arent very self explantory. Features like auto reset rainbow bomb upon player join, disable host only features when not host, etc are passive features; meaning they run behind the scenes to keep the mod stable. They are not listed here

(Yes, the README below is made by ChatGPT. I uploaded the entire source code and Itold it to make a detailed description of each feature, W codex. You bet I wasn't writing all this myself)

# Color Sniper Enhanced

Color Sniper Enhanced is a BepInEx IL2CPP mod for **Among Us**. It started as a priority-based color selector and grew into a lobby color and rainbow-effects toolbox.

## Requirements

- Among Us
- BepInEx for IL2CPP
- A build of the mod compiled for the installed Among Us version

Install the compiled plugin DLL in `BepInEx/plugins` and launch the game. The plugin identifies itself as **Color Sniper Enhanced 1.0.0** and runs in `Among Us.exe`.

## Opening the menu

The menu opens when the plugin loads. Press **F8** to hide or show it. Drag the top of the window to move it. The menu has three tabs: **Self**, **Lobby**, and **Players**.

## Self tab

### Sniper

When enabled, the sniper checks the saved priority list and requests the highest-priority color that is currently available. The check runs on the game’s update loop, so the configured 5 ms interval cannot run faster than the frame rate.

### Duplicate Colors (Host Only)

Lets the host take a color already used by another player. It changes the local player’s color without changing the other player’s color. This is a host-only operation.

### Switch Self to Fortegreen (Host Only)

Switches the local player to Fortegreen. Switching it off restores the color the player had before enabling it. Fortegreen is kept out of the priority list.

### Self Rainbow

- **Host:** cycles through palette colors every 0.1 seconds using the host’s direct color update path.
- **Non-host:** cycles every 0.2 seconds using the normal `CmdCheckColor` request.

The game and server may limit how quickly color requests take effect.

### Rainbow Bomb / Force Phantom

For a host in the lobby, the toggle arms Phantom assignment for the local player when the next game starts. Re-toggle the control in-game to start or stop Rainbow Bomb. The Phantom effect cycles colors and sends the vanish/appear ability RPCs.

The helper text recommends enabling **Disable Role Selection** in Sicko under **Host > Utils** when using the lobby role assignment if the user is using Sicko, otherwise there may be problems with assigning Phantom role.

### Rainbow Bomb (In Lobby, Host Only)

In a lobby, the host can assign themselves Phantom and start Rainbow Bomb immediately. Turning the toggle off stops the effect and restores the host’s previous role.

### Priority list

Drag colors to change their order. The first color is highest priority; the last is lowest. **Reset Priority** restores the default order. The priority list is saved in the BepInEx config, so it persists after leaving the game.

## Lobby tab (Host Only)

### Duplicate Colors for All Players

Allows players to join using their preferred color even if another player already has it. The original player keeps their color too.

### /color permissions for everyone

- **Allow All Players to Use /color in Lobby:** enables `/color` requests during the lobby.
- **Allow All Players to Use /color in Game:** enables `/color` requests during a match as well.

The in-game toggle applies to players covered by the lobby-wide permission or an individual permission in the Players tab.

### Force Rainbow Bomb for All (+25 Mode Only)

Assigns Phantom to every other player and starts their Rainbow Bomb. Players who join while it is enabled are included. Turning it off restores their previous roles. This is intended for **+25 mode** lobbies; normal public lobbies may reject ability RPCs.

### Turn All to Fortegreen

Forces all current players to the glitched color Fortegreen and keeps enforcing that color. Turning it off restores each player’s previous color.

### Linear Rainbow for All

Cycles the whole lobby through the palette together, so everyone changes to the same color at once.

### Random Rainbow for All

Assigns each player a random palette color on each cycle, so players do not all receive the same color.

Both lobby-wide rainbow modes are host-only and use 0.1 second update intervals.

## Players tab

Select another player from the list to show that player’s controls. The tab is host-only for changing other players.

### Player color and rainbow controls

- **Linear Rainbow:** cycles the selected player through palette colors in order.
- **Random Rainbow:** assigns the selected player a random palette color each cycle.
- **Force Rainbow Bomb (+25 Mode Only):** assigns Phantom to the selected player and runs their Rainbow Bomb. Turning it off restores their previous role.
- **Color list / Force Color:** choose a palette color, including Fortegreen, and force it onto the selected player.
- **Allow Player to Change Color:** removes an active enforced color or rainbow assignment so the player can change their color again.

The host’s color enforcement reapplies assigned colors if a player changes away from them.

### Per-player /color permissions

- **Give Player /color Permission in Lobby:** lets that player use `/color` in the lobby.
- **Allow /color in Game:** lets that player use `/color` during a match. This control is selectable independently; the host can configure it even when the player’s lobby permission is off.

In chat, the player enters `/color <color>`, for example `/color cyan`. Color names are matched without regard to capitalization. If a player lacks permission, or is not allowed to change color during a match, the host sends a private notice visible only to that player.

## Rainbow Bomb lobby compatibility

The other-player and all-player Rainbow Bomb controls are marked **+25 MODE ONLY**. They rely on host-side role and ability RPCs, which can be blocked by normal public-lobby protections. In testing, they worked in +25 lobbies with relaxed anti-cheat settings; they are not expected to work reliably in standard public lobbies.

## Settings and persistence

The **priority order** is the only setting saved to BepInEx config. Other toggles and per-player permissions are runtime settings and are not written to the config.


Okay, human back
Credits time baby:
1. Sicko menu: For the Color sniper idea in the first place
2. Hydra menu: for the glitterbomb inspiration, renamed to Rainbow bomb in CSE( no, i didnt simply take it and put it into my mod, i improved it by making it work in lobby, making it work for non-mod players, and over all making it much more customisazble customizable)
3.  Honorable mention:
    Braincell number 2: Supporter









Does anyone even notice my mods, let alone read these READMEs? I assume not...



