## Toba Notification Frameworks

> **Support All**
> **Support Icons**
> **Support Games**
> **Support Executors**
> **Support Audio**
> **Support Loadstrings**


# Toba Notification Framework Guide

### Overview

> **This framework allows you to create advanced, sketchy, or professional notifications in Roblox. It includes animations, styles, sounds, progress bars, typewriter text, draggable windows, dim background, and safe code execution.**


### Features and Customization

## 1. Title

• **Description: The text that appears at the top of the notification.**

**Default: "Windows Security"**

• **Example: Title = "Windows Defender"**


## 2. Desc

• **Description: Main description text inside the notification.**

• **Default: "Suspicious activity detected"**

• **Example: Desc = "Trojan.Win32.Injector detected in system files."**


## 3. Text

• **Description: Text on the confirm button.**

**Default: "OK"**

• **Example: Text = "Remove Threat"**


## 4. Mode

• **Description: Determines if new notifications replace the current one or wait in queue.**

• **Options: "Replace" or "Queue"**

**Default: "Replace"**

• **Example: Mode = "Queue"**


## 5. Style

• **Description: The visual style of the popup.**

• **Options: "Win10", "Win11", "Sketch", "Professional"**

**Default: "Win11"**

• **Example: Style = "Sketch"**


## 6. Animation

• **Description: How the popup appears.**

**Options: "Pop", "Slide", "Fade", "Glitch", "Corrupt"**

**Default: "Pop"**

• **Example: Animation = "Glitch"**


## 7. Duration

• **Description: Time in seconds before the notification auto-closes.**

**Default: 6**

• **Example: Duration = 8**


## 8. Cooldown

• **Description: Minimum time (seconds) before a new notification can appear.**

**Default: 0**

• **Example: Cooldown = 2**


## 9. Draggable

• **Description: Makes the popup draggable.**

**Default: true**

• **Example: Draggable = true**


## 10. DimBackground

• **Description: Darkens the background behind the popup.**

**Default: true**

**Example: DimBackground = true**


## 11. Progress

• **Description: Displays a progress bar for fake scanning/loading.**

**Default: false**

• **Example: Progress = true; ProgressTime = 5**


## 12. Typewriter

• **Description: Description text types letter by letter.**

**Default: false**

• **Example: Typewriter = true; TypeSpeed = 0.02**


## 13. Sounds

• **OpenSound: Plays when popup opens.**

• **LoopSound: Plays while popup is open, stops on close.**

• **CloseSound: Plays when popup closes.**

**SoundVolume: 0 to 1**

• **Example: OpenSound = "rbxassetid://9118823106"; CloseSound = "rbxassetid://138186576"; SoundVolume = 1**


## 14. Load

• **Description: Optional code execution after closing the popup. Can use a raw GitHub URL.**

# **Default: nil**

```lua
Example: Load = "https://raw.githubusercontent.com/USER/REPO/main/script.lua"
```

## 15. Queue System

• **Automatically queues notifications if Mode = "Queue".**

• **Notifications will play one after another without overlapping.**


## Example Usage

# **Minimal**

```lua
local Notification = loadstring(game:HttpGet("YOUR_GITHUB_RAW_URL"))()
Notification:Notify({
    Title = "Hello",
    Desc = "This is a clean notification",
    Text = "OK"
})
```

## Full Feature

```lua
Notification:Notify({
    Title = "Windows Defender",
    Desc = "Trojan.Win32.Injector detected in system files.\nImmediate action required",
    Text = "Remove Threat",
    Mode = "Queue",
    Style = "Win11",
    Animation = "Glitch",
    Duration = 8,
    Cooldown = 2,
    Draggable = true,
    DimBackground = true,
    Progress = true,
    ProgressTime = 5,
    Typewriter = true,
    TypeSpeed = 0.02,
    OpenSound = "rbxassetid://9118823106",
    LoopSound = nil,
    CloseSound = "rbxassetid://138186576",
    SoundVolume = 1,
    Load = "https://raw.githubusercontent.com/USER/REPO/main/script.lua"
})
```

## Replace Mode Example

```lua
Notification:Notify({
    Title = "Replace Mode",
    Desc = "This will instantly replace the current notification",
    Mode = "Replace"
})
```

## Queue Mode Example

```lua
Notification:Notify({
    Title = "First Notification",
    Mode = "Queue"
})
Notification:Notify({
    Title = "Second Notification",
    Mode = "Queue"
})
```

## Quick Tips

• **Combine Sketch style + Glitch animation + Loop sound for scary alerts.**

• **Combine Win11 + Fade + Typewriter + Progress for professional modern alerts.**

• **Always use Queue for multiple notifications in a row.**

• **Use Load to run safe scripts after the user acknowledges the notification.**
