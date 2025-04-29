### Preview
![a](https://github.com/Eazvy/UILibs/blob/main/Librarys/Kinx/Screenshot%202022-12-04%20133040.png?raw=true)

Thanks for the clarification! You're asking for **developer-facing documentation for the UI library itself**, explaining how to use its features like creating windows, tabs, sliders, buttons, toggles, etc. Here's a clean, structured documentation for that purpose:

---

# 📚 `UILib` – Roblox UI Library Documentation

A lightweight UI library for Roblox scripts, featuring windows, tabs, sliders, toggles, buttons, labels, and notifications.

---

## 📥 Loading the Library

```lua
local UILib = loadstring(game:HttpGet('https://raw.githubusercontent.com/inceldom/kinx/main/ui'))()
```

This fetches and loads the UI library from a remote GitHub source.

---

## 🪟 Creating a Window

```lua
local win = UILib:Window(title, color, toggleKey)
```

- `title` *(string)* – Title displayed on the UI.
- `color` *(Color3)* – Accent color for the UI.
- `toggleKey` *(Enum.KeyCode)* – Key to show/hide the UI.

**Example:**
```lua
local win = UILib:Window("My UI", Color3.fromRGB(44, 120, 224), Enum.KeyCode.RightControl)
```

---

## 📑 Creating Tabs

```lua
local tab = win:Tab(tabName)
```

- `tabName` *(string)* – The name shown on the tab.

**Example:**
```lua
local MainTab = win:Tab("Main")
```

---

## 🎚️ Adding Sliders

```lua
tab:Slider(name, min, max, default, callback)
```

- `name` *(string)* – Label for the slider.
- `min`, `max`, `default` *(number)* – Value bounds and default value.
- `callback(value)` – Function to call when the slider value changes.

**Example:**
```lua
tab:Slider("WalkSpeed", 0, 100, 16, function(val)
    game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = val
end)
```

---

## ✅ Adding Toggles

```lua
tab:Toggle(name, default, callback)
```

- `name` *(string)* – Label shown.
- `default` *(boolean)* – Initial state.
- `callback(state)` – Function called with `true` or `false`.

**Example:**
```lua
tab:Toggle("Noclip", false, function(enabled)
    -- enable/disable logic
end)
```

---

## 🔘 Adding Buttons

```lua
tab:Button(name, callback)
```

- `name` *(string)* – Button label.
- `callback()` – Function to execute when clicked.

**Example:**
```lua
tab:Button("Teleport", function()
    print("Teleported!")
end)
```

---

## 🏷️ Adding Labels

```lua
tab:Label(text)
```

Displays non-interactive text on the UI.

**Example:**
```lua
tab:Label("UI Toggle Key: Right-Ctrl")
```

---

## 🔔 Showing Notifications

```lua
UILib:Notification(title, message, buttonText)
```

- `title` *(string)* – Notification title.
- `message` *(string)* – Message body.
- `buttonText` *(string)* – Button label to dismiss.

**Example:**
```lua
UILib:Notification("Alert", "Something happened!", "Okay")
```

---

## 📌 Notes

- All UI elements are modular and tied to tabs.
- You can add unlimited elements to a tab.
- UI toggles automatically hide/show the full GUI.
- The library uses `Drawing` for ESP and standard Roblox UI for controls.

---

Would you like this turned into a code snippet template or GitHub README file?
