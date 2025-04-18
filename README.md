if game:GetService("Players").LocalPlayer:FindFirstChild("PlayerGui"):FindFirstChild("DragMenu") then
    game:GetService("Players").LocalPlayer.PlayerGui.DragMenu:Destroy()
end

local ScreenGui = Instance.new("ScreenGui")
ScreenGui.Name = "DragMenu"
ScreenGui.Parent = game:GetService("Players").LocalPlayer:WaitForChild("PlayerGui")

local MainContainer = Instance.new("Frame")
MainContainer.Size = UDim2.new(0, 200, 0, 220) 
MainContainer.Position = UDim2.new(0, 10, 0.4, -110)
MainContainer.BackgroundTransparency = 1
MainContainer.Parent = ScreenGui

local Frame = Instance.new("Frame")
Frame.Size = UDim2.new(1, 0, 0, 0)
Frame.Position = UDim2.new(0, 0, 0, 40)
Frame.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
Frame.BorderSizePixel = 0
Frame.ClipsDescendants = true
Frame.Parent = MainContainer

local ToggleButton = Instance.new("TextButton")
ToggleButton.Size = UDim2.new(0, 50, 0, 30)
ToggleButton.Position = UDim2.new(0, 0, 0, 0)
ToggleButton.Text = "Menu"
ToggleButton.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
ToggleButton.TextColor3 = Color3.new(1, 1, 1)
ToggleButton.TextSize = 14
ToggleButton.Font = Enum.Font.GothamBold
ToggleButton.Parent = MainContainer

local DeadRailsButton = Instance.new("TextButton")
DeadRailsButton.Size = UDim2.new(1, -20, 0, 50)
DeadRailsButton.Position = UDim2.new(0, 10, 0, 10)
DeadRailsButton.Text = "Dead Rails"
DeadRailsButton.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
DeadRailsButton.TextColor3 = Color3.new(1, 1, 1)
DeadRailsButton.TextSize = 14
DeadRailsButton.Font = Enum.Font.GothamBold
DeadRailsButton.Visible = false
DeadRailsButton.Parent = Frame

local MurderMystery2Button = Instance.new("TextButton")
MurderMystery2Button.Size = UDim2.new(1, -20, 0, 50)
MurderMystery2Button.Position = UDim2.new(0, 10, 0, 70)
MurderMystery2Button.Text = "Murder Mystery 2"
MurderMystery2Button.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
MurderMystery2Button.TextColor3 = Color3.new(1, 1, 1)
MurderMystery2Button.TextSize = 14
MurderMystery2Button.Font = Enum.Font.GothamBold
MurderMystery2Button.Visible = false
MurderMystery2Button.Parent = Frame

local ChatBypassButton = Instance.new("TextButton")
ChatBypassButton.Size = UDim2.new(1, -20, 0, 50)
ChatBypassButton.Position = UDim2.new(0, 10, 0, 130)
ChatBypassButton.Text = "Chat Bypass (қазақ тiлi)"
ChatBypassButton.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
ChatBypassButton.TextColor3 = Color3.new(1, 1, 1)
ChatBypassButton.TextSize = 14
ChatBypassButton.Font = Enum.Font.GothamBold
ChatBypassButton.Visible = false
ChatBypassButton.Parent = Frame

local menuOpen = false
local function toggleMenu()
    menuOpen = not menuOpen
    DeadRailsButton.Visible = menuOpen
    MurderMystery2Button.Visible = menuOpen
    ChatBypassButton.Visible = menuOpen
    
    if menuOpen then
        Frame:TweenSize(UDim2.new(1, 0, 0, 190), Enum.EasingDirection.Out, Enum.EasingStyle.Quad, 0.2, true) 
    else
        Frame:TweenSize(UDim2.new(1, 0, 0, 0), Enum.EasingDirection.Out, Enum.EasingStyle.Quad, 0.2, true)
    end
end

DeadRailsButton.MouseButton1Click:Connect(function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/JonasThePogi/DeadRails/refs/heads/main/newloadstring"))()
end)

MurderMystery2Button.MouseButton1Click:Connect(function()
    loadstring(game:HttpGet("https://raw.githubusercontent.com/Au0yX/Community/main/XhubMM2"))()
end)

ChatBypassButton.MouseButton1Click:Connect(function()
    loadstring(game:HttpGet('https://raw.githubusercontent.com/Gazer-Ha/bruh/refs/heads/main/ImBadd1'))()
end)

ToggleButton.MouseButton1Click:Connect(toggleMenu)
