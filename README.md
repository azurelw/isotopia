# 🌌 Isotopia UI Library

A high-performance, sleek, and modern UI library for Luau environments. Optimized for speed, customizability, and ease of use.

---

## 🚀 Quick Start (Example Usage)

```lua
local window = Isotopia:Window({
    Title = "Isotopia UI",
    Icon = "sword",
    MainColor = Color3.fromRGB(255, 0, 0),
    Transparent = false,
    Size = UDim2.fromOffset(700, 500),
    Spinning = true,
    AnimatedTitle = {
        AnimationColor = Color3.fromRGB(0, 255, 0),
        AnimationSide = "Right",
        AnimationSpeed = 5
    }
})

window:SetToggleKey(Enum.KeyCode.Insert)

local tab = window:Tab({ Title = "Main", Icon = "home" })
local section = tab:Section({ Side = "left" })

section:Toggle({
    Title = "My Toggle",
    Description = "Enable/disable feature",
    Default = false,
    Callback = function(state) print("Toggle:", state) end
})

section:Button({
    Title = "Click Me",
    Description = "A test button",
    Callback = function() print("Button clicked!") end
})

window:load()
```

📑 API Reference
<details>
<summary><b>🪟 Window Functions</b></summary>
    
```lua
window:load()                           -- Loads and displays the window
window:Toggle()                         -- Toggles window minimize/open
window:change_visiblity(state)          -- Changes window visibility (true/false)
window:EditOpenButton(settings)         -- Customize minimize button behavior
window:SetMainColor(color)              -- Changes the main accent color
window:SetSize(newSize)                 -- Changes window size (UDim2)
window:GetSize()                        -- Returns current window size
window:SetTransparent(state)            -- Toggles transparency
window:GetTransparent()                 -- Returns transparency state
window:SetAnimationSettings(settings)   -- Configures title animation
window:GetAnimationSettings()           -- Returns animation settings
window:SetToggleKey(keyCode)            -- Sets window toggle keybind
window:GetToggleKey()                   -- Returns toggle key
window:ClearToggleKey()                 -- Clears toggle keybind
window:SetSpinning(state)               -- Toggles icon spinning
window:GetSpinning()                    -- Returns spinning state
window:update_tabs(tab)                 -- Internal: Updates active tab
window:update_sections(left, right)     -- Internal: Updates visible sections
window:flag_type(flag, flag_type)       -- Checks flag type in config
```
</details>
<details>
<summary><b>📂 Tab & Section Functions</b></summary>
    
```lua
-- Tab Manager
tabManager:Section(settings)            -- Creates a new section

-- Section Modules
section:Toggle(settings)                -- Creates a toggle module
section:Button(settings)                -- Creates a button module
section:Slider(settings)                -- Creates a slider module
section:Dropdown(settings)              -- Creates a dropdown module
section:Label(settings)                 -- Creates a label module
section:Checkbox(settings)              -- Creates a checkbox module
section:Input(settings)                 -- Creates an input module
section:Divider(settings)               -- Creates a divider module
```
</details>
<details>
<summary><b>🧩 Module-Specific Methods</b></summary>
Toggle Module
    
```lua
toggle:Toggle(value)                    -- Toggles state (or sets specific value)

Slider Module
slider:Set(value)                       -- Sets slider value

Dropdown Module
dropdown:Set(value, isToggle)           -- Sets dropdown value
dropdown:Toggle()                       -- Toggles dropdown visibility
dropdown:GetValue()                     -- Returns current value(s)
dropdown:SetValue(value)                -- Sets value directly
dropdown:Clear()                        -- Clears selection

Checkbox Module
checkbox:change_state(state)            -- Changes checkbox state
checkbox:scale_keybind(empty)           -- Adjusts keybind UI size
checkbox:connect_keybind()              -- Connects keybind listener

Input Module
input:update_text(text)                 -- Updates input text
```
</details>
<details>
<summary><b>🛠️ Utilities & Notifications</b></summary>
Notifications
    
```lua
Isotopia:Notify(settings)               -- Creates a notification

Utility Functions
Isotopia.Theme                          -- Theme colors table
Config:save(file_name, config)          -- Saves configuration
Config:load(file_name, config)          -- Loads configuration
Util:map(value, in_min, in_max, out_min, out_max) -- Maps value ranges
Util:viewport_point_to_world(location, distance) -- Converts viewport to world
Util:get_offset()                       -- Gets UI offset based on screen size
```
</details>

