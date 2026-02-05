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

📑 API Reference
<details>
<summary><b>🪟 Window Functions</b></summary>
| Function | Parameters | Description |
|---|---|---|
| window:load() | None | Loads and displays the window. |
| window:Toggle() | None | Toggles window minimize/open. |
| window:change_visiblity(state) | boolean | Changes window visibility. |
| window:EditOpenButton(settings) | table | Customize minimize button behavior. |
| window:SetMainColor(color) | Color3 | Changes the main accent color. |
| window:SetSize(newSize) | UDim2 | Changes window size. |
| window:SetTransparent(state) | boolean | Toggles transparency. |
| window:SetToggleKey(keyCode) | Enum | Sets window toggle keybind. |
| window:SetSpinning(state) | boolean | Toggles icon spinning. |
| window:SetAnimationSettings(s) | table | Configures title animation. |
</details>
<details>
<summary><b>📂 Tab & Section Functions</b></summary>
Tab
local tab = window:Tab({ Title = "Name", Icon = "id" })
 * tab:Section({ Side = "left" }): Creates a new section on the specified side.
Section Modules
 * section:Toggle({Title, Description, Default, Callback})
 * section:Button({Title, Description, Callback})
 * section:Slider({Title, Min, Max, Default, Callback})
 * section:Dropdown({Title, Values, Default, Callback})
 * section:Input({Title, Callback})
 * section:Checkbox({Title, Callback})
 * section:Label({Title})
 * section:Divider()
</details>
<details>
<summary><b>🧩 Module-Specific Methods</b></summary>
Toggle Module
 * toggle:Toggle(value): Sets or toggles state.
Slider Module
 * slider:Set(value): Sets slider to specific value.
Dropdown Module
 * dropdown:Set(value, isToggle): Sets value.
 * dropdown:GetValue(): Returns current selection.
 * dropdown:Clear(): Resets the dropdown.
Checkbox Module
 * checkbox:change_state(state): Changes state.
 * checkbox:connect_keybind(): Listens for keybind.
Input Module
 * input:update_text(text): Updates the text field.
</details>
<details>
<summary><b>🛠️ Utilities & Notifications</b></summary>
Notifications
Isotopia:Notify({
    Title = "Notification",
    Content = "Hello from Isotopia!",
    Duration = 5
})

Utility Functions
 * Isotopia.Theme: Access theme colors.
 * Config:save(file, config): Save settings to file.
 * Config:load(file, config): Load settings from file.
 * Util:map(v, iMin, iMax, oMin, oMax): Maps value ranges.
 * Util:viewport_point_to_world(loc, dist): Conversion helper.
</details>

