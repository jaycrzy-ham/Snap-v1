# Snap UI Library
**Created by l0ckerV5**

# Example Usage
**An example script with the UI Library**
```
local Snap = loadstring(game:HttpGet("https://github.com/jaycrzy-ham/Snap-v1/raw/refs/heads/main/Source"))()

local GUI = Snap:CreateBase({
    Name = "Snap_UI"
})

local MenuCore = Snap:CreateFrame({
    Name = "MenuCore",
    Parent = GUI,
    BackgroundColor3 = Color3.fromRGB(28, 30, 39),
    Size = UDim2.new(0, 400, 0, 400),
    Position = UDim2.new(0.5, -200, 0.5, -200),
    Draggable = true,
    Active = true
})

local Window = Snap:CreateFrame({
    Parent = MenuCore,
    BackgroundColor3 = Color3.fromRGB(76, 130, 181),
    Size = UDim2.new(1, 0, 0, 25)
})

local Title = Snap:CreateLabel({
    Parent = Window,
    Text = "Snap",
    TextColor3 = Color3.new(1, 1, 1),
    Size = UDim2.new(0, 200, 0, 25),
    Position = UDim2.new(0.25, 0, 0, 0),
    Font = Enum.Font.SourceSans,
    TextSize = 14
})

local Button = Snap:CreateButton({
    Parent = MenuCore,
    Text = "Click Me!",
    BackgroundColor3 = Color3.fromRGB(27, 30, 37),
    Position = UDim2.new(0.1, 0, 0.1, 0),
    Size = UDim2.new(0, 80, 0, 30),
    Font = Enum.Font.SourceSans,
    TextColor3 = Color3.new(1, 1, 1),
    TextSize = 14
})

Button.MouseButton1Click:Connect(function()
    print("Button clicked!")
end)

local TextBox= Snap:CreateTextBox({
    Parent = MenuCore,
    Text = "16", -- Default Text
    BackgroundColor3 = Color3.fromRGB(27, 30, 37),
    Position = UDim2.new(0.1, 0, 0.3, 0),
    Size = UDim2.new(0, 100, 0, 30),
    Font = Enum.Font.SourceSans,
    TextColor3 = Color3.new(1, 1, 1),
    TextSize = 14
})

TextBox.FocusLost:Connect(function(PressedEnter)
    if PressedEnter then
        local Input = TextBox.Enter
        local Value = tonumber(Input)

        if Value then
            game.Players.LocalPlayer.Humanoid.WalkSpeed = Value
        end
    end
end)
```

***Keep in mind that the script is made for basic scriot hub gui's, thats the reason it doesn't have Toggles, Sliders, Dropdowns, Configures, etc.***
